# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::OnGaugeInputValueBegin

- ea: `0x18a0`
- end: `0x18d0`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::OnGaugeInputValueBegin`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18a0`
- `0x35e0`
- `0x55f0`

## pseudocode

```c

```

## disassembly

```asm
0x18a0  ldarg.0
0x18a1  ldarg.1
0x18a2  ldarg.2
0x18a3  ldarg.3
0x18a4  ldarg.s  4
0x18a6  ldarg.s  5
0x18a8  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnGaugeInputValueBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue gaugeInputValue, string defaultGaugeInputValueColName, bool output, object value, bool& walkThisGaugeInputValue)
0x18ad  ldarg.s  5
0x18af  ldind.u1
0x18b0  brfalse.s loc_18CF
0x18b2  ldarg.1
0x18b3  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue::get_DataElementName()
0x18b8  stloc.0
0x18b9  ldloc.0
0x18ba  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x18bf  brfalse.s loc_18C3
0x18c1  ldarg.2
0x18c2  stloc.0
0x18c3  ldarg.0
0x18c4  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0x18c9  ldloc.0
0x18ca  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::AddColumnName(string columnName)
0x18cf  ret
```
