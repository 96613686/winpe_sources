# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItemFactory::CreateFromXml

- ea: `0x580`
- end: `0x5d6`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItemFactory::CreateFromXml`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x340`
- `0x580`
- `0x710`
- `0xd00`
- `0x19b0`

## pseudocode

```c

```

## disassembly

```asm
0x580  ldarg.0
0x581  brtrue.s loc_58E
0x583  ldstr    aDefinitionsour// "definitionSource"
0x588  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x58d  throw
0x58e  nop
0x58f  ldarg.0
0x590  callvirt instance bool [mscorlib]System.IO.Stream::get_CanSeek()
0x595  brfalse.s loc_5A1
0x597  ldarg.0
0x598  ldc.i4.0
0x599  conv.i8
0x59a  ldc.i4.0
0x59b  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x5a0  pop
0x5a1  call     class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Serialization.RdlSerializer Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItemFactory::GetSerializer()
0x5a6  ldarg.0
0x5a7  ldtoken  Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem
0x5ac  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5b1  callvirt instance object [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Serialization.RdlSerializer::Deserialize(class [mscorlib]System.IO.Stream, class [mscorlib]System.Type)
0x5b6  castclass Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem
0x5bb  dup
0x5bc  callvirt instance void Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::ValidateComponent()
0x5c1  stloc.0
0x5c2  leave.s  loc_5D4
0x5c4  pop
0x5c5  rethrow
0x5c7  stloc.1
0x5c8  call     string Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ComponentItem_CreationFailed()
0x5cd  ldloc.1
0x5ce  newobj   instance void Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Exceptions.ComponentEngineException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x5d3  throw
0x5d4  ldloc.0
0x5d5  ret
```
