# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::GetColumnMetadata

- ea: `0x36d0`
- end: `0x375c`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::GetColumnMetadata`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x35f0`

## callees

- `0x36d0`
- `0x3fb0`
- `0x3fc0`

## pseudocode

```c

```

## disassembly

```asm
0x36d0  ldarg.1
0x36d1  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBox
0x36d6  stloc.0
0x36d7  ldloc.0
0x36d8  brfalse.s loc_371C
0x36da  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.ColumnMetadata::.ctor()
0x36df  stloc.3
0x36e0  ldloc.3
0x36e1  ldc.i4.0
0x36e2  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.ColumnMetadata::set_IsDynamic(bool value)
0x36e7  ldloc.0
0x36e8  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.IDefinitionPath [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_ParentDefinitionPath()
0x36ed  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHeader
0x36f2  stloc.s  4
0x36f4  ldloc.s  4
0x36f6  brfalse.s loc_371A
0x36f8  ldloc.s  4
0x36fa  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.IDefinitionPath [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHeader::get_ParentDefinitionPath()
0x36ff  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember
0x3704  stloc.s  5
0x3706  ldloc.s  5
0x3708  brfalse.s loc_371A
0x370a  ldloc.3
0x370b  ldloc.s  5
0x370d  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_IsStatic()
0x3712  ldc.i4.0
0x3713  ceq
0x3715  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.ColumnMetadata::set_IsDynamic(bool value)
0x371a  ldloc.3
0x371b  ret
0x371c  ldarg.1
0x371d  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember
0x3722  stloc.1
0x3723  ldloc.1
0x3724  brfalse.s loc_373B
0x3726  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.ColumnMetadata::.ctor()
0x372b  dup
0x372c  ldloc.1
0x372d  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_IsStatic()
0x3732  ldc.i4.0
0x3733  ceq
0x3735  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.ColumnMetadata::set_IsDynamic(bool value)
0x373a  ret
0x373b  ldarg.1
0x373c  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapMember
0x3741  stloc.2
0x3742  ldloc.2
0x3743  brfalse.s loc_375A
0x3745  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.ColumnMetadata::.ctor()
0x374a  dup
0x374b  ldloc.2
0x374c  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_IsStatic()
0x3751  ldc.i4.0
0x3752  ceq
0x3754  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.ColumnMetadata::set_IsDynamic(bool value)
0x3759  ret
0x375a  ldnull
0x375b  ret
```
