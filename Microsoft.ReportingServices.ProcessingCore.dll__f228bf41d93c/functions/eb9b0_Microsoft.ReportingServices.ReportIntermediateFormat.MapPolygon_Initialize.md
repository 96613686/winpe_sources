# Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygon::Initialize

- ea: `0xeb9b0`
- end: `0xeba66`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygon::Initialize`
- size: `182`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0xddad0`
- `0xeb9b0`
- `0xebe90`
- `0x117ce0`
- `0x13dfc0`
- `0x151330`
- `0x151360`
- `0x151390`
- `0x1513a0`

## string_xrefs

- `0xeb9e3`: `UseCustomPolygonTemplate`
- `0xeba22`: `UseCustomPointTemplate`

## pseudocode

```c

```

## disassembly

```asm
0xeb9b0  ldarga.s 1
0xeb9b2  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xeb9b7  ldarga.s 2
0xeb9b9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xeb9be  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0xeb9c3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xeb9c8  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::MapPolygonStart(string name)
0xeb9cd  ldarg.0
0xeb9ce  ldarg.1
0xeb9cf  ldarg.2
0xeb9d0  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapSpatialElement::Initialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context, int32 index)
0xeb9d5  ldarg.0
0xeb9d6  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygon::m_useCustomPolygonTemplate
0xeb9db  brfalse.s loc_EBA00
0xeb9dd  ldarg.0
0xeb9de  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygon::m_useCustomPolygonTemplate
0xeb9e3  ldstr    aUsecustompolyg// "UseCustomPolygonTemplate"
0xeb9e8  ldarg.1
0xeb9e9  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xeb9ee  ldarga.s 1
0xeb9f0  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xeb9f5  ldarg.0
0xeb9f6  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygon::m_useCustomPolygonTemplate
0xeb9fb  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::MapPolygonUseCustomPolygonTemplate(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xeba00  ldarg.0
0xeba01  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygonTemplate Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygon::m_mapPolygonTemplate
0xeba06  brfalse.s loc_EBA14
0xeba08  ldarg.0
0xeba09  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygonTemplate Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygon::m_mapPolygonTemplate
0xeba0e  ldarg.1
0xeba0f  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapStyleContainer::Initialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xeba14  ldarg.0
0xeba15  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygon::m_useCustomCenterPointTemplate
0xeba1a  brfalse.s loc_EBA3F
0xeba1c  ldarg.0
0xeba1d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygon::m_useCustomCenterPointTemplate
0xeba22  ldstr    aUsecustompoint// "UseCustomPointTemplate"
0xeba27  ldarg.1
0xeba28  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xeba2d  ldarga.s 1
0xeba2f  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xeba34  ldarg.0
0xeba35  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygon::m_useCustomCenterPointTemplate
0xeba3a  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::MapPolygonUseCustomCenterPointTemplate(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xeba3f  ldarg.0
0xeba40  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.MapPointTemplate Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygon::m_mapCenterPointTemplate
0xeba45  brfalse.s loc_EBA53
0xeba47  ldarg.0
0xeba48  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.MapPointTemplate Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygon::m_mapCenterPointTemplate
0xeba4d  ldarg.1
0xeba4e  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapStyleContainer::Initialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xeba53  ldarg.0
0xeba54  ldarga.s 1
0xeba56  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xeba5b  callvirt instance int32 Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::MapPolygonEnd()
0xeba60  stfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.MapSpatialElement::m_exprHostID
0xeba65  ret
```
