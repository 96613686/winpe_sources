# Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnTablixMemberBegin

- ea: `0x2480`
- end: `0x24bb`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnTablixMemberBegin`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x23f0`
- `0x2480`
- `0x54d0`

## pseudocode

```c

```

## disassembly

```asm
0x2480  ldarg.0
0x2481  ldarg.1
0x2482  ldarg.2
0x2483  ldarg.3
0x2484  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnTablixMemberBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember tablixMember, bool& walkThisMember, bool outputThisMember)
0x2489  ldarg.2
0x248a  ldind.u1
0x248b  brfalse.s loc_24BA
0x248d  ldarg.1
0x248e  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_Group()
0x2493  brfalse.s loc_24BA
0x2495  ldarg.1
0x2496  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_IsColumn()
0x249b  brfalse.s loc_24BA
0x249d  ldarg.0
0x249e  ldarg.1
0x249f  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_DefinitionPath()
0x24a4  ldarg.1
0x24a5  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_DataElementName()
0x24aa  ldarg.1
0x24ab  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_Group()
0x24b0  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group::get_Name()
0x24b5  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnDynamicMemberBegin(string definitionPath, string dataElementName, string reportItemName)
0x24ba  ret
```
