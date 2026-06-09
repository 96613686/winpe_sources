# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItemFactory::Create_0

- ea: `0x690`
- end: `0x702`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItemFactory::Create_0`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x5e0`

## callees

- `0x540`
- `0x560`
- `0x690`
- `0xb30`

## pseudocode

```c

```

## disassembly

```asm
0x690  ldarg.0
0x691  call     class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::GetType(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject rdlObject)
0x696  stloc.0
0x697  ldloc.0
0x698  brfalse.s loc_700
0x69a  ldarg.0
0x69b  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ComponentMetadata [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject::get_ComponentMetadata()
0x6a0  brtrue.s loc_6AD
0x6a2  ldarg.0
0x6a3  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ComponentMetadata::.ctor()
0x6a8  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject::set_ComponentMetadata(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ComponentMetadata)
0x6ad  ldarg.0
0x6ae  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ComponentMetadata [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject::get_ComponentMetadata()
0x6b3  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ComponentMetadata::get_ComponentId()
0x6b8  stloc.1
0x6b9  ldloca.s 1
0x6bb  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x6c0  brtrue.s loc_6D7
0x6c2  ldarg.0
0x6c3  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ComponentMetadata [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject::get_ComponentMetadata()
0x6c8  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x6cd  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x6d2  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ComponentMetadata::set_ComponentId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x6d7  ldarg.0
0x6d8  isinst   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem
0x6dd  brfalse.s loc_6EC
0x6df  ldarg.0
0x6e0  castclass [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem
0x6e5  ldloc.0
0x6e6  newobj   instance void Microsoft.ReportingServices.ComponentLibrary.Engine.ReportItemComponent::.ctor(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem reportItem, class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType type)
0x6eb  ret
0x6ec  ldarg.0
0x6ed  isinst   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportParameter
0x6f2  brfalse.s loc_700
0x6f4  ldarg.0
0x6f5  castclass [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportParameter
0x6fa  newobj   instance void Microsoft.ReportingServices.ComponentLibrary.Engine.ReportParameterComponent::.ctor(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportParameter reportParam)
0x6ff  ret
0x700  ldnull
0x701  ret
```
