# Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::Initialize

- ea: `0xd0000`
- end: `0xd01ce`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::Initialize`
- size: `462`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0xd0000`
- `0xd09d0`
- `0x117ce0`
- `0x13dfc0`
- `0x150870`
- `0x150890`
- `0x1508b0`
- `0x1508c0`
- `0x1508d0`
- `0x1508e0`
- `0x1508f0`
- `0x150900`
- `0x150910`
- `0x150920`
- `0x150930`
- `0x150940`

## string_xrefs

- `0xd0077`: `AllowUpsideDown`

## pseudocode

```c

```

## disassembly

```asm
0xd0000  ldarga.s 1
0xd0002  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xd0007  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ScaleLabelsStart()
0xd000c  ldarg.0
0xd000d  ldarg.1
0xd000e  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.GaugePanelStyleContainer::Initialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xd0013  ldarg.0
0xd0014  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_interval
0xd0019  brfalse.s loc_D003E
0xd001b  ldarg.0
0xd001c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_interval
0xd0021  ldstr    aInterval// "Interval"
0xd0026  ldarg.1
0xd0027  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xd002c  ldarga.s 1
0xd002e  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xd0033  ldarg.0
0xd0034  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_interval
0xd0039  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ScaleLabelsInterval(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xd003e  ldarg.0
0xd003f  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_intervalOffset
0xd0044  brfalse.s loc_D0069
0xd0046  ldarg.0
0xd0047  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_intervalOffset
0xd004c  ldstr    aIntervaloffset// "IntervalOffset"
0xd0051  ldarg.1
0xd0052  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xd0057  ldarga.s 1
0xd0059  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xd005e  ldarg.0
0xd005f  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_intervalOffset
0xd0064  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ScaleLabelsIntervalOffset(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xd0069  ldarg.0
0xd006a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_allowUpsideDown
0xd006f  brfalse.s loc_D0094
0xd0071  ldarg.0
0xd0072  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_allowUpsideDown
0xd0077  ldstr    aAllowupsidedow// "AllowUpsideDown"
0xd007c  ldarg.1
0xd007d  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xd0082  ldarga.s 1
0xd0084  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xd0089  ldarg.0
0xd008a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_allowUpsideDown
0xd008f  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ScaleLabelsAllowUpsideDown(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xd0094  ldarg.0
0xd0095  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_distanceFromScale
0xd009a  brfalse.s loc_D00BF
0xd009c  ldarg.0
0xd009d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_distanceFromScale
0xd00a2  ldstr    aDistancefromsc// "DistanceFromScale"
0xd00a7  ldarg.1
0xd00a8  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xd00ad  ldarga.s 1
0xd00af  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xd00b4  ldarg.0
0xd00b5  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_distanceFromScale
0xd00ba  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ScaleLabelsDistanceFromScale(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xd00bf  ldarg.0
0xd00c0  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_fontAngle
0xd00c5  brfalse.s loc_D00EA
0xd00c7  ldarg.0
0xd00c8  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_fontAngle
0xd00cd  ldstr    aFontangle// "FontAngle"
0xd00d2  ldarg.1
0xd00d3  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xd00d8  ldarga.s 1
0xd00da  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xd00df  ldarg.0
0xd00e0  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_fontAngle
0xd00e5  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ScaleLabelsFontAngle(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xd00ea  ldarg.0
0xd00eb  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_placement
0xd00f0  brfalse.s loc_D0115
0xd00f2  ldarg.0
0xd00f3  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_placement
0xd00f8  ldstr    aPlacement// "Placement"
0xd00fd  ldarg.1
0xd00fe  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xd0103  ldarga.s 1
0xd0105  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xd010a  ldarg.0
0xd010b  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_placement
0xd0110  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ScaleLabelsPlacement(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xd0115  ldarg.0
0xd0116  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_rotateLabels
0xd011b  brfalse.s loc_D0140
0xd011d  ldarg.0
0xd011e  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_rotateLabels
0xd0123  ldstr    aRotatelabels// "RotateLabels"
0xd0128  ldarg.1
0xd0129  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xd012e  ldarga.s 1
0xd0130  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xd0135  ldarg.0
0xd0136  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_rotateLabels
0xd013b  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ScaleLabelsRotateLabels(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xd0140  ldarg.0
0xd0141  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_showEndLabels
0xd0146  brfalse.s loc_D016B
0xd0148  ldarg.0
0xd0149  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_showEndLabels
0xd014e  ldstr    aShowendlabels// "ShowEndLabels"
0xd0153  ldarg.1
0xd0154  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xd0159  ldarga.s 1
0xd015b  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xd0160  ldarg.0
0xd0161  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_showEndLabels
0xd0166  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ScaleLabelsShowEndLabels(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xd016b  ldarg.0
0xd016c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_hidden
0xd0171  brfalse.s loc_D0196
0xd0173  ldarg.0
0xd0174  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_hidden
0xd0179  ldstr    aHidden// "Hidden"
0xd017e  ldarg.1
0xd017f  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xd0184  ldarga.s 1
0xd0186  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xd018b  ldarg.0
0xd018c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_hidden
0xd0191  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ScaleLabelsHidden(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xd0196  ldarg.0
0xd0197  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_useFontPercent
0xd019c  brfalse.s loc_D01C1
0xd019e  ldarg.0
0xd019f  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_useFontPercent
0xd01a4  ldstr    aUsefontpercent// "UseFontPercent"
0xd01a9  ldarg.1
0xd01aa  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xd01af  ldarga.s 1
0xd01b1  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xd01b6  ldarg.0
0xd01b7  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::m_useFontPercent
0xd01bc  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ScaleLabelsUseFontPercent(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xd01c1  ldarga.s 1
0xd01c3  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xd01c8  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ScaleLabelsEnd()
0xd01cd  ret
```
