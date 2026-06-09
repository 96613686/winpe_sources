# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeScaleRange

- ea: `0x9980`
- end: `0x99d9`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeScaleRange`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x9930`

## callees

- `0x9980`
- `0x9a80`
- `0x9fa0`
- `0xa020`
- `0xa270`
- `0xa280`
- `0xa290`

## pseudocode

```c

```

## disassembly

```asm
0x9980  ldarg.1
0x9981  brtrue.s loc_9984
0x9983  ret
0x9984  ldarg.0
0x9985  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x998a  ldarg.0
0x998b  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9990  ldarg.2
0x9991  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getGaugeScaleRangeTag(int32 aGaugeScaleRangeIndex)
0x9996  ldarg.3
0x9997  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartGroup(string name, bool firstInstance)
0x999c  ldarg.0
0x999d  ldarg.0
0x999e  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x99a3  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultGaugeStartValueTag()
0x99a8  ldarg.1
0x99a9  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ScaleRange::get_StartValue()
0x99ae  ldarg.3
0x99af  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeInputValue(string defaultTag, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue gaugeInputValue, bool firstInstance)
0x99b4  ldarg.0
0x99b5  ldarg.0
0x99b6  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x99bb  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultGaugeEndValueTag()
0x99c0  ldarg.1
0x99c1  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ScaleRange::get_EndValue()
0x99c6  ldarg.3
0x99c7  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeInputValue(string defaultTag, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue gaugeInputValue, bool firstInstance)
0x99cc  ldarg.0
0x99cd  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x99d2  ldarg.3
0x99d3  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x99d8  ret
```
