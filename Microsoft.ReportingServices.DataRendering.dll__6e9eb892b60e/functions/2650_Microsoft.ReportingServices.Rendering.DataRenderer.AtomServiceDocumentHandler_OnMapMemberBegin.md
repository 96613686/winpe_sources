# Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnMapMemberBegin

- ea: `0x2650`
- end: `0x2686`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnMapMemberBegin`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x23f0`
- `0x2650`
- `0x5660`

## pseudocode

```c

```

## disassembly

```asm
0x2650  ldarg.0
0x2651  ldarg.1
0x2652  ldarg.2
0x2653  ldarg.3
0x2654  ldarg.s  4
0x2656  ldarg.s  5
0x2658  ldarg.s  6
0x265a  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnMapMemberBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapMember mapMember, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapSpatialElementTemplate template, bool outputMapMemberLabel, bool outputDynamicMembers, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapVectorLayer layer, bool& walkMapMember)
0x265f  ldarg.1
0x2660  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_Group()
0x2665  brfalse.s loc_2685
0x2667  ldarg.0
0x2668  ldarg.1
0x2669  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_DefinitionPath()
0x266e  ldarg.s  5
0x2670  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapVectorLayer::get_MapDataRegionName()
0x2675  ldarg.1
0x2676  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_Group()
0x267b  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group::get_Name()
0x2680  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnDynamicMemberBegin(string definitionPath, string dataElementName, string reportItemName)
0x2685  ret
```
