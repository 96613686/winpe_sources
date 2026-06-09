# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeScaleRangeCollection

- ea: `0x9930`
- end: `0x9978`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeScaleRangeCollection`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x9700`

## callees

- `0x9930`
- `0x9980`
- `0x9fc0`
- `0xa020`
- `0xa260`

## pseudocode

```c

```

## disassembly

```asm
0x9930  ldarg.1
0x9931  brtrue.s loc_9934
0x9933  ret
0x9934  ldarg.0
0x9935  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x993a  ldarg.0
0x993b  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9940  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getGaugeScaleRangeCollectionTag()
0x9945  ldarg.2
0x9946  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartCollection(string name, bool firstInstance)
0x994b  ldc.i4.0
0x994c  stloc.0
0x994d  br.s     loc_9962
0x994f  ldarg.0
0x9950  ldarg.1
0x9951  ldloc.0
0x9952  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanelObjectCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ScaleRange>::get_Item(!!T0)
0x9957  ldloc.0
0x9958  ldarg.2
0x9959  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeScaleRange(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ScaleRange scaleRange, int32 scaleRangeIndex, bool firstInstance)
0x995e  ldloc.0
0x995f  ldc.i4.1
0x9960  add
0x9961  stloc.0
0x9962  ldloc.0
0x9963  ldarg.1
0x9964  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanelObjectCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ScaleRange>::get_Count()
0x9969  blt.s    loc_994F
0x996b  ldarg.0
0x996c  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9971  ldarg.2
0x9972  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x9977  ret
```
