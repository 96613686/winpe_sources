# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkIndicatorStateCollection

- ea: `0x95b0`
- end: `0x95f4`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkIndicatorStateCollection`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x9540`

## callees

- `0x95b0`
- `0x9600`
- `0x9fc0`
- `0xa020`
- `0xa1f0`

## pseudocode

```c

```

## disassembly

```asm
0x95b0  ldarg.0
0x95b1  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x95b6  ldarg.0
0x95b7  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x95bc  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getIndicatorStateCollectionTag()
0x95c1  ldarg.2
0x95c2  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartCollection(string name, bool firstInstance)
0x95c7  ldc.i4.0
0x95c8  stloc.0
0x95c9  br.s     loc_95DE
0x95cb  ldarg.0
0x95cc  ldarg.1
0x95cd  ldloc.0
0x95ce  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanelObjectCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.IndicatorState>::get_Item(!!T0)
0x95d3  ldloc.0
0x95d4  ldarg.2
0x95d5  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkIndicatorState(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.IndicatorState indicatorState, int32 indicatorStateIndex, bool firstInstance)
0x95da  ldloc.0
0x95db  ldc.i4.1
0x95dc  add
0x95dd  stloc.0
0x95de  ldloc.0
0x95df  ldarg.1
0x95e0  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanelObjectCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.IndicatorState>::get_Count()
0x95e5  blt.s    loc_95CB
0x95e7  ldarg.0
0x95e8  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x95ed  ldarg.2
0x95ee  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x95f3  ret
```
