# Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnChartMemberBegin

- ea: `0x2540`
- end: `0x2580`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnChartMemberBegin`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x23f0`
- `0x2540`
- `0x5550`

## pseudocode

```c

```

## disassembly

```asm
0x2540  ldarg.0
0x2541  ldarg.1
0x2542  ldarg.2
0x2543  ldarg.3
0x2544  ldarg.s  4
0x2546  ldarg.s  5
0x2548  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnChartMemberBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember chartMember, bool outputThisMember, bool outputMemberLabelColumn, string parentScopeName, bool& walkThisMember)
0x254d  ldarg.s  5
0x254f  ldind.u1
0x2550  brfalse.s loc_257F
0x2552  ldarg.1
0x2553  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_Group()
0x2558  brfalse.s loc_257F
0x255a  ldarg.1
0x255b  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember::get_IsCategory()
0x2560  brfalse.s loc_257F
0x2562  ldarg.0
0x2563  ldarg.1
0x2564  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_DefinitionPath()
0x2569  ldarg.1
0x256a  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember::get_DataElementName()
0x256f  ldarg.1
0x2570  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_Group()
0x2575  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group::get_Name()
0x257a  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnDynamicMemberBegin(string definitionPath, string dataElementName, string reportItemName)
0x257f  ret
```
