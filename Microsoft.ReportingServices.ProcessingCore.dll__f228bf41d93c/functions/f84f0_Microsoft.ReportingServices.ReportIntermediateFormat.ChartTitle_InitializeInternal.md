# Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::InitializeInternal

- ea: `0xf84f0`
- end: `0xf8654`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::InitializeInternal`
- size: `356`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0xf84c0`
- `0xf8e60`

## callees

- `0xee9b0`
- `0xf80e0`
- `0xf84f0`
- `0xfec50`
- `0x117ce0`
- `0x13dfc0`
- `0x14e2e0`
- `0x14e2f0`
- `0x14e300`
- `0x14e310`
- `0x14e320`
- `0x14e330`
- `0x14e340`

## string_xrefs

- `0xf858d`: `DockOutsideChartArea`

## pseudocode

```c

```

## disassembly

```asm
0xf84f0  ldarg.0
0xf84f1  ldarg.1
0xf84f2  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitleBase::Initialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xf84f7  ldarg.0
0xf84f8  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_position
0xf84fd  brfalse.s loc_F8522
0xf84ff  ldarg.0
0xf8500  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_position
0xf8505  ldstr    aPosition// "Position"
0xf850a  ldarg.1
0xf850b  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xf8510  ldarga.s 1
0xf8512  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xf8517  ldarg.0
0xf8518  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_position
0xf851d  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartTitlePosition(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xf8522  ldarg.0
0xf8523  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_hidden
0xf8528  brfalse.s loc_F854D
0xf852a  ldarg.0
0xf852b  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_hidden
0xf8530  ldstr    aHidden// "Hidden"
0xf8535  ldarg.1
0xf8536  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xf853b  ldarga.s 1
0xf853d  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xf8542  ldarg.0
0xf8543  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_hidden
0xf8548  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartTitleHidden(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xf854d  ldarg.0
0xf854e  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_docking
0xf8553  brfalse.s loc_F8578
0xf8555  ldarg.0
0xf8556  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_docking
0xf855b  ldstr    aDocking// "Docking"
0xf8560  ldarg.1
0xf8561  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xf8566  ldarga.s 1
0xf8568  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xf856d  ldarg.0
0xf856e  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_docking
0xf8573  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartTitleDocking(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xf8578  ldarg.0
0xf8579  ldfld    string Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_dockToChartArea
0xf857e  pop
0xf857f  ldarg.0
0xf8580  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_dockOutsideChartArea
0xf8585  brfalse.s loc_F85AA
0xf8587  ldarg.0
0xf8588  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_dockOutsideChartArea
0xf858d  ldstr    aDockoutsidecha// "DockOutsideChartArea"
0xf8592  ldarg.1
0xf8593  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xf8598  ldarga.s 1
0xf859a  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xf859f  ldarg.0
0xf85a0  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_dockOutsideChartArea
0xf85a5  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartTitleDockOutsideChartArea(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xf85aa  ldarg.0
0xf85ab  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_dockOffset
0xf85b0  brfalse.s loc_F85D5
0xf85b2  ldarg.0
0xf85b3  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_dockOffset
0xf85b8  ldstr    aDockoffset// "DockOffset"
0xf85bd  ldarg.1
0xf85be  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xf85c3  ldarga.s 1
0xf85c5  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xf85ca  ldarg.0
0xf85cb  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_dockOffset
0xf85d0  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartTitleDockOffset(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xf85d5  ldarg.0
0xf85d6  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_toolTip
0xf85db  brfalse.s loc_F8600
0xf85dd  ldarg.0
0xf85de  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_toolTip
0xf85e3  ldstr    aTooltip// "ToolTip"
0xf85e8  ldarg.1
0xf85e9  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xf85ee  ldarga.s 1
0xf85f0  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xf85f5  ldarg.0
0xf85f6  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_toolTip
0xf85fb  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartTitleToolTip(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xf8600  ldarg.0
0xf8601  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Action Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_action
0xf8606  brfalse.s loc_F8614
0xf8608  ldarg.0
0xf8609  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Action Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_action
0xf860e  ldarg.1
0xf860f  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Action::Initialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xf8614  ldarg.0
0xf8615  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_textOrientation
0xf861a  brfalse.s loc_F863F
0xf861c  ldarg.0
0xf861d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_textOrientation
0xf8622  ldstr    aTextorientatio// "TextOrientation"
0xf8627  ldarg.1
0xf8628  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xf862d  ldarga.s 1
0xf862f  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xf8634  ldarg.0
0xf8635  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_textOrientation
0xf863a  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartTitleTextOrientation(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xf863f  ldarg.0
0xf8640  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ChartElementPosition Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_chartElementPosition
0xf8645  brfalse.s loc_F8653
0xf8647  ldarg.0
0xf8648  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ChartElementPosition Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::m_chartElementPosition
0xf864d  ldarg.1
0xf864e  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartElementPosition::Initialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xf8653  ret
```
