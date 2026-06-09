# <>c__DisplayClass21_0::<CompareObjects>b__0

- ea: `0x2df0`
- end: `0x2e08`
- name: `<>c__DisplayClass21_0::<CompareObjects>b__0`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1ac0`

## pseudocode

```c

```

## disassembly

```asm
0x2df0  ldarg.0
0x2df1  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison <>c__DisplayClass21_0::<>4__this
0x2df6  ldarg.0
0x2df7  ldfld    object <>c__DisplayClass21_0::legacyExprResult
0x2dfc  ldarg.0
0x2dfd  ldfld    object <>c__DisplayClass21_0::safeExprResult
0x2e02  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareArrays(object a1, object a2)
0x2e07  ret
```
