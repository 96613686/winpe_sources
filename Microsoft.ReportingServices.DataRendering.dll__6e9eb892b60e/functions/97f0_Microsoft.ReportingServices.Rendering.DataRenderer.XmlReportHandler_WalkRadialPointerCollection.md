# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkRadialPointerCollection

- ea: `0x97f0`
- end: `0x9838`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkRadialPointerCollection`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x9700`

## callees

- `0x97f0`
- `0x9840`
- `0x9fc0`
- `0xa020`
- `0xa230`

## pseudocode

```c

```

## disassembly

```asm
0x97f0  ldarg.1
0x97f1  brtrue.s loc_97F4
0x97f3  ret
0x97f4  ldarg.0
0x97f5  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x97fa  ldarg.0
0x97fb  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9800  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getGaugePointerCollectionTag()
0x9805  ldarg.2
0x9806  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartCollection(string name, bool firstInstance)
0x980b  ldc.i4.0
0x980c  stloc.0
0x980d  br.s     loc_9822
0x980f  ldarg.0
0x9810  ldarg.1
0x9811  ldloc.0
0x9812  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanelObjectCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.RadialPointer>::get_Item(!!T0)
0x9817  ldloc.0
0x9818  ldarg.2
0x9819  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugePointer(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePointer gaugePointer, int32 gaugePointerIndex, bool firstInstance)
0x981e  ldloc.0
0x981f  ldc.i4.1
0x9820  add
0x9821  stloc.0
0x9822  ldloc.0
0x9823  ldarg.1
0x9824  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanelObjectCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.RadialPointer>::get_Count()
0x9829  blt.s    loc_980F
0x982b  ldarg.0
0x982c  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9831  ldarg.2
0x9832  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x9837  ret
```
