# Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnChartBegin

- ea: `0x24f0`
- end: `0x2516`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnChartBegin`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x29e0`

## callees

- `0x23f0`
- `0x24f0`
- `0x5530`

## pseudocode

```c

```

## disassembly

```asm
0x24f0  ldarg.0
0x24f1  ldarg.1
0x24f2  ldarg.2
0x24f3  ldarg.3
0x24f4  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnChartBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart chart, bool outputChart, bool& walkChart)
0x24f9  ldarg.3
0x24fa  ldind.u1
0x24fb  brfalse.s loc_2515
0x24fd  ldarg.0
0x24fe  ldarg.1
0x24ff  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_DefinitionPath()
0x2504  ldarg.1
0x2505  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementName()
0x250a  ldarg.1
0x250b  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Name()
0x2510  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnDynamicMemberBegin(string definitionPath, string dataElementName, string reportItemName)
0x2515  ret
```
