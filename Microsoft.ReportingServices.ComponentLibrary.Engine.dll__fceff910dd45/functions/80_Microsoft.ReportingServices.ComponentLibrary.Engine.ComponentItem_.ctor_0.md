# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::.ctor_0

- ea: `0x80`
- end: `0x10c`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::.ctor_0`
- size: `140`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x540`
- `0x560`

## callees

- `0x80`
- `0x120`
- `0x1f0`
- `0x3d0`
- `0x410`
- `0xb50`
- `0xcc0`
- `0x19a0`
- `0x1db0`

## pseudocode

```c

```

## disassembly

```asm
0x80  ldarg.0
0x81  newobj   instance void ComponentProperties::.ctor()
0x86  stfld    class ComponentProperties Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::m_componentProperies
0x8b  ldarg.0
0x8c  newobj   instance void Microsoft.ReportingServices.ComponentLibrary.Engine.RdlFragment::.ctor()
0x91  stfld    class Microsoft.ReportingServices.ComponentLibrary.Engine.RdlFragment Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::m_rdlFragment
0x96  ldarg.0
0x97  call     instance void [mscorlib]System.Object::.ctor()
0x9c  ldarg.1
0x9d  brtrue.s loc_AA
0x9f  ldstr    aRdlobject// "rdlObject"
0xa4  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa9  throw
0xaa  ldarg.2
0xab  brtrue.s loc_B8
0xad  ldstr    aType// "type"
0xb2  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb7  throw
0xb8  ldarg.1
0xb9  isinst   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.INamedObject
0xbe  brtrue.s loc_CB
0xc0  call     string Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ComponentItem_InvalidType()
0xc5  newobj   instance void Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Exceptions.ComponentEngineException::.ctor(string message)
0xca  throw
0xcb  ldarg.0
0xcc  ldarg.1
0xcd  castclass [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.INamedObject
0xd2  callvirt instance string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.INamedObject::get_Name()
0xd7  call     instance void Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::set_Name(string value)
0xdc  ldarg.0
0xdd  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_Properties()
0xe2  ldstr    aType_0// "Type"
0xe7  ldarg.2
0xe8  callvirt instance string Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::get_Name()
0xed  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xf2  ldarg.1
0xf3  callvirt instance object [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject::DeepClone()
0xf8  isinst   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject
0xfd  stloc.0
0xfe  ldarg.0
0xff  ldfld    class Microsoft.ReportingServices.ComponentLibrary.Engine.RdlFragment Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::m_rdlFragment
0x104  ldloc.0
0x105  callvirt instance bool Microsoft.ReportingServices.ComponentLibrary.Engine.RdlFragment::AddRdlObject(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject rdlObject)
0x10a  pop
0x10b  ret
```
