# Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnMapBegin

- ea: `0x2600`
- end: `0x2626`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnMapBegin`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x23f0`
- `0x2600`
- `0x5610`

## pseudocode

```c

```

## disassembly

```asm
0x2600  ldarg.0
0x2601  ldarg.1
0x2602  ldarg.2
0x2603  ldarg.3
0x2604  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnMapBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Map map, bool outputMap, bool& walkMap)
0x2609  ldarg.3
0x260a  ldind.u1
0x260b  brfalse.s loc_2625
0x260d  ldarg.0
0x260e  ldarg.1
0x260f  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_DefinitionPath()
0x2614  ldarg.1
0x2615  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementName()
0x261a  ldarg.1
0x261b  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Name()
0x2620  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnDynamicMemberBegin(string definitionPath, string dataElementName, string reportItemName)
0x2625  ret
```
