# Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnGaugePanelBegin

- ea: `0x25b0`
- end: `0x25d6`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnGaugePanelBegin`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x23f0`
- `0x25b0`
- `0x55d0`

## pseudocode

```c

```

## disassembly

```asm
0x25b0  ldarg.0
0x25b1  ldarg.1
0x25b2  ldarg.2
0x25b3  ldarg.3
0x25b4  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnGaugePanelBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanel gaugePanel, bool outputGaugePanelData, bool& walkGaugePanel)
0x25b9  ldarg.3
0x25ba  ldind.u1
0x25bb  brfalse.s loc_25D5
0x25bd  ldarg.0
0x25be  ldarg.1
0x25bf  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_DefinitionPath()
0x25c4  ldarg.1
0x25c5  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementName()
0x25ca  ldarg.1
0x25cb  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Name()
0x25d0  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnDynamicMemberBegin(string definitionPath, string dataElementName, string reportItemName)
0x25d5  ret
```
