# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::WriteAtomServiceDocument

- ea: `0x1cf0`
- end: `0x1d65`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::WriteAtomServiceDocument`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a90`

## callees

- `0x1cf0`
- `0x23e0`
- `0x26b0`
- `0x29d0`
- `0x2bd0`
- `0x2be0`
- `0x6c00`
- `0x6d00`
- `0x6d60`
- `0x6f70`

## pseudocode

```c

```

## disassembly

```asm
0x1cf0  ldnull
0x1cf1  ldnull
0x1cf2  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandlerSql11::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.AtomSchemaVisitor visitor, class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> feedNames)
0x1cf7  stloc.0
0x1cf8  ldloc.0
0x1cf9  ldloc.0
0x1cfa  ldloc.0
0x1cfb  ldloc.0
0x1cfc  ldc.i4.0
0x1cfd  ldc.i4.1
0x1cfe  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler reportHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler outputRowHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.ITablixHandler tablixHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase dvHandler, bool instanceWalk, bool walkTopLevelOnly)
0x1d03  dup
0x1d04  ldarg.2
0x1d05  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkReport(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report)
0x1d0a  callvirt instance class [mscorlib]System.Collections.IEnumerator Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::get_TopLevelDataRegionsOrMaps()
0x1d0f  stloc.1
0x1d10  ldarg.1
0x1d11  ldarg.3
0x1d12  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentVisitor::.ctor(class [System.Xml]System.Xml.XmlWriter xmlWriter, class [System]System.Collections.Specialized.NameValueCollection reportServerParameters)
0x1d17  stloc.2
0x1d18  ldloc.2
0x1d19  ldarg.2
0x1d1a  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentVisitor::CreateServiceDocument(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report)
0x1d1f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor()
0x1d24  stloc.3
0x1d25  br.s     loc_1D5C
0x1d27  ldloc.2
0x1d28  ldloc.3
0x1d29  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandlerSql11::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.AtomSchemaVisitor visitor, class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> feedNames)
0x1d2e  stloc.s  4
0x1d30  ldloc.s  4
0x1d32  ldloc.s  4
0x1d34  ldloc.s  4
0x1d36  ldloc.s  4
0x1d38  ldc.i4.0
0x1d39  ldc.i4.0
0x1d3a  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler reportHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler outputRowHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.ITablixHandler tablixHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase dvHandler, bool instanceWalk, bool walkTopLevelOnly)
0x1d3f  ldloc.1
0x1d40  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1d45  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem
0x1d4a  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkDataRegionOrMap(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem)
0x1d4f  ldloc.s  4
0x1d51  ldloc.0
0x1d52  callvirt instance class DynamicElement Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::get_DynamicElementRoot()
0x1d57  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::WriteCollection(class DynamicElement topLevelScope)
0x1d5c  ldloc.1
0x1d5d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1d62  brtrue.s loc_1D27
0x1d64  ret
```
