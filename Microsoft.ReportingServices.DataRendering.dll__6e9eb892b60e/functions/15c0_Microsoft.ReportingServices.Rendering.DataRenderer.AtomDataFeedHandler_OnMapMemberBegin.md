# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::OnMapMemberBegin

- ea: `0x15c0`
- end: `0x1622`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::OnMapMemberBegin`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1000`
- `0x1040`
- `0x15c0`
- `0x3370`
- `0x5230`
- `0x5660`

## pseudocode

```c

```

## disassembly

```asm
0x15c0  ldarg.0
0x15c1  ldarg.1
0x15c2  ldarg.2
0x15c3  ldarg.3
0x15c4  ldarg.s  4
0x15c6  ldarg.s  5
0x15c8  ldarg.s  6
0x15ca  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnMapMemberBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapMember mapMember, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapSpatialElementTemplate template, bool outputMapMemberLabel, bool outputDynamicMembers, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapVectorLayer layer, bool& walkMapMember)
0x15cf  ldarg.1
0x15d0  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_Group()
0x15d5  brfalse.s loc_15F1
0x15d7  ldarg.s  6
0x15d9  ldarg.0
0x15da  ldarg.1
0x15db  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_DefinitionPath()
0x15e0  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::IsPartOfDefinitionPathSteps(string definitionPath)
0x15e5  stind.i1
0x15e6  ldarg.0
0x15e7  ldarg.s  6
0x15e9  ldind.u1
0x15ea  ldarg.s  4
0x15ec  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::ValidateCurrentRow(bool walk, bool output)
0x15f1  ldarg.s  6
0x15f3  ldind.u1
0x15f4  brfalse.s loc_1621
0x15f6  ldarg.3
0x15f7  brfalse.s loc_1621
0x15f9  ldnull
0x15fa  stloc.0
0x15fb  ldc.i4.s 0x12
0x15fd  stloc.1
0x15fe  ldarg.s  4
0x1600  brfalse.s loc_1614
0x1602  ldarg.0
0x1603  ldarg.2
0x1604  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetDataElementLabelValue(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapSpatialElementTemplate template)
0x1609  stloc.0
0x160a  ldloc.0
0x160b  brfalse.s loc_1614
0x160d  ldloc.0
0x160e  callvirt instance valuetype [mscorlib]System.TypeCode [mscorlib]System.String::GetTypeCode()
0x1613  stloc.1
0x1614  ldarg.0
0x1615  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0x161a  ldloc.0
0x161b  ldloc.1
0x161c  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteValue(string value, valuetype [mscorlib]System.TypeCode typeCode)
0x1621  ret
```
