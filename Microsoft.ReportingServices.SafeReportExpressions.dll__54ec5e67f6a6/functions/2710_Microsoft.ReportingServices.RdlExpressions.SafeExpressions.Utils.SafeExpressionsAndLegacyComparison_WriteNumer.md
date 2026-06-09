# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteNumericResultDiff

- ea: `0x2710`
- end: `0x2723`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteNumericResultDiff`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2170`

## pseudocode

```c

```

## disassembly

```asm
0x2710  ldarg.1
0x2711  ldstr    aNumericresultd_0// "NumericResultDiff"
0x2716  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x271b  ldarg.1
0x271c  ldarg.2
0x271d  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(object)
0x2722  ret
```
