# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareExpressionResults

- ea: `0x16f0`
- end: `0x170e`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareExpressionResults`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1710`

## pseudocode

```c

```

## disassembly

```asm
0x16f0  ldarg.0
0x16f1  ldsfld   string [mscorlib]System.String::Empty
0x16f6  stfld    string Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_mismatchDetail
0x16fb  ldarg.0
0x16fc  ldarg.0
0x16fd  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x1702  ldarg.0
0x1703  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x1708  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareObjects(object legacyExprResult, object safeExprResult)
0x170d  ret
```
