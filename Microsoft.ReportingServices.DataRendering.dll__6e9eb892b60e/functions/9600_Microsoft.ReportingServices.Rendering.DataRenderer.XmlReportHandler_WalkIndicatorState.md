# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkIndicatorState

- ea: `0x9600`
- end: `0x9655`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkIndicatorState`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x95b0`

## callees

- `0x9a80`
- `0x9fa0`
- `0xa020`
- `0xa200`
- `0xa280`
- `0xa290`

## pseudocode

```c

```

## disassembly

```asm
0x9600  ldarg.0
0x9601  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9606  ldarg.0
0x9607  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x960c  ldarg.2
0x960d  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getIndicatorStateTag(int32 index)
0x9612  ldarg.3
0x9613  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartGroup(string name, bool firstInstance)
0x9618  ldarg.0
0x9619  ldarg.0
0x961a  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x961f  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultGaugeStartValueTag()
0x9624  ldarg.1
0x9625  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.IndicatorState::get_StartValue()
0x962a  ldarg.3
0x962b  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeInputValue(string defaultTag, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue gaugeInputValue, bool firstInstance)
0x9630  ldarg.0
0x9631  ldarg.0
0x9632  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9637  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultGaugeEndValueTag()
0x963c  ldarg.1
0x963d  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.IndicatorState::get_EndValue()
0x9642  ldarg.3
0x9643  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeInputValue(string defaultTag, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue gaugeInputValue, bool firstInstance)
0x9648  ldarg.0
0x9649  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x964e  ldarg.3
0x964f  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x9654  ret
```
