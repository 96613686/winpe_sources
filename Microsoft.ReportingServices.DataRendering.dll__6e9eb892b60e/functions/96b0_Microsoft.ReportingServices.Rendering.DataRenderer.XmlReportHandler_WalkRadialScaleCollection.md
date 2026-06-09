# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkRadialScaleCollection

- ea: `0x96b0`
- end: `0x96f8`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkRadialScaleCollection`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x94e0`

## callees

- `0x96b0`
- `0x9700`
- `0x9fc0`
- `0xa020`
- `0xa210`

## pseudocode

```c

```

## disassembly

```asm
0x96b0  ldarg.1
0x96b1  brtrue.s loc_96B4
0x96b3  ret
0x96b4  ldarg.0
0x96b5  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x96ba  ldarg.0
0x96bb  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x96c0  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getGaugeScaleCollectionTag()
0x96c5  ldarg.2
0x96c6  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartCollection(string name, bool firstInstance)
0x96cb  ldc.i4.0
0x96cc  stloc.0
0x96cd  br.s     loc_96E2
0x96cf  ldarg.0
0x96d0  ldarg.1
0x96d1  ldloc.0
0x96d2  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanelObjectCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.RadialScale>::get_Item(!!T0)
0x96d7  ldloc.0
0x96d8  ldarg.2
0x96d9  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeScale(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeScale gaugeScale, int32 gaugeScaleIndex, bool firstInstance)
0x96de  ldloc.0
0x96df  ldc.i4.1
0x96e0  add
0x96e1  stloc.0
0x96e2  ldloc.0
0x96e3  ldarg.1
0x96e4  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanelObjectCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.RadialScale>::get_Count()
0x96e9  blt.s    loc_96CF
0x96eb  ldarg.0
0x96ec  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x96f1  ldarg.2
0x96f2  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x96f7  ret
```
