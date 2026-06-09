# Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::Initialize

- ea: `0xff440`
- end: `0xff671`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::Initialize`
- size: `561`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1013c0`

## callees

- `0xfe2f0`
- `0xff440`
- `0x117ce0`
- `0x13dfc0`
- `0x14ec10`
- `0x14ec30`
- `0x14ec40`
- `0x14ec50`
- `0x14ec60`
- `0x14ec70`
- `0x14ec80`
- `0x14ec90`
- `0x14eca0`
- `0x14ecb0`
- `0x14ecc0`
- `0x14ecd0`
- `0x14ece0`
- `0x14ecf0`

## string_xrefs

- `0xff45a`: `AllowOutSidePlotArea`

## pseudocode

```c

```

## disassembly

```asm
0xff440  ldarga.s 1
0xff442  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xff447  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartSmartLabelStart()
0xff44c  ldarg.0
0xff44d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_allowOutSidePlotArea
0xff452  brfalse.s loc_FF477
0xff454  ldarg.0
0xff455  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_allowOutSidePlotArea
0xff45a  ldstr    aAllowoutsidepl// "AllowOutSidePlotArea"
0xff45f  ldarg.1
0xff460  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xff465  ldarga.s 1
0xff467  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xff46c  ldarg.0
0xff46d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_allowOutSidePlotArea
0xff472  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartSmartLabelAllowOutSidePlotArea(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xff477  ldarg.0
0xff478  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_calloutBackColor
0xff47d  brfalse.s loc_FF4A2
0xff47f  ldarg.0
0xff480  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_calloutBackColor
0xff485  ldstr    aCalloutbackcol// "CalloutBackColor"
0xff48a  ldarg.1
0xff48b  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xff490  ldarga.s 1
0xff492  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xff497  ldarg.0
0xff498  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_calloutBackColor
0xff49d  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartSmartLabelCalloutBackColor(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xff4a2  ldarg.0
0xff4a3  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_calloutLineAnchor
0xff4a8  brfalse.s loc_FF4CD
0xff4aa  ldarg.0
0xff4ab  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_calloutLineAnchor
0xff4b0  ldstr    aCalloutlineanc// "CalloutLineAnchor"
0xff4b5  ldarg.1
0xff4b6  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xff4bb  ldarga.s 1
0xff4bd  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xff4c2  ldarg.0
0xff4c3  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_calloutLineAnchor
0xff4c8  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartSmartLabelCalloutLineAnchor(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xff4cd  ldarg.0
0xff4ce  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_calloutLineColor
0xff4d3  brfalse.s loc_FF4F8
0xff4d5  ldarg.0
0xff4d6  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_calloutLineColor
0xff4db  ldstr    aCalloutlinecol// "CalloutLineColor"
0xff4e0  ldarg.1
0xff4e1  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xff4e6  ldarga.s 1
0xff4e8  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xff4ed  ldarg.0
0xff4ee  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_calloutLineColor
0xff4f3  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartSmartLabelCalloutLineColor(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xff4f8  ldarg.0
0xff4f9  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_calloutLineStyle
0xff4fe  brfalse.s loc_FF523
0xff500  ldarg.0
0xff501  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_calloutLineStyle
0xff506  ldstr    aCalloutlinesty// "CalloutLineStyle"
0xff50b  ldarg.1
0xff50c  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xff511  ldarga.s 1
0xff513  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xff518  ldarg.0
0xff519  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_calloutLineStyle
0xff51e  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartSmartLabelCalloutLineStyle(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xff523  ldarg.0
0xff524  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_calloutLineWidth
0xff529  brfalse.s loc_FF54E
0xff52b  ldarg.0
0xff52c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_calloutLineWidth
0xff531  ldstr    aCalloutlinewid// "CalloutLineWidth"
0xff536  ldarg.1
0xff537  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xff53c  ldarga.s 1
0xff53e  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xff543  ldarg.0
0xff544  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_calloutLineWidth
0xff549  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartSmartLabelCalloutLineWidth(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xff54e  ldarg.0
0xff54f  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_calloutStyle
0xff554  brfalse.s loc_FF579
0xff556  ldarg.0
0xff557  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_calloutStyle
0xff55c  ldstr    aCalloutstyle// "CalloutStyle"
0xff561  ldarg.1
0xff562  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xff567  ldarga.s 1
0xff569  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xff56e  ldarg.0
0xff56f  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_calloutStyle
0xff574  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartSmartLabelCalloutStyle(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xff579  ldarg.0
0xff57a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_showOverlapped
0xff57f  brfalse.s loc_FF5A4
0xff581  ldarg.0
0xff582  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_showOverlapped
0xff587  ldstr    aShowoverlapped// "ShowOverlapped"
0xff58c  ldarg.1
0xff58d  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xff592  ldarga.s 1
0xff594  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xff599  ldarg.0
0xff59a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_showOverlapped
0xff59f  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartSmartLabelShowOverlapped(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xff5a4  ldarg.0
0xff5a5  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_markerOverlapping
0xff5aa  brfalse.s loc_FF5CF
0xff5ac  ldarg.0
0xff5ad  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_markerOverlapping
0xff5b2  ldstr    aMarkeroverlapp// "MarkerOverlapping"
0xff5b7  ldarg.1
0xff5b8  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xff5bd  ldarga.s 1
0xff5bf  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xff5c4  ldarg.0
0xff5c5  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_markerOverlapping
0xff5ca  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartSmartLabelMarkerOverlapping(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xff5cf  ldarg.0
0xff5d0  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_maxMovingDistance
0xff5d5  brfalse.s loc_FF5FA
0xff5d7  ldarg.0
0xff5d8  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_maxMovingDistance
0xff5dd  ldstr    aMaxmovingdista// "MaxMovingDistance"
0xff5e2  ldarg.1
0xff5e3  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xff5e8  ldarga.s 1
0xff5ea  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xff5ef  ldarg.0
0xff5f0  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_maxMovingDistance
0xff5f5  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartSmartLabelMaxMovingDistance(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xff5fa  ldarg.0
0xff5fb  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_minMovingDistance
0xff600  brfalse.s loc_FF625
0xff602  ldarg.0
0xff603  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_minMovingDistance
0xff608  ldstr    aMinmovingdista// "MinMovingDistance"
0xff60d  ldarg.1
0xff60e  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xff613  ldarga.s 1
0xff615  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xff61a  ldarg.0
0xff61b  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_minMovingDistance
0xff620  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartSmartLabelMinMovingDistance(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xff625  ldarg.0
0xff626  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ChartNoMoveDirections Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_noMoveDirections
0xff62b  brfalse.s loc_FF639
0xff62d  ldarg.0
0xff62e  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ChartNoMoveDirections Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_noMoveDirections
0xff633  ldarg.1
0xff634  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartNoMoveDirections::Initialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xff639  ldarg.0
0xff63a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_disabled
0xff63f  brfalse.s loc_FF664
0xff641  ldarg.0
0xff642  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_disabled
0xff647  ldstr    aDisabled// "Disabled"
0xff64c  ldarg.1
0xff64d  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xff652  ldarga.s 1
0xff654  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xff659  ldarg.0
0xff65a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::m_disabled
0xff65f  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartSmartLabelDisabled(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xff664  ldarga.s 1
0xff666  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xff66b  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartSmartLabelEnd()
0xff670  ret
```
