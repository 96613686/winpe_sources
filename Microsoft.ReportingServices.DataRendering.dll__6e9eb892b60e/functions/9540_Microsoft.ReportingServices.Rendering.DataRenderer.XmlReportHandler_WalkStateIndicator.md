# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkStateIndicator

- ea: `0x9540`
- end: `0x95a5`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkStateIndicator`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x93e0`

## callees

- `0x9540`
- `0x95b0`
- `0x99e0`
- `0x9a80`
- `0x9fa0`
- `0xa020`
- `0xa1d0`
- `0xa1e0`
- `0xa250`

## pseudocode

```c

```

## disassembly

```asm
0x9540  ldarg.0
0x9541  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9546  ldarg.0
0x9547  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x954c  ldarg.2
0x954d  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getStateIndicatorTag(int32 index)
0x9552  ldarg.3
0x9553  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartGroup(string name, bool firstInstance)
0x9558  ldarg.0
0x9559  ldarg.0
0x955a  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x955f  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultStateNameTag()
0x9564  ldarg.1
0x9565  ldarg.3
0x9566  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkStateIndicatorName(string defaultTag, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.StateIndicator stateIndicator, bool firstInstance)
0x956b  ldarg.0
0x956c  ldarg.0
0x956d  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9572  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultGaugeInputValueTag()
0x9577  ldarg.1
0x9578  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.StateIndicator::get_GaugeInputValue()
0x957d  ldarg.3
0x957e  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeInputValue(string defaultTag, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue gaugeInputValue, bool firstInstance)
0x9583  ldarg.1
0x9584  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.IndicatorStateCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.StateIndicator::get_IndicatorStates()
0x9589  brfalse.s loc_9598
0x958b  ldarg.0
0x958c  ldarg.1
0x958d  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.IndicatorStateCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.StateIndicator::get_IndicatorStates()
0x9592  ldarg.3
0x9593  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkIndicatorStateCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.IndicatorStateCollection indicatorStateCollection, bool firstInstance)
0x9598  ldarg.0
0x9599  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x959e  ldarg.3
0x959f  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x95a4  ret
```
