# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::OnMapAppearanceRuleBegin

- ea: `0x1630`
- end: `0x1666`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::OnMapAppearanceRuleBegin`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1630`
- `0x3370`
- `0x5300`
- `0x5680`

## pseudocode

```c

```

## disassembly

```asm
0x1630  ldarg.0
0x1631  ldarg.1
0x1632  ldarg.2
0x1633  ldarg.3
0x1634  ldarg.s  4
0x1636  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnMapAppearanceRuleBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapAppearanceRule mapRule, bool outputMapRule, int32& index, bool& walkRule)
0x163b  ldarg.s  4
0x163d  ldind.u1
0x163e  brfalse.s loc_1665
0x1640  ldsfld   string [mscorlib]System.String::Empty
0x1645  stloc.0
0x1646  ldc.i4.s 0x12
0x1648  stloc.1
0x1649  ldarg.2
0x164a  brfalse.s loc_1658
0x164c  ldarg.0
0x164d  ldarg.1
0x164e  ldloca.s 0
0x1650  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetMapRuleDataValue(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapAppearanceRule mapRule, [out] string& ruleValue)
0x1655  brtrue.s loc_1658
0x1657  ret
0x1658  ldarg.0
0x1659  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0x165e  ldloc.0
0x165f  ldloc.1
0x1660  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteValue(string value, valuetype [mscorlib]System.TypeCode typeCode)
0x1665  ret
```
