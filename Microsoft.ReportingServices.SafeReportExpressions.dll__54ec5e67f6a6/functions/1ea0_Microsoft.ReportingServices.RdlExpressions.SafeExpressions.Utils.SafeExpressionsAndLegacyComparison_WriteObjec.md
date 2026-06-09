# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteObjectProperties

- ea: `0x1ea0`
- end: `0x1ee3`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteObjectProperties`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1e10`

## callees

- `0x1ea0`
- `0x1ef0`

## pseudocode

```c

```

## disassembly

```asm
0x1ea0  ldarg.2
0x1ea1  brtrue.s loc_1EA6
0x1ea3  ldnull
0x1ea4  br.s     loc_1EAC
0x1ea6  ldarg.2
0x1ea7  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1eac  stloc.0
0x1ead  ldarg.1
0x1eae  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteStartObject()
0x1eb3  ldarg.1
0x1eb4  ldstr    aObjecttype// "ObjectType"
0x1eb9  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x1ebe  ldarg.1
0x1ebf  ldloc.0
0x1ec0  brtrue.s loc_1EC5
0x1ec2  ldnull
0x1ec3  br.s     loc_1ECB
0x1ec5  ldloc.0
0x1ec6  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1ecb  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(string)
0x1ed0  ldarg.2
0x1ed1  brfalse.s loc_1EDC
0x1ed3  ldarg.0
0x1ed4  ldarg.1
0x1ed5  ldarg.2
0x1ed6  ldloc.0
0x1ed7  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteTypeBasedDetails(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, object result, class [mscorlib]System.Type resultType)
0x1edc  ldarg.1
0x1edd  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteEndObject()
0x1ee2  ret
```
