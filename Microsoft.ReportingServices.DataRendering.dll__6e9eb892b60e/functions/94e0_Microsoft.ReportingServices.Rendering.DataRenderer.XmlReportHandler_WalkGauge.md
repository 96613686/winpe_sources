# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGauge

- ea: `0x94e0`
- end: `0x9537`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGauge`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x93e0`

## callees

- `0x94e0`
- `0x9660`
- `0x96b0`
- `0x9fa0`
- `0xa020`
- `0xa1c0`

## pseudocode

```c

```

## disassembly

```asm
0x94e0  ldarg.1
0x94e1  brtrue.s loc_94E4
0x94e3  ret
0x94e4  ldarg.0
0x94e5  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x94ea  ldarg.0
0x94eb  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x94f0  ldarg.2
0x94f1  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getGaugeTag(int32 aGaugeIndex)
0x94f6  ldarg.3
0x94f7  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartGroup(string name, bool firstInstance)
0x94fc  ldarg.1
0x94fd  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.LinearGauge
0x9502  brfalse.s loc_9518
0x9504  ldarg.0
0x9505  ldarg.1
0x9506  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.LinearGauge
0x950b  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.LinearScaleCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.LinearGauge::get_GaugeScales()
0x9510  ldarg.3
0x9511  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkLinearScaleCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.LinearScaleCollection linearScaleCollection, bool firstInstance)
0x9516  br.s     loc_952A
0x9518  ldarg.0
0x9519  ldarg.1
0x951a  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.RadialGauge
0x951f  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.RadialScaleCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.RadialGauge::get_GaugeScales()
0x9524  ldarg.3
0x9525  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkRadialScaleCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.RadialScaleCollection radialScaleCollection, bool firstInstance)
0x952a  ldarg.0
0x952b  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9530  ldarg.3
0x9531  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x9536  ret
```
