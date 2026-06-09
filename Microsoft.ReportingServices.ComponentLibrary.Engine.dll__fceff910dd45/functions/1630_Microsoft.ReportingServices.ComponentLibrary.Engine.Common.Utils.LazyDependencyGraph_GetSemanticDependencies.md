# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.LazyDependencyGraph::GetSemanticDependencies

- ea: `0x1630`
- end: `0x168a`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.LazyDependencyGraph::GetSemanticDependencies`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x15e0`

## callees

- `0xbe0`
- `0xc40`
- `0xc60`
- `0x1630`

## pseudocode

```c

```

## disassembly

```asm
0x1630  ldarg.1
0x1631  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::get_Dependency()
0x1636  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject::GetDependencies()
0x163b  stloc.0
0x163c  ldloc.0
0x163d  brfalse.s loc_1689
0x163f  ldloc.0
0x1640  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject>::get_Count()
0x1645  ldc.i4.0
0x1646  ble.s    loc_1689
0x1648  ldloc.0
0x1649  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject>::GetEnumerator()
0x164e  stloc.1
0x164f  br.s     loc_1675
0x1651  ldloc.1
0x1652  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject>::get_Current()
0x1657  stloc.2
0x1658  ldloc.2
0x1659  isinst   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.CodeObject
0x165e  brfalse.s loc_1669
0x1660  ldarg.1
0x1661  ldc.i4.1
0x1662  callvirt instance void Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::set_HasCodeDependency(bool value)
0x1667  br.s     loc_1675
0x1669  ldarg.2
0x166a  ldloc.2
0x166b  newobj   instance void Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::.ctor(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject dependency)
0x1670  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode>::Add(var<u1>)
0x1675  ldloc.1
0x1676  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x167b  brtrue.s loc_1651
0x167d  leave.s  loc_1689
0x167f  ldloc.1
0x1680  brfalse.s loc_1688
0x1682  ldloc.1
0x1683  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1688  endfinally
0x1689  ret
```
