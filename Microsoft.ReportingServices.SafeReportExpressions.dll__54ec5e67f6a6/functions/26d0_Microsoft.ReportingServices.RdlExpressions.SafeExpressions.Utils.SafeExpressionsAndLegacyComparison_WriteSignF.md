# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteSignForNumericResult

- ea: `0x26d0`
- end: `0x26e3`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteSignForNumericResult`
- size: `19`
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
0x26d0  ldarg.1
0x26d1  ldstr    aNumericresults// "NumericResultSign"
0x26d6  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x26db  ldarg.1
0x26dc  ldarg.2
0x26dd  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(int32)
0x26e2  ret
```
