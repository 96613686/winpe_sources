# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::AddDependency

- ea: `0x380`
- end: `0x3b4`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::AddDependency`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1e90`

## callees

- `0x380`
- `0x410`

## string_xrefs

- `0x3a8`: `The type of the dependency object is not supported on this Component`

## pseudocode

```c

```

## disassembly

```asm
0x380  ldarg.1
0x381  brtrue.s loc_38E
0x383  ldstr    aRdlobject// "rdlObject"
0x388  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x38d  throw
0x38e  ldarg.1
0x38f  callvirt instance object [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject::DeepClone()
0x394  isinst   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject
0x399  stloc.0
0x39a  ldarg.0
0x39b  ldfld    class Microsoft.ReportingServices.ComponentLibrary.Engine.RdlFragment Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::m_rdlFragment
0x3a0  ldloc.0
0x3a1  callvirt instance bool Microsoft.ReportingServices.ComponentLibrary.Engine.RdlFragment::AddRdlObject(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject rdlObject)
0x3a6  brtrue.s loc_3B3
0x3a8  ldstr    aTheTypeOfTheDe// "The type of the dependency object is no"...
0x3ad  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3b2  throw
0x3b3  ret
```
