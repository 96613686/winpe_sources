# <>c__DisplayClass21_0::<CompareObjects>b__4

- ea: `0x2e80`
- end: `0x2e98`
- name: `<>c__DisplayClass21_0::<CompareObjects>b__4`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x19d0`

## pseudocode

```c

```

## disassembly

```asm
0x2e80  ldarg.0
0x2e81  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison <>c__DisplayClass21_0::<>4__this
0x2e86  ldarg.0
0x2e87  ldfld    object <>c__DisplayClass21_0::legacyExprResult
0x2e8c  ldarg.0
0x2e8d  ldfld    object <>c__DisplayClass21_0::safeExprResult
0x2e92  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareComplexObjects(object legacyExprResult, object safeExprResult)
0x2e97  ret
```
