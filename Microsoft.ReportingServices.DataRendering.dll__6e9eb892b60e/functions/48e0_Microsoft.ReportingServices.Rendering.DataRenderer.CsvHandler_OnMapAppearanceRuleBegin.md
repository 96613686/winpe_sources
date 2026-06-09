# Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::OnMapAppearanceRuleBegin

- ea: `0x48e0`
- end: `0x4926`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::OnMapAppearanceRuleBegin`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x48e0`
- `0x4f50`
- `0x5300`
- `0x5680`

## pseudocode

```c

```

## disassembly

```asm
0x48e0  ldarg.0
0x48e1  ldarg.1
0x48e2  ldarg.2
0x48e3  ldarg.3
0x48e4  ldarg.s  4
0x48e6  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnMapAppearanceRuleBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapAppearanceRule mapRule, bool outputMapRule, int32& index, bool& walkRule)
0x48eb  ldarg.s  4
0x48ed  ldind.u1
0x48ee  brfalse.s loc_4925
0x48f0  ldarg.0
0x48f1  ldarg.0
0x48f2  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x48f7  ldc.i4.1
0x48f8  add
0x48f9  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x48fe  ldsfld   string [mscorlib]System.String::Empty
0x4903  stloc.0
0x4904  ldarg.2
0x4905  brfalse.s loc_4913
0x4907  ldarg.0
0x4908  ldarg.1
0x4909  ldloca.s 0
0x490b  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetMapRuleDataValue(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapAppearanceRule mapRule, [out] string& ruleValue)
0x4910  brtrue.s loc_4913
0x4912  ret
0x4913  ldarg.0
0x4914  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_visitor
0x4919  ldloc.0
0x491a  ldarg.0
0x491b  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_stackedMode
0x4920  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::WriteValue(string unformattedValue, bool excelMode)
0x4925  ret
```
