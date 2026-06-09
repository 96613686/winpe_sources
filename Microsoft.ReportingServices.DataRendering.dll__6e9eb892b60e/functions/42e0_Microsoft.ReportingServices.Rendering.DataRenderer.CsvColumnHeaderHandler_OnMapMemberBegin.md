# Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::OnMapMemberBegin

- ea: `0x42e0`
- end: `0x432b`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::OnMapMemberBegin`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x42e0`
- `0x4f50`
- `0x5270`
- `0x52e0`
- `0x5660`

## pseudocode

```c

```

## disassembly

```asm
0x42e0  ldarg.0
0x42e1  ldarg.1
0x42e2  ldarg.2
0x42e3  ldarg.3
0x42e4  ldarg.s  4
0x42e6  ldarg.s  5
0x42e8  ldarg.s  6
0x42ea  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnMapMemberBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapMember mapMember, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapSpatialElementTemplate template, bool outputMapMemberLabel, bool outputDynamicMembers, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapVectorLayer layer, bool& walkMapMember)
0x42ef  ldarg.3
0x42f0  brfalse.s loc_432A
0x42f2  ldarg.0
0x42f3  ldarg.0
0x42f4  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::m_columnsNum
0x42f9  ldc.i4.1
0x42fa  add
0x42fb  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::m_columnsNum
0x4300  ldarg.0
0x4301  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::m_noHeaders
0x4306  brtrue.s loc_432A
0x4308  ldarg.0
0x4309  ldarg.s  5
0x430b  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetLayerName(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapVectorLayer layer)
0x4310  stloc.0
0x4311  ldarg.0
0x4312  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::m_visitor
0x4317  ldarg.0
0x4318  ldarg.2
0x4319  ldloc.0
0x431a  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetMapMemberColumnName(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapSpatialElementTemplate template, string layerName)
0x431f  ldarg.0
0x4320  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::m_excelMode
0x4325  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::WriteValue(string unformattedValue, bool excelMode)
0x432a  ret
```
