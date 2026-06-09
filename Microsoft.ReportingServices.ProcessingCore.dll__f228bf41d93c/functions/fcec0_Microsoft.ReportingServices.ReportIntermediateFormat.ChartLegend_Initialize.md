# Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::Initialize

- ea: `0xfcec0`
- end: `0xfd256`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::Initialize`
- size: `918`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0xfcec0`
- `0xfec50`
- `0x107a20`
- `0x117ce0`
- `0x13dfc0`
- `0x14e870`
- `0x14e8a0`
- `0x14e8b0`
- `0x14e8c0`
- `0x14e8d0`
- `0x14e8e0`
- `0x14e8f0`
- `0x14e900`
- `0x14e910`
- `0x14e920`
- `0x14e930`
- `0x14e940`
- `0x14e950`
- `0x14e960`
- `0x14e970`
- `0x14e980`
- `0x14e990`
- `0x14e9a0`
- `0x14e9b0`

## string_xrefs

- `0xfcf6f`: `DockOutsideChartArea`

## pseudocode

```c

```

## disassembly

```asm
0xfcec0  ldarga.s 1
0xfcec2  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xfcec7  ldarg.0
0xfcec8  ldfld    string Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_name
0xfcecd  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartLegendStart(string legendName)
0xfced2  ldarg.0
0xfced3  ldarg.1
0xfced4  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartStyleContainer::Initialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xfced9  ldarg.0
0xfceda  ldfld    string Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_dockToChartArea
0xfcedf  pop
0xfcee0  ldarg.0
0xfcee1  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_position
0xfcee6  brfalse.s loc_FCF0B
0xfcee8  ldarg.0
0xfcee9  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_position
0xfceee  ldstr    aPosition// "Position"
0xfcef3  ldarg.1
0xfcef4  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xfcef9  ldarga.s 1
0xfcefb  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xfcf00  ldarg.0
0xfcf01  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_position
0xfcf06  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartLegendPosition(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xfcf0b  ldarg.0
0xfcf0c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_layout
0xfcf11  brfalse.s loc_FCF36
0xfcf13  ldarg.0
0xfcf14  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_layout
0xfcf19  ldstr    aLayout// "Layout"
0xfcf1e  ldarg.1
0xfcf1f  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xfcf24  ldarga.s 1
0xfcf26  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xfcf2b  ldarg.0
0xfcf2c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_layout
0xfcf31  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartLegendLayout(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xfcf36  ldarg.0
0xfcf37  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_hidden
0xfcf3c  brfalse.s loc_FCF61
0xfcf3e  ldarg.0
0xfcf3f  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_hidden
0xfcf44  ldstr    aHidden// "Hidden"
0xfcf49  ldarg.1
0xfcf4a  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xfcf4f  ldarga.s 1
0xfcf51  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xfcf56  ldarg.0
0xfcf57  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_hidden
0xfcf5c  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartLegendHidden(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xfcf61  ldarg.0
0xfcf62  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_dockOutsideChartArea
0xfcf67  brfalse.s loc_FCF8C
0xfcf69  ldarg.0
0xfcf6a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_dockOutsideChartArea
0xfcf6f  ldstr    aDockoutsidecha// "DockOutsideChartArea"
0xfcf74  ldarg.1
0xfcf75  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xfcf7a  ldarga.s 1
0xfcf7c  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xfcf81  ldarg.0
0xfcf82  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_dockOutsideChartArea
0xfcf87  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartLegendDockOutsideChartArea(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xfcf8c  ldarg.0
0xfcf8d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegendTitle Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_chartLegendTitle
0xfcf92  brfalse.s loc_FCFA0
0xfcf94  ldarg.0
0xfcf95  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegendTitle Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_chartLegendTitle
0xfcf9a  ldarg.1
0xfcf9b  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartStyleContainer::Initialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xfcfa0  ldarg.0
0xfcfa1  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_autoFitTextDisabled
0xfcfa6  brfalse.s loc_FCFCB
0xfcfa8  ldarg.0
0xfcfa9  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_autoFitTextDisabled
0xfcfae  ldstr    aAutofittextdis// "AutoFitTextDisabled"
0xfcfb3  ldarg.1
0xfcfb4  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xfcfb9  ldarga.s 1
0xfcfbb  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xfcfc0  ldarg.0
0xfcfc1  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_autoFitTextDisabled
0xfcfc6  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartLegendAutoFitTextDisabled(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xfcfcb  ldarg.0
0xfcfcc  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_minFontSize
0xfcfd1  brfalse.s loc_FCFF6
0xfcfd3  ldarg.0
0xfcfd4  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_minFontSize
0xfcfd9  ldstr    aMinfontsize// "MinFontSize"
0xfcfde  ldarg.1
0xfcfdf  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xfcfe4  ldarga.s 1
0xfcfe6  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xfcfeb  ldarg.0
0xfcfec  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_minFontSize
0xfcff1  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartLegendMinFontSize(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xfcff6  ldarg.0
0xfcff7  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_headerSeparator
0xfcffc  brfalse.s loc_FD021
0xfcffe  ldarg.0
0xfcfff  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_headerSeparator
0xfd004  ldstr    aHeaderseparato// "HeaderSeparator"
0xfd009  ldarg.1
0xfd00a  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xfd00f  ldarga.s 1
0xfd011  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xfd016  ldarg.0
0xfd017  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_headerSeparator
0xfd01c  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartLegendHeaderSeparator(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xfd021  ldarg.0
0xfd022  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_headerSeparatorColor
0xfd027  brfalse.s loc_FD04C
0xfd029  ldarg.0
0xfd02a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_headerSeparatorColor
0xfd02f  ldstr    aHeaderseparato_0// "HeaderSeparatorColor"
0xfd034  ldarg.1
0xfd035  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xfd03a  ldarga.s 1
0xfd03c  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xfd041  ldarg.0
0xfd042  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_headerSeparatorColor
0xfd047  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartLegendHeaderSeparatorColor(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xfd04c  ldarg.0
0xfd04d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_columnSeparator
0xfd052  brfalse.s loc_FD077
0xfd054  ldarg.0
0xfd055  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_columnSeparator
0xfd05a  ldstr    aColumnseparato// "ColumnSeparator"
0xfd05f  ldarg.1
0xfd060  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xfd065  ldarga.s 1
0xfd067  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xfd06c  ldarg.0
0xfd06d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_columnSeparator
0xfd072  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartLegendColumnSeparator(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xfd077  ldarg.0
0xfd078  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_columnSeparatorColor
0xfd07d  brfalse.s loc_FD0A2
0xfd07f  ldarg.0
0xfd080  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_columnSeparatorColor
0xfd085  ldstr    aColumnseparato_0// "ColumnSeparatorColor"
0xfd08a  ldarg.1
0xfd08b  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xfd090  ldarga.s 1
0xfd092  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xfd097  ldarg.0
0xfd098  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_columnSeparatorColor
0xfd09d  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartLegendColumnSeparatorColor(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xfd0a2  ldarg.0
0xfd0a3  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_columnSpacing
0xfd0a8  brfalse.s loc_FD0CD
0xfd0aa  ldarg.0
0xfd0ab  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_columnSpacing
0xfd0b0  ldstr    aColumnspacing// "ColumnSpacing"
0xfd0b5  ldarg.1
0xfd0b6  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xfd0bb  ldarga.s 1
0xfd0bd  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xfd0c2  ldarg.0
0xfd0c3  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_columnSpacing
0xfd0c8  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartLegendColumnSpacing(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xfd0cd  ldarg.0
0xfd0ce  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_interlacedRows
0xfd0d3  brfalse.s loc_FD0F8
0xfd0d5  ldarg.0
0xfd0d6  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_interlacedRows
0xfd0db  ldstr    aInterlacedrows// "InterlacedRows"
0xfd0e0  ldarg.1
0xfd0e1  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xfd0e6  ldarga.s 1
0xfd0e8  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xfd0ed  ldarg.0
0xfd0ee  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_interlacedRows
0xfd0f3  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartLegendInterlacedRows(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xfd0f8  ldarg.0
0xfd0f9  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_interlacedRowsColor
0xfd0fe  brfalse.s loc_FD123
0xfd100  ldarg.0
0xfd101  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_interlacedRowsColor
0xfd106  ldstr    aInterlacedrows_0// "InterlacedRowsColor"
0xfd10b  ldarg.1
0xfd10c  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xfd111  ldarga.s 1
0xfd113  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xfd118  ldarg.0
0xfd119  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_interlacedRowsColor
0xfd11e  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartLegendInterlacedRowsColor(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xfd123  ldarg.0
0xfd124  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_equallySpacedItems
0xfd129  brfalse.s loc_FD14E
0xfd12b  ldarg.0
0xfd12c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_equallySpacedItems
0xfd131  ldstr    aEquallyspacedi// "EquallySpacedItems"
0xfd136  ldarg.1
0xfd137  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xfd13c  ldarga.s 1
0xfd13e  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xfd143  ldarg.0
0xfd144  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_equallySpacedItems
0xfd149  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartLegendEquallySpacedItems(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xfd14e  ldarg.0
0xfd14f  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_reversed
0xfd154  brfalse.s loc_FD179
0xfd156  ldarg.0
0xfd157  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_reversed
0xfd15c  ldstr    aReversed// "Reversed"
0xfd161  ldarg.1
0xfd162  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xfd167  ldarga.s 1
0xfd169  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xfd16e  ldarg.0
0xfd16f  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_reversed
0xfd174  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartLegendReversed(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xfd179  ldarg.0
0xfd17a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_maxAutoSize
0xfd17f  brfalse.s loc_FD1A4
0xfd181  ldarg.0
0xfd182  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_maxAutoSize
0xfd187  ldstr    aMaxautosize// "MaxAutoSize"
0xfd18c  ldarg.1
0xfd18d  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xfd192  ldarga.s 1
0xfd194  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xfd199  ldarg.0
0xfd19a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_maxAutoSize
0xfd19f  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartLegendMaxAutoSize(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xfd1a4  ldarg.0
0xfd1a5  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_textWrapThreshold
0xfd1aa  brfalse.s loc_FD1CF
0xfd1ac  ldarg.0
0xfd1ad  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_textWrapThreshold
0xfd1b2  ldstr    aTextwrapthresh// "TextWrapThreshold"
0xfd1b7  ldarg.1
0xfd1b8  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xfd1bd  ldarga.s 1
0xfd1bf  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xfd1c4  ldarg.0
0xfd1c5  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_textWrapThreshold
0xfd1ca  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartLegendTextWrapThreshold(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xfd1cf  ldarg.0
0xfd1d0  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegendCustomItem> Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_chartLegendCustomItems
0xfd1d5  brfalse.s loc_FD1FF
0xfd1d7  ldc.i4.0
0xfd1d8  stloc.0
0xfd1d9  br.s     loc_FD1F1
0xfd1db  ldarg.0
0xfd1dc  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegendCustomItem> Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_chartLegendCustomItems
0xfd1e1  ldloc.0
0xfd1e2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegendCustomItem>::get_Item(!!T0)
0xfd1e7  ldarg.1
0xfd1e8  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartStyleContainer::Initialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xfd1ed  ldloc.0
0xfd1ee  ldc.i4.1
0xfd1ef  add
0xfd1f0  stloc.0
0xfd1f1  ldloc.0
0xfd1f2  ldarg.0
0xfd1f3  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegendCustomItem> Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_chartLegendCustomItems
0xfd1f8  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegendCustomItem>::get_Count()
0xfd1fd  blt.s    loc_FD1DB
0xfd1ff  ldarg.0
0xfd200  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegendColumn> Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_chartLegendColumns
0xfd205  brfalse.s loc_FD22F
0xfd207  ldc.i4.0
0xfd208  stloc.1
0xfd209  br.s     loc_FD221
0xfd20b  ldarg.0
0xfd20c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegendColumn> Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_chartLegendColumns
0xfd211  ldloc.1
0xfd212  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegendColumn>::get_Item(!!T0)
0xfd217  ldarg.1
0xfd218  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartStyleContainer::Initialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xfd21d  ldloc.1
0xfd21e  ldc.i4.1
0xfd21f  add
0xfd220  stloc.1
0xfd221  ldloc.1
0xfd222  ldarg.0
0xfd223  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegendColumn> Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_chartLegendColumns
0xfd228  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegendColumn>::get_Count()
0xfd22d  blt.s    loc_FD20B
0xfd22f  ldarg.0
0xfd230  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ChartElementPosition Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_chartElementPosition
0xfd235  brfalse.s loc_FD243
0xfd237  ldarg.0
0xfd238  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ChartElementPosition Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_chartElementPosition
0xfd23d  ldarg.1
0xfd23e  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartElementPosition::Initialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xfd243  ldarg.0
0xfd244  ldarga.s 1
0xfd246  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xfd24b  callvirt instance int32 Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartLegendEnd()
0xfd250  stfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::m_exprHostID
0xfd255  ret
```
