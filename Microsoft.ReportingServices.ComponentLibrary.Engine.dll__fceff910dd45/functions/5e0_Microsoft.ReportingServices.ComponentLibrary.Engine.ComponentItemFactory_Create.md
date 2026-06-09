# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItemFactory::Create

- ea: `0x5e0`
- end: `0x690`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItemFactory::Create`
- size: `176`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x5e0`
- `0x690`
- `0xc40`
- `0xd00`
- `0x1580`
- `0x19a0`
- `0x1e80`
- `0x1ec0`

## pseudocode

```c

```

## disassembly

```asm
0x5e0  newobj   instance void <>c__DisplayClass1_0::.ctor()
0x5e5  stloc.0
0x5e6  ldarg.0
0x5e7  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::get_Dependency()
0x5ec  brtrue.s loc_5F9
0x5ee  ldstr    aElement// "element"
0x5f3  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5f8  throw
0x5f9  ldarg.1
0x5fa  brtrue.s loc_607
0x5fc  ldstr    aGraph// "graph"
0x601  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x606  throw
0x607  ldloc.0
0x608  ldarg.0
0x609  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::get_Dependency()
0x60e  stfld    class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject <>c__DisplayClass1_0::rdlObject
0x613  ldloc.0
0x614  ldloc.0
0x615  ldfld    class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject <>c__DisplayClass1_0::rdlObject
0x61a  call     class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItemFactory::Create(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject rdlObject)
0x61f  stfld    class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem <>c__DisplayClass1_0::component
0x624  ldloc.0
0x625  ldfld    class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem <>c__DisplayClass1_0::component
0x62a  brfalse.s loc_689
0x62c  newobj   instance void <>c__DisplayClass1_1::.ctor()
0x631  stloc.1
0x632  ldloc.1
0x633  ldloc.0
0x634  stfld    class <>c__DisplayClass1_0 <>c__DisplayClass1_1::CS$<>8__locals1
0x639  ldloc.1
0x63a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode>::.ctor()
0x63f  stfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode> <>c__DisplayClass1_1::subgraphNodes
0x644  ldarg.1
0x645  ldarg.0
0x646  ldloc.1
0x647  ldftn    instance void <>c__DisplayClass1_1::<Create>b__0(class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode node)
0x64d  newobj   instance void class [mscorlib]System.Action`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode>::.ctor(object, native int)
0x652  call     T0x2B000001
0x657  ldloc.1
0x658  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode> <>c__DisplayClass1_1::subgraphNodes
0x65d  call     class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.LazyDependencyGraph Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.LazyDependencyGraph::ConstructAcyclicalDependencyGraph(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode> initialVertices)
0x662  stloc.2
0x663  ldloc.2
0x664  ldloc.1
0x665  ldfld    class <>c__DisplayClass1_0 <>c__DisplayClass1_1::CS$<>8__locals1
0x66a  ldftn    instance void <>c__DisplayClass1_0::<Create>b__1(class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode node)
0x670  newobj   instance void class [mscorlib]System.Action`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode>::.ctor(object, native int)
0x675  call     T0x2B000002
0x67a  pop
0x67b  leave.s  loc_689
0x67d  pop
0x67e  call     string Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ComponentItem_CreationFailed()
0x683  newobj   instance void Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Exceptions.ComponentEngineException::.ctor(string message)
0x688  throw
0x689  ldloc.0
0x68a  ldfld    class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem <>c__DisplayClass1_0::component
0x68f  ret
```
