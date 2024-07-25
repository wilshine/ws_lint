# 自定义Lint规则

## use_emit_synchronously

用于检测bloc中使用emit前，如果有异步操作，且没有添加isClosed判断的情况。此种情况下，emit会抛出异常。

## 使用方法

参考custom_lint[官方配置](https://pub.dev/packages/custom_lint)


```yaml
include: package:flutter_lints/flutter.yaml

analyzer:
  plugins:
    - custom_lint
  exclude:
    - lib/services/model/**
    - lib/**/*.page.dart
  errors:
    prefer_const_constructors: warning # const优化性能
    use_build_context_synchronously: warning # 异步使用BuildContext
    use_emit_synchronously: warning # 异步使用emit
  language:
    strict-casts: false # 严格类型转换，dynamic不再进行隐式类型转换
    strict-inference: false
    strict-raw-types: false

linter:
  rules:
    package_api_docs: true
    comment_references: true
    curly_braces_in_flow_control_structures: true
    library_names: true
    file_names: true
    library_prefixes: true
    camel_case_types: true
    camel_case_extensions: true
    non_constant_identifier_names: false
    constant_identifier_names: false
    use_rethrow_when_possible: true
    cancel_subscriptions: true
    close_sinks: true
    prefer_const_constructors: true
    avoid_print: true  # Uncomment to disable the `avoid_print` rule
    prefer_single_quotes: true  # Uncomment to enable the `prefer_single_quotes` rule

custom_lint:
  debug: true
  verbose: true

```