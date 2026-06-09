# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChart

- ea: `0x89e0`
- end: `0x8a46`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChart`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x8130`

## callees

- `0x89e0`
- `0x8a50`
- `0x9f90`
- `0xa020`
- `0xa090`
- `0xa150`

## pseudocode

```c

```

## disassembly

```asm
0x89e0  ldarg.1
0x89e1  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementOutput()
0x89e6  ldc.i4.1
0x89e7  bne.un.s loc_89EA
0x89e9  ret
0x89ea  ldarg.0
0x89eb  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x89f0  ldarg.1
0x89f1  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementName()
0x89f6  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EncodeString(string aName)
0x89fb  stloc.0
0x89fc  ldloc.0
0x89fd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8a02  brfalse.s loc_8A10
0x8a04  ldarg.0
0x8a05  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8a0a  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultChartTag()
0x8a0f  stloc.0
0x8a10  ldarg.0
0x8a11  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8a16  ldloc.0
0x8a17  ldarg.2
0x8a18  ldc.i4.0
0x8a19  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartDataRegion(string name, bool firstInstance, bool optional)
0x8a1e  ldarg.1
0x8a1f  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartHierarchy [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart::get_SeriesHierarchy()
0x8a24  brfalse.s loc_8A39
0x8a26  ldarg.0
0x8a27  ldarg.1
0x8a28  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartHierarchy [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart::get_SeriesHierarchy()
0x8a2d  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartHierarchy::get_MemberCollection()
0x8a32  ldarg.1
0x8a33  ldarg.2
0x8a34  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartMemberCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMemberCollection chartMemberCollection, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart chart, bool firstInstance)
0x8a39  ldarg.0
0x8a3a  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8a3f  ldarg.2
0x8a40  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x8a45  ret
```
