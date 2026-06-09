# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeScale

- ea: `0x9700`
- end: `0x9794`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeScale`
- size: `148`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x9660`
- `0x96b0`

## callees

- `0x9700`
- `0x97a0`
- `0x97f0`
- `0x9930`
- `0x9a80`
- `0x9fa0`
- `0xa020`
- `0xa220`
- `0xa2a0`
- `0xa2b0`

## pseudocode

```c

```

## disassembly

```asm
0x9700  ldarg.1
0x9701  brtrue.s loc_9704
0x9703  ret
0x9704  ldarg.0
0x9705  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x970a  ldarg.0
0x970b  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9710  ldarg.2
0x9711  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getGaugeScaleTag(int32 aGaugeScaleIndex)
0x9716  ldarg.3
0x9717  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartGroup(string name, bool firstInstance)
0x971c  ldarg.0
0x971d  ldarg.0
0x971e  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9723  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultGaugeMinimumValueTag()
0x9728  ldarg.1
0x9729  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeScale::get_MinimumValue()
0x972e  ldarg.3
0x972f  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeInputValue(string defaultTag, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue gaugeInputValue, bool firstInstance)
0x9734  ldarg.0
0x9735  ldarg.0
0x9736  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x973b  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultGaugeMaximumValueTag()
0x9740  ldarg.1
0x9741  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeScale::get_MaximumValue()
0x9746  ldarg.3
0x9747  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeInputValue(string defaultTag, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue gaugeInputValue, bool firstInstance)
0x974c  ldarg.1
0x974d  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.LinearScale
0x9752  brfalse.s loc_9768
0x9754  ldarg.0
0x9755  ldarg.1
0x9756  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.LinearScale
0x975b  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.LinearPointerCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.LinearScale::get_GaugePointers()
0x9760  ldarg.3
0x9761  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkLinearPointerCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.LinearPointerCollection linearPointerCollection, bool firstInstance)
0x9766  br.s     loc_977A
0x9768  ldarg.0
0x9769  ldarg.1
0x976a  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.RadialScale
0x976f  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.RadialPointerCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.RadialScale::get_GaugePointers()
0x9774  ldarg.3
0x9775  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkRadialPointerCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.RadialPointerCollection radialPointerCollection, bool firstInstance)
0x977a  ldarg.0
0x977b  ldarg.1
0x977c  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ScaleRangeCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeScale::get_ScaleRanges()
0x9781  ldarg.3
0x9782  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeScaleRangeCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ScaleRangeCollection scaleRangeCollection, bool firstInstance)
0x9787  ldarg.0
0x9788  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x978d  ldarg.3
0x978e  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x9793  ret
```
