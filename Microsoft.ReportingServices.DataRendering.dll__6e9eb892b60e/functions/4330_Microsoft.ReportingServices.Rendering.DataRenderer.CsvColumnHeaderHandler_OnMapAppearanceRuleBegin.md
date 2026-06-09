# Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::OnMapAppearanceRuleBegin

- ea: `0x4330`
- end: `0x4399`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::OnMapAppearanceRuleBegin`
- size: `105`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x4330`
- `0x4f50`
- `0x52c0`
- `0x5300`
- `0x5680`

## pseudocode

```c

```

## disassembly

```asm
0x4330  ldarg.0
0x4331  ldarg.1
0x4332  ldarg.2
0x4333  ldarg.3
0x4334  ldarg.s  4
0x4336  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnMapAppearanceRuleBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapAppearanceRule mapRule, bool outputMapRule, int32& index, bool& walkRule)
0x433b  ldarg.s  4
0x433d  ldind.u1
0x433e  brfalse.s loc_4398
0x4340  ldarg.0
0x4341  ldarg.0
0x4342  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::m_columnsNum
0x4347  ldc.i4.1
0x4348  add
0x4349  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::m_columnsNum
0x434e  ldarg.0
0x434f  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::m_noHeaders
0x4354  brtrue.s loc_4398
0x4356  ldsfld   string [mscorlib]System.String::Empty
0x435b  stloc.0
0x435c  ldarg.0
0x435d  ldarg.1
0x435e  ldloca.s 0
0x4360  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetMapRuleDataValue(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapAppearanceRule mapRule, [out] string& ruleValue)
0x4365  brtrue.s loc_4368
0x4367  ret
0x4368  ldarg.1
0x4369  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapAppearanceRule::get_DataElementName()
0x436e  stloc.1
0x436f  ldloc.1
0x4370  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4375  brfalse.s loc_4386
0x4377  ldarg.0
0x4378  ldarg.3
0x4379  ldind.i4
0x437a  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetMapRuleColName(int32 index)
0x437f  stloc.1
0x4380  ldarg.3
0x4381  ldarg.3
0x4382  ldind.i4
0x4383  ldc.i4.1
0x4384  add
0x4385  stind.i4
0x4386  ldarg.0
0x4387  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::m_visitor
0x438c  ldloc.1
0x438d  ldarg.0
0x438e  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::m_excelMode
0x4393  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::WriteValue(string unformattedValue, bool excelMode)
0x4398  ret
```
