# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::WriteAtomDataFeed

- ea: `0x1d70`
- end: `0x1e8c`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::WriteAtomDataFeed`
- size: `284`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a90`
- `0x2110`

## callees

- `0x180`
- `0x1170`
- `0x16c0`
- `0x19b0`
- `0x1d70`
- `0x2030`
- `0x21e0`
- `0x2200`
- `0x22c0`
- `0x2900`
- `0x2ed0`
- `0x30a0`
- `0x31f0`
- `0x3520`
- `0x35d0`
- `0x3660`
- `0x5740`
- `0x6c00`
- `0x6d00`
- `0x6d60`
- `0x6f70`

## pseudocode

```c

```

## disassembly

```asm
0x1d70  ldarg.0
0x1d71  ldfld    valuetype DataFeedIdentifierType Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_dataFeedIdentifierType
0x1d76  ldc.i4.2
0x1d77  bne.un.s loc_1D97
0x1d79  ldarg.2
0x1d7a  call     class DynamicElement Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::GetDynamicElementTree(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report)
0x1d7f  ldarg.s  4
0x1d81  call     string Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::GetDefinitionPath(class DynamicElement dynamicElement, string reportItemPath)
0x1d86  starg.s  4
0x1d88  ldarg.s  4
0x1d8a  brtrue.s loc_1D97
0x1d8c  call     string Microsoft.ReportingServices.DataRendering.StringResources::get_rrDataFeedNotFound()
0x1d91  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportRenderingException::.ctor(string)
0x1d96  throw
0x1d97  ldarg.1
0x1d98  ldarg.3
0x1d99  ldarg.2
0x1d9a  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameterCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_Parameters()
0x1d9f  ldarg.0
0x1da0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_dataFeedQueries
0x1da5  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::.ctor(class [System.Xml]System.Xml.XmlWriter xmlWriter, class [System]System.Collections.Specialized.NameValueCollection reportServerParameters, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameterCollection reportParamters, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> dataFeedQueries)
0x1daa  stloc.0
0x1dab  ldloc.0
0x1dac  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::CreateSyndicationFeed()
0x1db1  ldloc.0
0x1db2  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::ClearColumnNames()
0x1db7  ldloc.0
0x1db8  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::ClearFeedLevelRowContent()
0x1dbd  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.NullHandler::.ctor()
0x1dc2  stloc.1
0x1dc3  ldloc.0
0x1dc4  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedTextBoxHandler::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor visitor)
0x1dc9  ldloc.1
0x1dca  ldloc.1
0x1dcb  ldloc.1
0x1dcc  ldc.i4.0
0x1dcd  ldc.i4.1
0x1dce  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler reportHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler outputRowHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.ITablixHandler tablixHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase dvHandler, bool instanceWalk, bool walkTopLevelOnly)
0x1dd3  dup
0x1dd4  ldarg.2
0x1dd5  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkReport(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report)
0x1dda  callvirt instance class [mscorlib]System.Collections.IEnumerator Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::get_TopLevelDataRegionsOrMaps()
0x1ddf  stloc.2
0x1de0  br       loc_1E76
0x1de5  ldloc.2
0x1de6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1deb  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem
0x1df0  stloc.3
0x1df1  ldloc.3
0x1df2  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_DefinitionPath()
0x1df7  ldarg.s  4
0x1df9  call     bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::IsOnDefinitionPath(string item, string path)
0x1dfe  brfalse.s loc_1E76
0x1e00  ldarg.0
0x1e01  ldloc.3
0x1e02  ldarg.s  4
0x1e04  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::GetStepsToDefinitonPath(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem, string definitionPath)
0x1e09  stloc.s  4
0x1e0b  ldloc.s  4
0x1e0d  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x1e12  brtrue.s loc_1E1F
0x1e14  call     string Microsoft.ReportingServices.DataRendering.StringResources::get_rrDataFeedNotFound()
0x1e19  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportRenderingException::.ctor(string)
0x1e1e  throw
0x1e1f  ldloc.0
0x1e20  ldloc.s  4
0x1e22  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor visitor, class [mscorlib]System.Collections.Generic.List`1<string> definitionPathSteps)
0x1e27  stloc.s  5
0x1e29  ldloc.s  5
0x1e2b  ldloc.s  5
0x1e2d  ldloc.s  5
0x1e2f  ldloc.s  5
0x1e31  ldc.i4.0
0x1e32  ldc.i4.0
0x1e33  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler reportHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler outputRowHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.ITablixHandler tablixHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase dvHandler, bool instanceWalk, bool walkTopLevelOnly)
0x1e38  ldloc.3
0x1e39  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkDataRegionOrMap(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem)
0x1e3e  ldarg.0
0x1e3f  ldloc.3
0x1e40  ldloc.s  4
0x1e42  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::ResolveDataTypes(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem, class [mscorlib]System.Collections.Generic.List`1<string> definitionPathSteps)
0x1e47  stloc.s  6
0x1e49  ldloc.0
0x1e4a  ldloc.s  6
0x1e4c  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::SetResolvedEdmTypes(class [mscorlib]System.Collections.Generic.List`1<string> resolvedEdmTypes)
0x1e51  ldloc.0
0x1e52  ldloc.s  4
0x1e54  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor visitor, class [mscorlib]System.Collections.Generic.List`1<string> definitionPathSteps)
0x1e59  stloc.s  7
0x1e5b  ldloc.s  7
0x1e5d  ldloc.s  7
0x1e5f  ldloc.s  7
0x1e61  ldloc.s  7
0x1e63  ldc.i4.1
0x1e64  ldc.i4.0
0x1e65  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler reportHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler outputRowHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.ITablixHandler tablixHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase dvHandler, bool instanceWalk, bool walkTopLevelOnly)
0x1e6a  stloc.s  8
0x1e6c  ldloc.0
0x1e6d  ldloc.s  8
0x1e6f  ldloc.3
0x1e70  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteDataRegionFeed(class Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker dataRegionWalker, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem)
0x1e75  ret
0x1e76  ldloc.2
0x1e77  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1e7c  brtrue   loc_1DE5
0x1e81  call     string Microsoft.ReportingServices.DataRendering.StringResources::get_rrDataFeedNotFound()
0x1e86  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportRenderingException::.ctor(string)
0x1e8b  throw
```
