# Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::ShredDocument

- ea: `0x860`
- end: `0x909`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::ShredDocument`
- size: `169`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x7a0`
- `0x800`

## callees

- `0x860`
- `0x910`
- `0x950`
- `0x990`
- `0x1580`

## pseudocode

```c

```

## disassembly

```asm
0x860  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode>::.ctor()
0x865  stloc.0
0x866  ldarg.0
0x867  ldfld    class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::m_report
0x86c  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportSection> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report::get_ReportSections()
0x871  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportSection>::GetEnumerator()
0x876  stloc.1
0x877  br.s     loc_8DA
0x879  ldloc.1
0x87a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportSection>::get_Current()
0x87f  stloc.2
0x880  ldarg.0
0x881  ldloc.2
0x882  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Body [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportSection::get_Body()
0x887  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Body::get_ReportItems()
0x88c  ldloc.0
0x88d  call     instance void Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::DecomposeReportItems(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem> items, class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode> vertices)
0x892  ldloc.2
0x893  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Page [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportSection::get_Page()
0x898  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.PageSection [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Page::get_PageHeader()
0x89d  brfalse.s loc_8B6
0x89f  ldarg.0
0x8a0  ldloc.2
0x8a1  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Page [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportSection::get_Page()
0x8a6  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.PageSection [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Page::get_PageHeader()
0x8ab  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.PageSection::get_ReportItems()
0x8b0  ldloc.0
0x8b1  call     instance void Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::DecomposeReportItems(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem> items, class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode> vertices)
0x8b6  ldloc.2
0x8b7  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Page [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportSection::get_Page()
0x8bc  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.PageSection [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Page::get_PageFooter()
0x8c1  brfalse.s loc_8DA
0x8c3  ldarg.0
0x8c4  ldloc.2
0x8c5  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Page [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportSection::get_Page()
0x8ca  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.PageSection [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Page::get_PageFooter()
0x8cf  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.PageSection::get_ReportItems()
0x8d4  ldloc.0
0x8d5  call     instance void Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::DecomposeReportItems(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem> items, class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode> vertices)
0x8da  ldloc.1
0x8db  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8e0  brtrue.s loc_879
0x8e2  leave.s  loc_8EE
0x8e4  ldloc.1
0x8e5  brfalse.s loc_8ED
0x8e7  ldloc.1
0x8e8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8ed  endfinally
0x8ee  ldarg.0
0x8ef  ldloc.0
0x8f0  call     instance void Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::DecomposeDataSets(class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode> vertices)
0x8f5  ldarg.0
0x8f6  ldloc.0
0x8f7  call     instance void Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::DecomposeReportParameters(class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode> vertices)
0x8fc  ldarg.0
0x8fd  ldloc.0
0x8fe  call     class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.LazyDependencyGraph Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.LazyDependencyGraph::ConstructAcyclicalDependencyGraph(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode> initialVertices)
0x903  stfld    class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.LazyDependencyGraph Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::m_graph
0x908  ret
```
