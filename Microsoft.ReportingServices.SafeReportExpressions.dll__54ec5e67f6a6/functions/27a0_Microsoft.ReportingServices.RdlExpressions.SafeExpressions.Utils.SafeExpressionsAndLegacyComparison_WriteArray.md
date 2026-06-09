# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteArrayLength

- ea: `0x27a0`
- end: `0x27bf`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteArrayLength`
- size: `31`
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
0x27a0  ldarg.2
0x27a1  isinst   [mscorlib]System.Array
0x27a6  stloc.0
0x27a7  ldarg.1
0x27a8  ldstr    aResultlength// "ResultLength"
0x27ad  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x27b2  ldarg.1
0x27b3  ldloc.0
0x27b4  callvirt instance int32 [mscorlib]System.Array::get_Length()
0x27b9  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(int32)
0x27be  ret
```
