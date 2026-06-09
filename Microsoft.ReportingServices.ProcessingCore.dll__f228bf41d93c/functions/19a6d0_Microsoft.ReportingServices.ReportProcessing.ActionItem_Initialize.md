# Microsoft.ReportingServices.ReportProcessing.ActionItem::Initialize

- ea: `0x19a6d0`
- end: `0x19a815`
- name: `Microsoft.ReportingServices.ReportProcessing.ActionItem::Initialize`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x19a300`

## callees

- `0x18d600`
- `0x18d9d0`
- `0x18da00`
- `0x18da30`
- `0x18da40`
- `0x18da50`
- `0x18da60`
- `0x18da70`
- `0x18da80`
- `0x18ee10`
- `0x191020`
- `0x1989c0`
- `0x1989f0`
- `0x19a6d0`
- `0x1a7610`

## string_xrefs

- `0x19a6ea`: `Hyperlink`
- `0x19a78f`: `BookmarkLink`
- `0x19a7ba`: `BookmarkLink`

## pseudocode

```c

```

## disassembly

```asm
0x19a6d0  ldarga.s 1
0x19a6d2  call     instance class Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder Microsoft.ReportingServices.ReportProcessing.InitializationContext::get_ExprHostBuilder()
0x19a6d7  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder::ActionStart()
0x19a6dc  ldarg.0
0x19a6dd  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ActionItem::m_hyperLinkURL
0x19a6e2  brfalse.s loc_19A707
0x19a6e4  ldarg.0
0x19a6e5  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ActionItem::m_hyperLinkURL
0x19a6ea  ldstr    aHyperlink// "Hyperlink"
0x19a6ef  ldarg.1
0x19a6f0  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportProcessing.InitializationContext context)
0x19a6f5  ldarga.s 1
0x19a6f7  call     instance class Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder Microsoft.ReportingServices.ReportProcessing.InitializationContext::get_ExprHostBuilder()
0x19a6fc  ldarg.0
0x19a6fd  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ActionItem::m_hyperLinkURL
0x19a702  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder::ActionHyperlink(class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo expression)
0x19a707  ldarg.0
0x19a708  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ActionItem::m_drillthroughReportName
0x19a70d  brfalse.s loc_19A732
0x19a70f  ldarg.0
0x19a710  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ActionItem::m_drillthroughReportName
0x19a715  ldstr    aDrillthroughre// "DrillthroughReportName"
0x19a71a  ldarg.1
0x19a71b  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportProcessing.InitializationContext context)
0x19a720  ldarga.s 1
0x19a722  call     instance class Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder Microsoft.ReportingServices.ReportProcessing.InitializationContext::get_ExprHostBuilder()
0x19a727  ldarg.0
0x19a728  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ActionItem::m_drillthroughReportName
0x19a72d  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder::ActionDrillThroughReportName(class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo expression)
0x19a732  ldarg.0
0x19a733  ldfld    class Microsoft.ReportingServices.ReportProcessing.ParameterValueList Microsoft.ReportingServices.ReportProcessing.ActionItem::m_drillthroughParameters
0x19a738  brfalse.s loc_19A781
0x19a73a  ldc.i4.0
0x19a73b  stloc.0
0x19a73c  br.s     loc_19A773
0x19a73e  ldarg.0
0x19a73f  ldfld    class Microsoft.ReportingServices.ReportProcessing.ParameterValueList Microsoft.ReportingServices.ReportProcessing.ActionItem::m_drillthroughParameters
0x19a744  ldloc.0
0x19a745  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ParameterValue Microsoft.ReportingServices.ReportProcessing.ParameterValueList::get_Item(int32 index)
0x19a74a  ldarga.s 1
0x19a74c  call     instance class Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder Microsoft.ReportingServices.ReportProcessing.InitializationContext::get_ExprHostBuilder()
0x19a751  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder::ActionDrillThroughParameterStart()
0x19a756  dup
0x19a757  ldarg.1
0x19a758  ldc.i4.0
0x19a759  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ParameterValue::Initialize(valuetype Microsoft.ReportingServices.ReportProcessing.InitializationContext context, bool queryParam)
0x19a75e  ldarga.s 1
0x19a760  call     instance class Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder Microsoft.ReportingServices.ReportProcessing.InitializationContext::get_ExprHostBuilder()
0x19a765  callvirt instance int32 Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder::ActionDrillThroughParameterEnd()
0x19a76a  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ParameterValue::set_ExprHostID(int32 value)
0x19a76f  ldloc.0
0x19a770  ldc.i4.1
0x19a771  add
0x19a772  stloc.0
0x19a773  ldloc.0
0x19a774  ldarg.0
0x19a775  ldfld    class Microsoft.ReportingServices.ReportProcessing.ParameterValueList Microsoft.ReportingServices.ReportProcessing.ActionItem::m_drillthroughParameters
0x19a77a  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x19a77f  blt.s    loc_19A73E
0x19a781  ldarg.0
0x19a782  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ActionItem::m_drillthroughBookmarkLink
0x19a787  brfalse.s loc_19A7AC
0x19a789  ldarg.0
0x19a78a  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ActionItem::m_drillthroughBookmarkLink
0x19a78f  ldstr    aBookmarklink// "BookmarkLink"
0x19a794  ldarg.1
0x19a795  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportProcessing.InitializationContext context)
0x19a79a  ldarga.s 1
0x19a79c  call     instance class Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder Microsoft.ReportingServices.ReportProcessing.InitializationContext::get_ExprHostBuilder()
0x19a7a1  ldarg.0
0x19a7a2  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ActionItem::m_drillthroughBookmarkLink
0x19a7a7  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder::ActionDrillThroughBookmarkLink(class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo expression)
0x19a7ac  ldarg.0
0x19a7ad  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ActionItem::m_bookmarkLink
0x19a7b2  brfalse.s loc_19A7D7
0x19a7b4  ldarg.0
0x19a7b5  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ActionItem::m_bookmarkLink
0x19a7ba  ldstr    aBookmarklink// "BookmarkLink"
0x19a7bf  ldarg.1
0x19a7c0  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportProcessing.InitializationContext context)
0x19a7c5  ldarga.s 1
0x19a7c7  call     instance class Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder Microsoft.ReportingServices.ReportProcessing.InitializationContext::get_ExprHostBuilder()
0x19a7cc  ldarg.0
0x19a7cd  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ActionItem::m_bookmarkLink
0x19a7d2  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder::ActionBookmarkLink(class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo expression)
0x19a7d7  ldarg.0
0x19a7d8  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ActionItem::m_label
0x19a7dd  brfalse.s loc_19A802
0x19a7df  ldarg.0
0x19a7e0  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ActionItem::m_label
0x19a7e5  ldstr    aLabel// "Label"
0x19a7ea  ldarg.1
0x19a7eb  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportProcessing.InitializationContext context)
0x19a7f0  ldarga.s 1
0x19a7f2  call     instance class Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder Microsoft.ReportingServices.ReportProcessing.InitializationContext::get_ExprHostBuilder()
0x19a7f7  ldarg.0
0x19a7f8  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ActionItem::m_label
0x19a7fd  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder::GenericLabel(class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo expression)
0x19a802  ldarg.0
0x19a803  ldarga.s 1
0x19a805  call     instance class Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder Microsoft.ReportingServices.ReportProcessing.InitializationContext::get_ExprHostBuilder()
0x19a80a  callvirt instance int32 Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder::ActionEnd()
0x19a80f  stfld    int32 Microsoft.ReportingServices.ReportProcessing.ActionItem::m_exprHostID
0x19a814  ret
```
