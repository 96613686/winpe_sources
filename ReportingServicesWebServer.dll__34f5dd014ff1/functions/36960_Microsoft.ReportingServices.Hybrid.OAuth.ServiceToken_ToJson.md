# Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken::ToJson

- ea: `0x36960`
- end: `0x369b3`
- name: `Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken::ToJson`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x36450`

## callees

- `0x36960`

## string_xrefs

- `0x36998`: `Error serializing saved json Service token. Message from Exception: `

## pseudocode

```c

```

## disassembly

```asm
0x36960  ldtoken  Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken
0x36965  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3696a  newobj   instance void [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer::.ctor(class [mscorlib]System.Type)
0x3696f  stloc.0
0x36970  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x36975  stloc.1
0x36976  ldloc.0
0x36977  ldloc.1
0x36978  ldarg.0
0x36979  callvirt instance void [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer::WriteObject(class [mscorlib]System.IO.Stream, object)
0x3697e  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Default()
0x36983  ldloc.1
0x36984  callvirt instance unsigned int8[] [mscorlib]System.IO.MemoryStream::ToArray()
0x36989  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x3698e  stloc.2
0x3698f  leave.s  loc_369B1
0x36991  stloc.3
0x36992  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x36997  ldc.i4.2
0x36998  ldstr    aErrorSerializi// "Error serializing saved json Service to"...
0x3699d  ldloc.3
0x3699e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x369a3  call     string [mscorlib]System.String::Concat(string, string)
0x369a8  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x369ad  ldnull
0x369ae  stloc.2
0x369af  leave.s  loc_369B1
0x369b1  ldloc.2
0x369b2  ret
```
