# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteDecimalIndexForNumericResult

- ea: `0x26f0`
- end: `0x270d`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteDecimalIndexForNumericResult`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ef0`

## pseudocode

```c

```

## disassembly

```asm
0x26f0  ldarg.1
0x26f1  ldstr    aNumericresultd// "NumericResultDecimalIndex"
0x26f6  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x26fb  ldarg.1
0x26fc  ldarg.2
0x26fd  ldstr    asc_49FA// "."
0x2702  callvirt instance int32 [mscorlib]System.String::IndexOf(string)
0x2707  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(int32)
0x270c  ret
```
