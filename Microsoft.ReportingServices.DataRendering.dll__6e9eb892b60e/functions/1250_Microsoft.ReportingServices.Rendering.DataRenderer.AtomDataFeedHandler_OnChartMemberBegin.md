# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::OnChartMemberBegin

- ea: `0x1250`
- end: `0x12d8`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::OnChartMemberBegin`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1000`
- `0x1040`
- `0x1250`
- `0x3370`
- `0x5550`

## pseudocode

```c

```

## disassembly

```asm
0x1250  ldarg.s  5
0x1252  ldind.u1
0x1253  stloc.0
0x1254  ldloc.0
0x1255  brtrue.s loc_1264
0x1257  ldarg.0
0x1258  ldarg.1
0x1259  ldarg.2
0x125a  ldarg.3
0x125b  ldarg.s  4
0x125d  ldarg.s  5
0x125f  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnChartMemberBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember chartMember, bool outputThisMember, bool outputMemberLabelColumn, string parentScopeName, bool& walkThisMember)
0x1264  ldarg.s  5
0x1266  ldind.u1
0x1267  brfalse.s loc_12D7
0x1269  ldarg.1
0x126a  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_Group()
0x126f  brfalse.s loc_1295
0x1271  ldarg.1
0x1272  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember::get_IsCategory()
0x1277  brfalse.s loc_1295
0x1279  ldloc.0
0x127a  brtrue.s loc_128B
0x127c  ldarg.s  5
0x127e  ldarg.0
0x127f  ldarg.1
0x1280  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_DefinitionPath()
0x1285  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::IsPartOfDefinitionPathSteps(string definitionPath)
0x128a  stind.i1
0x128b  ldarg.0
0x128c  ldarg.s  5
0x128e  ldind.u1
0x128f  ldarg.2
0x1290  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::ValidateCurrentRow(bool walk, bool output)
0x1295  ldarg.s  5
0x1297  ldind.u1
0x1298  brfalse.s loc_12D7
0x129a  ldarg.3
0x129b  brfalse.s loc_12D7
0x129d  ldnull
0x129e  stloc.1
0x129f  ldc.i4.s 0x12
0x12a1  stloc.2
0x12a2  ldarg.2
0x12a3  brfalse.s loc_12CA
0x12a5  ldarg.1
0x12a6  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMemberInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember::get_Instance()
0x12ab  stloc.3
0x12ac  ldloc.3
0x12ad  brfalse.s loc_12CA
0x12af  ldloc.3
0x12b0  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMemberInstance::get_Label()
0x12b5  brfalse.s loc_12CA
0x12b7  ldloc.3
0x12b8  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMemberInstance::get_Label()
0x12bd  stloc.1
0x12be  ldloc.3
0x12bf  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMemberInstance::get_Label()
0x12c4  callvirt instance valuetype [mscorlib]System.TypeCode [mscorlib]System.String::GetTypeCode()
0x12c9  stloc.2
0x12ca  ldarg.0
0x12cb  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0x12d0  ldloc.1
0x12d1  ldloc.2
0x12d2  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteValue(string value, valuetype [mscorlib]System.TypeCode typeCode)
0x12d7  ret
```
