# Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::Initialize

- ea: `0xc8480`
- end: `0xc85cd`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::Initialize`
- size: `333`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0xc8480`
- `0xd09d0`
- `0x117ce0`
- `0x13dfc0`
- `0x1505a0`
- `0x1505c0`
- `0x1505e0`
- `0x1505f0`
- `0x150600`
- `0x150610`
- `0x150620`
- `0x150630`
- `0x150640`

## string_xrefs

- `0xc84cc`: `AllowUpsideDown`

## pseudocode

```c

```

## disassembly

```asm
0xc8480  ldarga.s 1
0xc8482  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xc8487  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::PinLabelStart()
0xc848c  ldarg.0
0xc848d  ldarg.1
0xc848e  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.GaugePanelStyleContainer::Initialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xc8493  ldarg.0
0xc8494  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::m_text
0xc8499  brfalse.s loc_C84BE
0xc849b  ldarg.0
0xc849c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::m_text
0xc84a1  ldstr    aText// "Text"
0xc84a6  ldarg.1
0xc84a7  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xc84ac  ldarga.s 1
0xc84ae  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xc84b3  ldarg.0
0xc84b4  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::m_text
0xc84b9  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::PinLabelText(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xc84be  ldarg.0
0xc84bf  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::m_allowUpsideDown
0xc84c4  brfalse.s loc_C84E9
0xc84c6  ldarg.0
0xc84c7  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::m_allowUpsideDown
0xc84cc  ldstr    aAllowupsidedow// "AllowUpsideDown"
0xc84d1  ldarg.1
0xc84d2  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xc84d7  ldarga.s 1
0xc84d9  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xc84de  ldarg.0
0xc84df  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::m_allowUpsideDown
0xc84e4  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::PinLabelAllowUpsideDown(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xc84e9  ldarg.0
0xc84ea  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::m_distanceFromScale
0xc84ef  brfalse.s loc_C8514
0xc84f1  ldarg.0
0xc84f2  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::m_distanceFromScale
0xc84f7  ldstr    aDistancefromsc// "DistanceFromScale"
0xc84fc  ldarg.1
0xc84fd  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xc8502  ldarga.s 1
0xc8504  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xc8509  ldarg.0
0xc850a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::m_distanceFromScale
0xc850f  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::PinLabelDistanceFromScale(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xc8514  ldarg.0
0xc8515  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::m_fontAngle
0xc851a  brfalse.s loc_C853F
0xc851c  ldarg.0
0xc851d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::m_fontAngle
0xc8522  ldstr    aFontangle// "FontAngle"
0xc8527  ldarg.1
0xc8528  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xc852d  ldarga.s 1
0xc852f  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xc8534  ldarg.0
0xc8535  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::m_fontAngle
0xc853a  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::PinLabelFontAngle(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xc853f  ldarg.0
0xc8540  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::m_placement
0xc8545  brfalse.s loc_C856A
0xc8547  ldarg.0
0xc8548  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::m_placement
0xc854d  ldstr    aPlacement// "Placement"
0xc8552  ldarg.1
0xc8553  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xc8558  ldarga.s 1
0xc855a  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xc855f  ldarg.0
0xc8560  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::m_placement
0xc8565  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::PinLabelPlacement(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xc856a  ldarg.0
0xc856b  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::m_rotateLabel
0xc8570  brfalse.s loc_C8595
0xc8572  ldarg.0
0xc8573  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::m_rotateLabel
0xc8578  ldstr    aRotatelabel// "RotateLabel"
0xc857d  ldarg.1
0xc857e  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xc8583  ldarga.s 1
0xc8585  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xc858a  ldarg.0
0xc858b  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::m_rotateLabel
0xc8590  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::PinLabelRotateLabel(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xc8595  ldarg.0
0xc8596  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::m_useFontPercent
0xc859b  brfalse.s loc_C85C0
0xc859d  ldarg.0
0xc859e  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::m_useFontPercent
0xc85a3  ldstr    aUsefontpercent// "UseFontPercent"
0xc85a8  ldarg.1
0xc85a9  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xc85ae  ldarga.s 1
0xc85b0  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xc85b5  ldarg.0
0xc85b6  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::m_useFontPercent
0xc85bb  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::PinLabelUseFontPercent(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xc85c0  ldarga.s 1
0xc85c2  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xc85c7  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::PinLabelEnd()
0xc85cc  ret
```
