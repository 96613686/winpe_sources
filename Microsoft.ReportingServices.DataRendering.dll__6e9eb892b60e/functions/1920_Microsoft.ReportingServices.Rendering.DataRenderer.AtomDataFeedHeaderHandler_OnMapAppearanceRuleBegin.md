# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::OnMapAppearanceRuleBegin

- ea: `0x1920`
- end: `0x196d`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::OnMapAppearanceRuleBegin`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1920`
- `0x35e0`
- `0x52c0`
- `0x5300`
- `0x5680`

## pseudocode

```c

```

## disassembly

```asm
0x1920  ldarg.0
0x1921  ldarg.1
0x1922  ldarg.2
0x1923  ldarg.3
0x1924  ldarg.s  4
0x1926  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnMapAppearanceRuleBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapAppearanceRule mapRule, bool outputMapRule, int32& index, bool& walkRule)
0x192b  ldarg.s  4
0x192d  ldind.u1
0x192e  brfalse.s loc_196C
0x1930  ldarg.1
0x1931  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapAppearanceRule::get_DataElementName()
0x1936  stloc.0
0x1937  ldsfld   string [mscorlib]System.String::Empty
0x193c  stloc.1
0x193d  ldarg.0
0x193e  ldarg.1
0x193f  ldloca.s 1
0x1941  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetMapRuleDataValue(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapAppearanceRule mapRule, [out] string& ruleValue)
0x1946  brtrue.s loc_1949
0x1948  ret
0x1949  ldloc.0
0x194a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x194f  brfalse.s loc_1960
0x1951  ldarg.0
0x1952  ldarg.3
0x1953  ldind.i4
0x1954  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetMapRuleColName(int32 index)
0x1959  stloc.0
0x195a  ldarg.3
0x195b  ldarg.3
0x195c  ldind.i4
0x195d  ldc.i4.1
0x195e  add
0x195f  stind.i4
0x1960  ldarg.0
0x1961  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0x1966  ldloc.0
0x1967  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::AddColumnName(string columnName)
0x196c  ret
```
