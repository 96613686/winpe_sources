# Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::Initialize

- ea: `0xdef40`
- end: `0xdf008`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::Initialize`
- size: `200`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0xdf5f0`
- `0xe0170`
- `0xe04f0`
- `0xe0a40`

## callees

- `0xde760`
- `0xdef40`
- `0xee9b0`
- `0x117ce0`
- `0x13dfc0`
- `0x151fd0`
- `0x151fe0`
- `0x151ff0`
- `0x152000`

## string_xrefs

- `0xdef94`: `DockOutsideViewport`

## pseudocode

```c

```

## disassembly

```asm
0xdef40  ldarg.0
0xdef41  ldarg.1
0xdef42  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapSubItem::Initialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xdef47  ldarg.0
0xdef48  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Action Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::m_action
0xdef4d  brfalse.s loc_DEF5B
0xdef4f  ldarg.0
0xdef50  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Action Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::m_action
0xdef55  ldarg.1
0xdef56  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Action::Initialize(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xdef5b  ldarg.0
0xdef5c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::m_position
0xdef61  brfalse.s loc_DEF86
0xdef63  ldarg.0
0xdef64  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::m_position
0xdef69  ldstr    aPosition// "Position"
0xdef6e  ldarg.1
0xdef6f  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xdef74  ldarga.s 1
0xdef76  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xdef7b  ldarg.0
0xdef7c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::m_position
0xdef81  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::MapDockableSubItemPosition(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xdef86  ldarg.0
0xdef87  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::m_dockOutsideViewport
0xdef8c  brfalse.s loc_DEFB1
0xdef8e  ldarg.0
0xdef8f  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::m_dockOutsideViewport
0xdef94  ldstr    aDockoutsidevie// "DockOutsideViewport"
0xdef99  ldarg.1
0xdef9a  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xdef9f  ldarga.s 1
0xdefa1  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xdefa6  ldarg.0
0xdefa7  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::m_dockOutsideViewport
0xdefac  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::MapDockableSubItemDockOutsideViewport(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xdefb1  ldarg.0
0xdefb2  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::m_hidden
0xdefb7  brfalse.s loc_DEFDC
0xdefb9  ldarg.0
0xdefba  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::m_hidden
0xdefbf  ldstr    aHidden// "Hidden"
0xdefc4  ldarg.1
0xdefc5  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xdefca  ldarga.s 1
0xdefcc  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xdefd1  ldarg.0
0xdefd2  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::m_hidden
0xdefd7  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::MapDockableSubItemHidden(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xdefdc  ldarg.0
0xdefdd  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::m_toolTip
0xdefe2  brfalse.s loc_DF007
0xdefe4  ldarg.0
0xdefe5  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::m_toolTip
0xdefea  ldstr    aTooltip// "ToolTip"
0xdefef  ldarg.1
0xdeff0  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0xdeff5  ldarga.s 1
0xdeff7  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0xdeffc  ldarg.0
0xdeffd  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::m_toolTip
0xdf002  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::MapDockableSubItemToolTip(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0xdf007  ret
```
