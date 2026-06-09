# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::WriteXml

- ea: `0x350`
- end: `0x37c`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::WriteXml`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x350`
- `0x710`
- `0xcf0`
- `0x19f0`

## pseudocode

```c

```

## disassembly

```asm
0x350  ldarg.1
0x351  brtrue.s loc_35E
0x353  ldstr    aStream// "stream"
0x358  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x35d  throw
0x35e  call     class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Serialization.RdlSerializer Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItemFactory::GetSerializer()
0x363  stloc.0
0x364  ldloc.0
0x365  ldarg.1
0x366  ldarg.0
0x367  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Serialization.RdlSerializer::Serialize(class [mscorlib]System.IO.Stream, object)
0x36c  leave.s  loc_37B
0x36e  stloc.1
0x36f  call     string Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ComponentItem_SerializationFailed()
0x374  ldloc.1
0x375  newobj   instance void Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Exceptions.InternalComponentEngineException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x37a  throw
0x37b  ret
```
