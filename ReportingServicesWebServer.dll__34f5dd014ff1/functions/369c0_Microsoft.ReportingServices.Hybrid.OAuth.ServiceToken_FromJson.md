# Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken::FromJson

- ea: `0x369c0`
- end: `0x36a1a`
- name: `Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken::FromJson`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x36470`

## callees

- `0x369c0`

## string_xrefs

- `0x369ff`: `Error deserialzing json Service token. Message from Exception: `

## pseudocode

```c

```

## disassembly

```asm
0x369c0  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0x369c5  ldarg.0
0x369c6  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x369cb  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0x369d0  stloc.0
0x369d1  ldtoken  Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken
0x369d6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x369db  newobj   instance void [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer::.ctor(class [mscorlib]System.Type)
0x369e0  ldloc.0
0x369e1  callvirt instance object [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer::ReadObject(class [mscorlib]System.IO.Stream)
0x369e6  castclass Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken
0x369eb  stloc.1
0x369ec  leave.s  loc_36A18
0x369ee  ldloc.0
0x369ef  brfalse.s loc_369F7
0x369f1  ldloc.0
0x369f2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x369f7  endfinally
0x369f8  stloc.2
0x369f9  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x369fe  ldc.i4.2
0x369ff  ldstr    aErrorDeserialz// "Error deserialzing json Service token. "...
0x36a04  ldloc.2
0x36a05  callvirt instance string [mscorlib]System.Exception::get_Message()
0x36a0a  call     string [mscorlib]System.String::Concat(string, string)
0x36a0f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x36a14  ldnull
0x36a15  stloc.1
0x36a16  leave.s  loc_36A18
0x36a18  ldloc.1
0x36a19  ret
```
