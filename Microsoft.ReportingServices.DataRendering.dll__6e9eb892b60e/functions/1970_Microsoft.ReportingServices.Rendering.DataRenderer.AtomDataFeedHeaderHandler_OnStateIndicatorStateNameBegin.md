# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::OnStateIndicatorStateNameBegin

- ea: `0x1970`
- end: `0x199e`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::OnStateIndicatorStateNameBegin`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1970`
- `0x35e0`
- `0x56b0`

## pseudocode

```c

```

## disassembly

```asm
0x1970  ldarg.0
0x1971  ldarg.1
0x1972  ldarg.2
0x1973  ldarg.3
0x1974  ldarg.s  4
0x1976  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnStateIndicatorStateNameBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.StateIndicator stateIndicator, string defaultStateIndicatorStateNameColName, bool output, bool& walkThisStateName)
0x197b  ldarg.s  4
0x197d  ldind.u1
0x197e  brfalse.s loc_199D
0x1980  ldarg.1
0x1981  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.StateIndicator::get_StateDataElementName()
0x1986  stloc.0
0x1987  ldloc.0
0x1988  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x198d  brfalse.s loc_1991
0x198f  ldarg.2
0x1990  stloc.0
0x1991  ldarg.0
0x1992  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0x1997  ldloc.0
0x1998  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::AddColumnName(string columnName)
0x199d  ret
```
