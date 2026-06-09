# Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::OnMapMemberBegin

- ea: `0x4890`
- end: `0x48d5`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::OnMapMemberBegin`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x4890`
- `0x4f50`
- `0x5230`
- `0x5660`

## pseudocode

```c

```

## disassembly

```asm
0x4890  ldarg.0
0x4891  ldarg.1
0x4892  ldarg.2
0x4893  ldarg.3
0x4894  ldarg.s  4
0x4896  ldarg.s  5
0x4898  ldarg.s  6
0x489a  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnMapMemberBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapMember mapMember, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapSpatialElementTemplate template, bool outputMapMemberLabel, bool outputDynamicMembers, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapVectorLayer layer, bool& walkMapMember)
0x489f  ldarg.3
0x48a0  brfalse.s loc_48D4
0x48a2  ldarg.0
0x48a3  ldarg.0
0x48a4  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x48a9  ldc.i4.1
0x48aa  add
0x48ab  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x48b0  ldsfld   string [mscorlib]System.String::Empty
0x48b5  stloc.0
0x48b6  ldarg.s  4
0x48b8  brfalse.s loc_48C2
0x48ba  ldarg.0
0x48bb  ldarg.2
0x48bc  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetDataElementLabelValue(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapSpatialElementTemplate template)
0x48c1  stloc.0
0x48c2  ldarg.0
0x48c3  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_visitor
0x48c8  ldloc.0
0x48c9  ldarg.0
0x48ca  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_stackedMode
0x48cf  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::WriteValue(string unformattedValue, bool excelMode)
0x48d4  ret
```
