# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkLinearScaleCollection

- ea: `0x9660`
- end: `0x96a8`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkLinearScaleCollection`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x94e0`

## callees

- `0x9660`
- `0x9700`
- `0x9fc0`
- `0xa020`
- `0xa210`

## pseudocode

```c

```

## disassembly

```asm
0x9660  ldarg.1
0x9661  brtrue.s loc_9664
0x9663  ret
0x9664  ldarg.0
0x9665  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x966a  ldarg.0
0x966b  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9670  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getGaugeScaleCollectionTag()
0x9675  ldarg.2
0x9676  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartCollection(string name, bool firstInstance)
0x967b  ldc.i4.0
0x967c  stloc.0
0x967d  br.s     loc_9692
0x967f  ldarg.0
0x9680  ldarg.1
0x9681  ldloc.0
0x9682  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanelObjectCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.LinearScale>::get_Item(!!T0)
0x9687  ldloc.0
0x9688  ldarg.2
0x9689  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeScale(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeScale gaugeScale, int32 gaugeScaleIndex, bool firstInstance)
0x968e  ldloc.0
0x968f  ldc.i4.1
0x9690  add
0x9691  stloc.0
0x9692  ldloc.0
0x9693  ldarg.1
0x9694  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanelObjectCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.LinearScale>::get_Count()
0x9699  blt.s    loc_967F
0x969b  ldarg.0
0x969c  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x96a1  ldarg.2
0x96a2  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x96a7  ret
```
