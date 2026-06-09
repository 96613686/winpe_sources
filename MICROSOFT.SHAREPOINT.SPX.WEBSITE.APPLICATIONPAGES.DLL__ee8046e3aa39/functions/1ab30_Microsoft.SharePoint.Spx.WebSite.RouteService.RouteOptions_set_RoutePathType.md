# Microsoft.SharePoint.Spx.WebSite.RouteService.RouteOptions::set_RoutePathType

- ea: `0x1ab30`
- end: `0x1ab5b`
- name: `Microsoft.SharePoint.Spx.WebSite.RouteService.RouteOptions::set_RoutePathType`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab30`
- `0x1ac00`

## string_xrefs

- `0x1ab50`: `RoutePathType`

## pseudocode

```c

```

## disassembly

```asm
0x1ab30  ldarg.0
0x1ab31  ldfld    valuetype Microsoft.SharePoint.Spx.WebSite.RouteService.RoutePathType Microsoft.SharePoint.Spx.WebSite.RouteService.RouteOptions::RoutePathTypeField
0x1ab36  box      Microsoft.SharePoint.Spx.WebSite.RouteService.RoutePathType
0x1ab3b  ldarg.1
0x1ab3c  box      Microsoft.SharePoint.Spx.WebSite.RouteService.RoutePathType
0x1ab41  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x1ab46  brtrue.s loc_1AB5A
0x1ab48  ldarg.0
0x1ab49  ldarg.1
0x1ab4a  stfld    valuetype Microsoft.SharePoint.Spx.WebSite.RouteService.RoutePathType Microsoft.SharePoint.Spx.WebSite.RouteService.RouteOptions::RoutePathTypeField
0x1ab4f  ldarg.0
0x1ab50  ldstr    aRoutepathtype// "RoutePathType"
0x1ab55  call     instance void Microsoft.SharePoint.Spx.WebSite.RouteService.RouteOptions::RaisePropertyChanged(string propertyName)
0x1ab5a  ret
```
