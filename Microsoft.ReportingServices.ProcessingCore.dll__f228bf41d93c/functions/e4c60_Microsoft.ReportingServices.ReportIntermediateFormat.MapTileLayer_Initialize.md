# Microsoft.ReportingServices.ReportIntermediateFormat.MapTileLayer::Initialize

- ea: `0xe4c60`
- end: `0xe4d3e`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.MapTileLayer::Initialize`
- size: `222`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0xe1c80`
- `0xe1d50`
- `0xe4870`
- `0xe4c60`
- `0x117ce0`
- `0x13dfc0`
- `0x150f00`
- `0x150f30`
- `0x150f60`
- `0x150f70`
- `0x150f80`

## string_xrefs

- `0xe4c87`: `ServiceUrl`

## pseudocode

```c

```

## disassembly

```asm
0xe4c60  ldarga.s 1
0xe4c62  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xe4c67  ldarg.0
0xe4c68  call     instance string Microsoft.ReportingServices.ReportIntermediateFormat.MapLayer::get_Name()
0xe4c6d  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::MapTileLayerStart(string name)
0xe4c72  ldarg.0
0xe4c73  ldarg.1
0xe4c74  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapLayer::Initialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xe4c79  ldarg.0
0xe4c7a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapTileLayer::m_serviceUrl
0xe4c7f  brfalse.s loc_E4CA4
0xe4c81  ldarg.0
0xe4c82  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapTileLayer::m_serviceUrl
0xe4c87  ldstr    aServiceurl// "ServiceUrl"
0xe4c8c  ldarg.1
0xe4c8d  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xe4c92  ldarga.s 1
0xe4c94  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xe4c99  ldarg.0
0xe4c9a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapTileLayer::m_serviceUrl
0xe4c9f  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::MapTileLayerServiceUrl(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xe4ca4  ldarg.0
0xe4ca5  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapTileLayer::m_tileStyle
0xe4caa  brfalse.s loc_E4CCF
0xe4cac  ldarg.0
0xe4cad  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapTileLayer::m_tileStyle
0xe4cb2  ldstr    aTilestyle// "TileStyle"
0xe4cb7  ldarg.1
0xe4cb8  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xe4cbd  ldarga.s 1
0xe4cbf  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xe4cc4  ldarg.0
0xe4cc5  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapTileLayer::m_tileStyle
0xe4cca  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::MapTileLayerTileStyle(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xe4ccf  ldarg.0
0xe4cd0  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapTileLayer::m_useSecureConnection
0xe4cd5  brfalse.s loc_E4CFA
0xe4cd7  ldarg.0
0xe4cd8  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapTileLayer::m_useSecureConnection
0xe4cdd  ldstr    aUsesecureconne// "UseSecureConnection"
0xe4ce2  ldarg.1
0xe4ce3  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xe4ce8  ldarga.s 1
0xe4cea  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xe4cef  ldarg.0
0xe4cf0  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapTileLayer::m_useSecureConnection
0xe4cf5  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::MapTileLayerUseSecureConnection(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xe4cfa  ldarg.0
0xe4cfb  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.MapTile> Microsoft.ReportingServices.ReportIntermediateFormat.MapTileLayer::m_mapTiles
0xe4d00  brfalse.s loc_E4D2B
0xe4d02  ldc.i4.0
0xe4d03  stloc.0
0xe4d04  br.s     loc_E4D1D
0xe4d06  ldarg.0
0xe4d07  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.MapTile> Microsoft.ReportingServices.ReportIntermediateFormat.MapTileLayer::m_mapTiles
0xe4d0c  ldloc.0
0xe4d0d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.MapTile>::get_Item(!!T0)
0xe4d12  ldarg.1
0xe4d13  ldloc.0
0xe4d14  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapTile::Initialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context, int32 index)
0xe4d19  ldloc.0
0xe4d1a  ldc.i4.1
0xe4d1b  add
0xe4d1c  stloc.0
0xe4d1d  ldloc.0
0xe4d1e  ldarg.0
0xe4d1f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.MapTile> Microsoft.ReportingServices.ReportIntermediateFormat.MapTileLayer::m_mapTiles
0xe4d24  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.MapTile>::get_Count()
0xe4d29  blt.s    loc_E4D06
0xe4d2b  ldarg.0
0xe4d2c  ldarga.s 1
0xe4d2e  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xe4d33  callvirt instance int32 Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::MapTileLayerEnd()
0xe4d38  stfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.MapLayer::m_exprHostID
0xe4d3d  ret
```
