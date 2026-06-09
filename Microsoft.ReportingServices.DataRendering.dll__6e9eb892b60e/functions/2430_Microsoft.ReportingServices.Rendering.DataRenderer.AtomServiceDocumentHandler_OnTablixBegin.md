# Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnTablixBegin

- ea: `0x2430`
- end: `0x2456`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnTablixBegin`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x23f0`
- `0x2430`
- `0x54b0`

## pseudocode

```c

```

## disassembly

```asm
0x2430  ldarg.0
0x2431  ldarg.1
0x2432  ldarg.2
0x2433  ldarg.3
0x2434  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnTablixBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix tablix, bool& walkTablix, bool outputTablix)
0x2439  ldarg.2
0x243a  ldind.u1
0x243b  brfalse.s loc_2455
0x243d  ldarg.0
0x243e  ldarg.1
0x243f  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_DefinitionPath()
0x2444  ldarg.1
0x2445  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementName()
0x244a  ldarg.1
0x244b  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Name()
0x2450  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnDynamicMemberBegin(string definitionPath, string dataElementName, string reportItemName)
0x2455  ret
```
