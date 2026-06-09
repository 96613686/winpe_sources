# Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::Initialize

- ea: `0xeeeb0`
- end: `0xeeffa`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::Initialize`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0xee9b0`

## callees

- `0xeeeb0`
- `0x117ce0`
- `0x13cbf0`
- `0x13cc20`
- `0x13dfc0`
- `0x14d390`
- `0x14d820`
- `0x14d850`
- `0x14d880`
- `0x14d890`
- `0x14d8a0`
- `0x14d8b0`
- `0x14d8c0`
- `0x14d8d0`

## string_xrefs

- `0xeeeca`: `Hyperlink`
- `0xeef74`: `BookmarkLink`
- `0xeef9f`: `BookmarkLink`

## pseudocode

```c

```

## disassembly

```asm
0xeeeb0  ldarga.s 1
0xeeeb2  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xeeeb7  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ActionStart()
0xeeebc  ldarg.0
0xeeebd  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::m_hyperLinkURL
0xeeec2  brfalse.s loc_EEEE7
0xeeec4  ldarg.0
0xeeec5  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::m_hyperLinkURL
0xeeeca  ldstr    aHyperlink// "Hyperlink"
0xeeecf  ldarg.1
0xeeed0  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xeeed5  ldarga.s 1
0xeeed7  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xeeedc  ldarg.0
0xeeedd  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::m_hyperLinkURL
0xeeee2  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ActionHyperlink(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xeeee7  ldarg.0
0xeeee8  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::m_drillthroughReportName
0xeeeed  brfalse.s loc_EEF12
0xeeeef  ldarg.0
0xeeef0  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::m_drillthroughReportName
0xeeef5  ldstr    aDrillthroughre// "DrillthroughReportName"
0xeeefa  ldarg.1
0xeeefb  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xeef00  ldarga.s 1
0xeef02  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xeef07  ldarg.0
0xeef08  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::m_drillthroughReportName
0xeef0d  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ActionDrillThroughReportName(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xeef12  ldarg.0
0xeef13  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue> Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::m_drillthroughParameters
0xeef18  brfalse.s loc_EEF66
0xeef1a  ldc.i4.0
0xeef1b  stloc.0
0xeef1c  br.s     loc_EEF58
0xeef1e  ldarg.0
0xeef1f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue> Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::m_drillthroughParameters
0xeef24  ldloc.0
0xeef25  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue>::get_Item(!!T0)
0xeef2a  ldarga.s 1
0xeef2c  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xeef31  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ActionDrillThroughParameterStart()
0xeef36  dup
0xeef37  ldstr    aDrillthroughpa// "DrillthroughParameters"
0xeef3c  ldarg.1
0xeef3d  ldc.i4.0
0xeef3e  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue::Initialize(string containerPropertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context, bool queryParam)
0xeef43  ldarga.s 1
0xeef45  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xeef4a  callvirt instance int32 Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ActionDrillThroughParameterEnd()
0xeef4f  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue::set_ExprHostID(int32 value)
0xeef54  ldloc.0
0xeef55  ldc.i4.1
0xeef56  add
0xeef57  stloc.0
0xeef58  ldloc.0
0xeef59  ldarg.0
0xeef5a  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue> Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::m_drillthroughParameters
0xeef5f  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue>::get_Count()
0xeef64  blt.s    loc_EEF1E
0xeef66  ldarg.0
0xeef67  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::m_drillthroughBookmarkLink
0xeef6c  brfalse.s loc_EEF91
0xeef6e  ldarg.0
0xeef6f  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::m_drillthroughBookmarkLink
0xeef74  ldstr    aBookmarklink// "BookmarkLink"
0xeef79  ldarg.1
0xeef7a  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xeef7f  ldarga.s 1
0xeef81  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xeef86  ldarg.0
0xeef87  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::m_drillthroughBookmarkLink
0xeef8c  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ActionDrillThroughBookmarkLink(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xeef91  ldarg.0
0xeef92  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::m_bookmarkLink
0xeef97  brfalse.s loc_EEFBC
0xeef99  ldarg.0
0xeef9a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::m_bookmarkLink
0xeef9f  ldstr    aBookmarklink// "BookmarkLink"
0xeefa4  ldarg.1
0xeefa5  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xeefaa  ldarga.s 1
0xeefac  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xeefb1  ldarg.0
0xeefb2  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::m_bookmarkLink
0xeefb7  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ActionBookmarkLink(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xeefbc  ldarg.0
0xeefbd  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::m_label
0xeefc2  brfalse.s loc_EEFE7
0xeefc4  ldarg.0
0xeefc5  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::m_label
0xeefca  ldstr    aLabel// "Label"
0xeefcf  ldarg.1
0xeefd0  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xeefd5  ldarga.s 1
0xeefd7  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xeefdc  ldarg.0
0xeefdd  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::m_label
0xeefe2  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::GenericLabel(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xeefe7  ldarg.0
0xeefe8  ldarga.s 1
0xeefea  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xeefef  callvirt instance int32 Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ActionEnd()
0xeeff4  stfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::m_exprHostID
0xeeff9  ret
```
