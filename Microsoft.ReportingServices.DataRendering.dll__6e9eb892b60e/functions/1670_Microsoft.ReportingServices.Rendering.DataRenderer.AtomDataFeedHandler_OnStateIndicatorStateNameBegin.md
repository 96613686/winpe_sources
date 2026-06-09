# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::OnStateIndicatorStateNameBegin

- ea: `0x1670`
- end: `0x16ac`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::OnStateIndicatorStateNameBegin`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x11e0`
- `0x1670`
- `0x3370`
- `0x56b0`

## pseudocode

```c

```

## disassembly

```asm
0x1670  ldarg.0
0x1671  ldarg.1
0x1672  ldarg.2
0x1673  ldarg.3
0x1674  ldarg.s  4
0x1676  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnStateIndicatorStateNameBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.StateIndicator stateIndicator, string defaultStateIndicatorStateNameColName, bool output, bool& walkThisStateName)
0x167b  ldarg.s  4
0x167d  ldind.u1
0x167e  brfalse.s loc_16AB
0x1680  ldsfld   string [mscorlib]System.String::Empty
0x1685  stloc.0
0x1686  ldarg.3
0x1687  brfalse.s loc_169D
0x1689  ldarg.1
0x168a  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.StateIndicator::get_CompiledStateName()
0x168f  brfalse.s loc_169D
0x1691  ldarg.1
0x1692  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.StateIndicator::get_CompiledStateName()
0x1697  call     string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::XmlConvertOrginalValue(object value)
0x169c  stloc.0
0x169d  ldarg.0
0x169e  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0x16a3  ldloc.0
0x16a4  ldc.i4.s 0x12
0x16a6  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteValue(string value, valuetype [mscorlib]System.TypeCode typeCode)
0x16ab  ret
```
