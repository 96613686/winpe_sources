# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteObjectLength

- ea: `0x26b0`
- end: `0x26c3`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteObjectLength`
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
0x26b0  ldarg.1
0x26b1  ldstr    aResultlength// "ResultLength"
0x26b6  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x26bb  ldarg.1
0x26bc  ldarg.2
0x26bd  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(int32)
0x26c2  ret
```
