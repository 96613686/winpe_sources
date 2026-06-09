# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkLinearPointerCollection

- ea: `0x97a0`
- end: `0x97e8`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkLinearPointerCollection`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x9700`

## callees

- `0x97a0`
- `0x9840`
- `0x9fc0`
- `0xa020`
- `0xa230`

## pseudocode

```c

```

## disassembly

```asm
0x97a0  ldarg.1
0x97a1  brtrue.s loc_97A4
0x97a3  ret
0x97a4  ldarg.0
0x97a5  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x97aa  ldarg.0
0x97ab  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x97b0  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getGaugePointerCollectionTag()
0x97b5  ldarg.2
0x97b6  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartCollection(string name, bool firstInstance)
0x97bb  ldc.i4.0
0x97bc  stloc.0
0x97bd  br.s     loc_97D2
0x97bf  ldarg.0
0x97c0  ldarg.1
0x97c1  ldloc.0
0x97c2  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanelObjectCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.LinearPointer>::get_Item(!!T0)
0x97c7  ldloc.0
0x97c8  ldarg.2
0x97c9  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugePointer(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePointer gaugePointer, int32 gaugePointerIndex, bool firstInstance)
0x97ce  ldloc.0
0x97cf  ldc.i4.1
0x97d0  add
0x97d1  stloc.0
0x97d2  ldloc.0
0x97d3  ldarg.1
0x97d4  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanelObjectCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.LinearPointer>::get_Count()
0x97d9  blt.s    loc_97BF
0x97db  ldarg.0
0x97dc  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x97e1  ldarg.2
0x97e2  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x97e7  ret
```
