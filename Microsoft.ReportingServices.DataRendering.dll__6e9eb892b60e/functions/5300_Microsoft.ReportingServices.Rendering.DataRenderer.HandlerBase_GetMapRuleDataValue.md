# Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetMapRuleDataValue

- ea: `0x5300`
- end: `0x536c`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetMapRuleDataValue`
- size: `108`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1630`
- `0x1920`
- `0x4330`
- `0x48e0`

## callees

- `0x5300`

## pseudocode

```c

```

## disassembly

```asm
0x5300  ldarg.1
0x5301  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapAppearanceRule::get_DataValue()
0x5306  stloc.0
0x5307  ldnull
0x5308  stloc.1
0x5309  ldarg.2
0x530a  ldsfld   string [mscorlib]System.String::Empty
0x530f  stind.ref
0x5310  ldloc.0
0x5311  brfalse.s loc_5338
0x5313  ldloc.0
0x5314  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportProperty::get_IsExpression()
0x5319  brfalse.s loc_5331
0x531b  ldarg.1
0x531c  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapAppearanceRuleInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapAppearanceRule::get_Instance()
0x5321  brfalse.s loc_5338
0x5323  ldarg.1
0x5324  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapAppearanceRuleInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapAppearanceRule::get_Instance()
0x5329  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapAppearanceRuleInstance::get_DataValue()
0x532e  stloc.1
0x532f  br.s     loc_5338
0x5331  ldloc.0
0x5332  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty::get_Value()
0x5337  stloc.1
0x5338  ldloc.1
0x5339  brfalse.s loc_534D
0x533b  ldarg.2
0x533c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5341  ldstr    a0// "{0}"
0x5346  ldloc.1
0x5347  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x534c  stind.ref
0x534d  ldloc.1
0x534e  isinst   [mscorlib]System.String
0x5353  brfalse.s loc_536A
0x5355  ldloc.1
0x5356  castclass [mscorlib]System.String
0x535b  ldstr    asc_F6A2// "#"
0x5360  ldc.i4.4
0x5361  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x5366  brfalse.s loc_536A
0x5368  ldc.i4.0
0x5369  ret
0x536a  ldc.i4.1
0x536b  ret
```
