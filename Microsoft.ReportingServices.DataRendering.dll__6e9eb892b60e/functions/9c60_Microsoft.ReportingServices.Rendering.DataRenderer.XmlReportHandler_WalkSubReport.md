# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkSubReport

- ea: `0x9c60`
- end: `0x9cd7`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkSubReport`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x8130`

## callees

- `0x7ec0`
- `0x9c60`
- `0x9f90`
- `0xa020`
- `0xa090`
- `0xa140`

## pseudocode

```c

```

## disassembly

```asm
0x9c60  ldarg.0
0x9c61  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9c66  ldarg.1
0x9c67  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementName()
0x9c6c  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EncodeString(string aName)
0x9c71  stloc.0
0x9c72  ldloc.0
0x9c73  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9c78  brfalse.s loc_9C86
0x9c7a  ldarg.0
0x9c7b  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9c80  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultSubreportTag()
0x9c85  stloc.0
0x9c86  ldarg.0
0x9c87  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9c8c  ldloc.0
0x9c8d  ldarg.2
0x9c8e  ldc.i4.0
0x9c8f  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartDataRegion(string name, bool firstInstance, bool optional)
0x9c94  ldarg.1
0x9c95  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Instance()
0x9c9a  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReportInstance
0x9c9f  stloc.1
0x9ca0  ldloc.1
0x9ca1  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReportInstance::get_ProcessedWithError()
0x9ca6  brfalse.s loc_9CB4
0x9ca8  ldloc.1
0x9ca9  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReportInstance::get_ErrorMessage()
0x9cae  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportRenderingException::.ctor(string)
0x9cb3  throw
0x9cb4  ldarg.1
0x9cb5  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReport::get_Report()
0x9cba  brfalse.s loc_9CCA
0x9cbc  ldarg.0
0x9cbd  ldarg.1
0x9cbe  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReport::get_Report()
0x9cc3  ldc.i4.0
0x9cc4  ldarg.2
0x9cc5  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkReport(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report, bool rootReport, bool firstInstance)
0x9cca  ldarg.0
0x9ccb  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9cd0  ldarg.2
0x9cd1  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x9cd6  ret
```
