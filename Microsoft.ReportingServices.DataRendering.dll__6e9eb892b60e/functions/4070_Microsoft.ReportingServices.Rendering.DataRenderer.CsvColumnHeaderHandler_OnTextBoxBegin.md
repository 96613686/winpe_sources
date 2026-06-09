# Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::OnTextBoxBegin

- ea: `0x4070`
- end: `0x40c3`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::OnTextBoxBegin`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x4030`
- `0x4050`
- `0x4060`
- `0x4070`
- `0x4f50`

## pseudocode

```c

```

## disassembly

```asm
0x4070  ldarg.1
0x4071  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementOutput()
0x4076  ldc.i4.1
0x4077  bne.un.s loc_407A
0x4079  ret
0x407a  ldarg.3
0x407b  ldc.i4.1
0x407c  stind.i1
0x407d  ldarg.0
0x407e  ldarg.0
0x407f  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::m_columnsNum
0x4084  ldc.i4.1
0x4085  add
0x4086  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::m_columnsNum
0x408b  ldarg.0
0x408c  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::get_HeaderOnlyMode()
0x4091  brfalse.s loc_40A3
0x4093  ldarg.0
0x4094  call     instance int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::get_HeaderOnlyColumns()
0x4099  stloc.0
0x409a  ldarg.0
0x409b  ldloc.0
0x409c  ldc.i4.1
0x409d  add
0x409e  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::set_HeaderOnlyColumns(int32 value)
0x40a3  ldarg.0
0x40a4  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::m_noHeaders
0x40a9  brtrue.s loc_40C2
0x40ab  ldarg.0
0x40ac  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::m_visitor
0x40b1  ldarg.1
0x40b2  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementName()
0x40b7  ldarg.0
0x40b8  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::m_excelMode
0x40bd  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::WriteValue(string unformattedValue, bool excelMode)
0x40c2  ret
```
