# Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::Initialize

- ea: `0xc6620`
- end: `0xc67e3`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::Initialize`
- size: `451`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0xc6620`
- `0xd09d0`
- `0x117ce0`
- `0x13dfc0`
- `0x14fc90`
- `0x14fcc0`
- `0x14fcf0`
- `0x14fd00`
- `0x14fd10`
- `0x14fd20`
- `0x14fd30`
- `0x14fd40`
- `0x14fd50`
- `0x14fd60`
- `0x14fd70`

## string_xrefs

- `0xc6672`: `AllowUpsideDown`

## pseudocode

```c

```

## disassembly

```asm
0xc6620  ldarga.s 1
0xc6622  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xc6627  ldarg.0
0xc6628  ldfld    string Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_name
0xc662d  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::CustomLabelStart(string name)
0xc6632  ldarg.0
0xc6633  ldarg.1
0xc6634  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.GaugePanelStyleContainer::Initialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xc6639  ldarg.0
0xc663a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_text
0xc663f  brfalse.s loc_C6664
0xc6641  ldarg.0
0xc6642  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_text
0xc6647  ldstr    aText// "Text"
0xc664c  ldarg.1
0xc664d  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xc6652  ldarga.s 1
0xc6654  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xc6659  ldarg.0
0xc665a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_text
0xc665f  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::CustomLabelText(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xc6664  ldarg.0
0xc6665  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_allowUpsideDown
0xc666a  brfalse.s loc_C668F
0xc666c  ldarg.0
0xc666d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_allowUpsideDown
0xc6672  ldstr    aAllowupsidedow// "AllowUpsideDown"
0xc6677  ldarg.1
0xc6678  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xc667d  ldarga.s 1
0xc667f  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xc6684  ldarg.0
0xc6685  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_allowUpsideDown
0xc668a  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::CustomLabelAllowUpsideDown(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xc668f  ldarg.0
0xc6690  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_distanceFromScale
0xc6695  brfalse.s loc_C66BA
0xc6697  ldarg.0
0xc6698  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_distanceFromScale
0xc669d  ldstr    aDistancefromsc// "DistanceFromScale"
0xc66a2  ldarg.1
0xc66a3  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xc66a8  ldarga.s 1
0xc66aa  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xc66af  ldarg.0
0xc66b0  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_distanceFromScale
0xc66b5  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::CustomLabelDistanceFromScale(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xc66ba  ldarg.0
0xc66bb  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_fontAngle
0xc66c0  brfalse.s loc_C66E5
0xc66c2  ldarg.0
0xc66c3  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_fontAngle
0xc66c8  ldstr    aFontangle// "FontAngle"
0xc66cd  ldarg.1
0xc66ce  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xc66d3  ldarga.s 1
0xc66d5  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xc66da  ldarg.0
0xc66db  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_fontAngle
0xc66e0  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::CustomLabelFontAngle(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xc66e5  ldarg.0
0xc66e6  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_placement
0xc66eb  brfalse.s loc_C6710
0xc66ed  ldarg.0
0xc66ee  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_placement
0xc66f3  ldstr    aPlacement// "Placement"
0xc66f8  ldarg.1
0xc66f9  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xc66fe  ldarga.s 1
0xc6700  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xc6705  ldarg.0
0xc6706  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_placement
0xc670b  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::CustomLabelPlacement(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xc6710  ldarg.0
0xc6711  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_rotateLabel
0xc6716  brfalse.s loc_C673B
0xc6718  ldarg.0
0xc6719  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_rotateLabel
0xc671e  ldstr    aRotatelabel// "RotateLabel"
0xc6723  ldarg.1
0xc6724  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xc6729  ldarga.s 1
0xc672b  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xc6730  ldarg.0
0xc6731  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_rotateLabel
0xc6736  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::CustomLabelRotateLabel(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xc673b  ldarg.0
0xc673c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.TickMarkStyle Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_tickMarkStyle
0xc6741  brfalse.s loc_C674F
0xc6743  ldarg.0
0xc6744  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.TickMarkStyle Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_tickMarkStyle
0xc6749  ldarg.1
0xc674a  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.GaugePanelStyleContainer::Initialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xc674f  ldarg.0
0xc6750  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_value
0xc6755  brfalse.s loc_C677A
0xc6757  ldarg.0
0xc6758  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_value
0xc675d  ldstr    aValue// "Value"
0xc6762  ldarg.1
0xc6763  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xc6768  ldarga.s 1
0xc676a  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xc676f  ldarg.0
0xc6770  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_value
0xc6775  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::CustomLabelValue(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xc677a  ldarg.0
0xc677b  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_hidden
0xc6780  brfalse.s loc_C67A5
0xc6782  ldarg.0
0xc6783  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_hidden
0xc6788  ldstr    aHidden// "Hidden"
0xc678d  ldarg.1
0xc678e  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xc6793  ldarga.s 1
0xc6795  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xc679a  ldarg.0
0xc679b  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_hidden
0xc67a0  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::CustomLabelHidden(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xc67a5  ldarg.0
0xc67a6  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_useFontPercent
0xc67ab  brfalse.s loc_C67D0
0xc67ad  ldarg.0
0xc67ae  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_useFontPercent
0xc67b3  ldstr    aUsefontpercent// "UseFontPercent"
0xc67b8  ldarg.1
0xc67b9  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xc67be  ldarga.s 1
0xc67c0  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xc67c5  ldarg.0
0xc67c6  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_useFontPercent
0xc67cb  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::CustomLabelUseFontPercent(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xc67d0  ldarg.0
0xc67d1  ldarga.s 1
0xc67d3  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xc67d8  callvirt instance int32 Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::CustomLabelEnd()
0xc67dd  stfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::m_exprHostID
0xc67e2  ret
```
