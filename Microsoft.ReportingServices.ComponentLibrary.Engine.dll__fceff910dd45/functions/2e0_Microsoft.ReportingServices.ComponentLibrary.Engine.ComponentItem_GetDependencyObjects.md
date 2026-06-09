# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::GetDependencyObjects

- ea: `0x2e0`
- end: `0x331`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::GetDependencyObjects`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1c0`
- `0x2c0`
- `0x3f0`
- `0x800`
- `0x830`
- `0x840`
- `0x1dd0`

## pseudocode

```c

```

## disassembly

```asm
0x2e0  newobj   instance void <>c__DisplayClass29_0::.ctor()
0x2e5  stloc.0
0x2e6  ldloc.0
0x2e7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject>::.ctor()
0x2ec  stfld    class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject> <>c__DisplayClass29_0::dependencies
0x2f1  ldarg.0
0x2f2  call     instance class Microsoft.ReportingServices.ComponentLibrary.Engine.RdlFragment Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_RdlFragment()
0x2f7  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject Microsoft.ReportingServices.ComponentLibrary.Engine.RdlFragment::get_RdlObject()
0x2fc  castclass [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report
0x301  newobj   instance void Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::.ctor(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report report)
0x306  dup
0x307  callvirt instance class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.IDirectedGraph`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode> Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::get_DependencyGraph()
0x30c  pop
0x30d  ldloc.0
0x30e  ldarg.0
0x30f  call     instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_RdlObject()
0x314  stfld    class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject <>c__DisplayClass29_0::component
0x319  ldloc.0
0x31a  ldftn    instance void <>c__DisplayClass29_0::<GetDependencyObjects>b__0(class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode node)
0x320  newobj   instance void class [mscorlib]System.Action`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode>::.ctor(object, native int)
0x325  callvirt instance void Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::TraverseFromDependencyNodes(class [mscorlib]System.Action`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode> handler)
0x32a  ldloc.0
0x32b  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject> <>c__DisplayClass29_0::dependencies
0x330  ret
```
