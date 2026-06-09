# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::OnMapMemberBegin

- ea: `0x18d0`
- end: `0x191c`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::OnMapMemberBegin`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1000`
- `0x18d0`
- `0x35f0`
- `0x5270`
- `0x52e0`
- `0x5660`

## pseudocode

```c

```

## disassembly

```asm
0x18d0  ldarg.0
0x18d1  ldarg.1
0x18d2  ldarg.2
0x18d3  ldarg.3
0x18d4  ldarg.s  4
0x18d6  ldarg.s  5
0x18d8  ldarg.s  6
0x18da  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnMapMemberBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapMember mapMember, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapSpatialElementTemplate template, bool outputMapMemberLabel, bool outputDynamicMembers, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapVectorLayer layer, bool& walkMapMember)
0x18df  ldarg.1
0x18e0  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_Group()
0x18e5  brfalse.s loc_18F6
0x18e7  ldarg.s  6
0x18e9  ldarg.0
0x18ea  ldarg.1
0x18eb  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_DefinitionPath()
0x18f0  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::IsPartOfDefinitionPathSteps(string definitionPath)
0x18f5  stind.i1
0x18f6  ldarg.s  6
0x18f8  ldind.u1
0x18f9  brfalse.s loc_191B
0x18fb  ldarg.3
0x18fc  brfalse.s loc_191B
0x18fe  ldarg.0
0x18ff  ldarg.s  5
0x1901  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetLayerName(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapVectorLayer layer)
0x1906  stloc.0
0x1907  ldarg.0
0x1908  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0x190d  ldarg.0
0x190e  ldarg.2
0x190f  ldloc.0
0x1910  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetMapMemberColumnName(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapSpatialElementTemplate template, string layerName)
0x1915  ldarg.1
0x1916  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::AddColumnName(string columnName, object source)
0x191b  ret
```
