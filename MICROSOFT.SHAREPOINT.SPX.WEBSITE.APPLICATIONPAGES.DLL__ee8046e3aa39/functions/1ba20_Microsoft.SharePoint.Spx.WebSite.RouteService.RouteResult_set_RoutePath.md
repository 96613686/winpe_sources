# Microsoft.SharePoint.Spx.WebSite.RouteService.RouteResult::set_RoutePath

- ea: `0x1ba20`
- end: `0x1ba41`
- name: `Microsoft.SharePoint.Spx.WebSite.RouteService.RouteResult::set_RoutePath`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ba20`
- `0x1baf0`

## string_xrefs

- `0x1ba36`: `RoutePath`

## pseudocode

```c

```

## disassembly

```asm
0x1ba20  ldarg.0
0x1ba21  ldfld    class Microsoft.SharePoint.Spx.WebSite.RouteService.RoutePath Microsoft.SharePoint.Spx.WebSite.RouteService.RouteResult::RoutePathField
0x1ba26  ldarg.1
0x1ba27  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x1ba2c  brtrue.s loc_1BA40
0x1ba2e  ldarg.0
0x1ba2f  ldarg.1
0x1ba30  stfld    class Microsoft.SharePoint.Spx.WebSite.RouteService.RoutePath Microsoft.SharePoint.Spx.WebSite.RouteService.RouteResult::RoutePathField
0x1ba35  ldarg.0
0x1ba36  ldstr    aRoutepath// "RoutePath"
0x1ba3b  call     instance void Microsoft.SharePoint.Spx.WebSite.RouteService.RouteResult::RaisePropertyChanged(string propertyName)
0x1ba40  ret
```
