# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::OnChartMemberBegin

- ea: `0x16f0`
- end: `0x175c`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::OnChartMemberBegin`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1000`
- `0x16f0`
- `0x35f0`
- `0x5550`

## pseudocode

```c

```

## disassembly

```asm
0x16f0  ldarg.s  5
0x16f2  ldind.u1
0x16f3  stloc.0
0x16f4  ldloc.0
0x16f5  brtrue.s loc_1704
0x16f7  ldarg.0
0x16f8  ldarg.1
0x16f9  ldarg.2
0x16fa  ldarg.3
0x16fb  ldarg.s  4
0x16fd  ldarg.s  5
0x16ff  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnChartMemberBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember chartMember, bool outputThisMember, bool outputMemberLabelColumn, string parentScopeName, bool& walkThisMember)
0x1704  ldarg.s  5
0x1706  ldind.u1
0x1707  brfalse.s loc_175B
0x1709  ldarg.1
0x170a  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_Group()
0x170f  brfalse.s loc_172B
0x1711  ldarg.1
0x1712  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember::get_IsCategory()
0x1717  brfalse.s loc_172B
0x1719  ldloc.0
0x171a  brtrue.s loc_172B
0x171c  ldarg.s  5
0x171e  ldarg.0
0x171f  ldarg.1
0x1720  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_DefinitionPath()
0x1725  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::IsPartOfDefinitionPathSteps(string definitionPath)
0x172a  stind.i1
0x172b  ldarg.s  5
0x172d  ldind.u1
0x172e  brfalse.s loc_175B
0x1730  ldarg.3
0x1731  brfalse.s loc_175B
0x1733  ldarg.0
0x1734  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0x1739  ldarg.s  4
0x173b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1740  brtrue.s loc_1750
0x1742  ldarg.s  4
0x1744  ldstr    aLabel// "_label"
0x1749  call     string [mscorlib]System.String::Concat(string, string)
0x174e  br.s     loc_1755
0x1750  ldstr    aLabel_0// "Label"
0x1755  ldarg.1
0x1756  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::AddColumnName(string columnName, object source)
0x175b  ret
```
