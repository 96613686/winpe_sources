# Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::set_Style

- ea: `0x192c0`
- end: `0x192eb`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::set_Style`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9a40`
- `0x9b90`

## callees

- `0x192c0`
- `0x193d0`

## pseudocode

```c

```

## disassembly

```asm
0x192c0  ldarg.0
0x192c1  ldfld    valuetype Microsoft.SharePoint.Spx.WebSite.ImageryService.MapStyle Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::StyleField
0x192c6  box      Microsoft.SharePoint.Spx.WebSite.ImageryService.MapStyle
0x192cb  ldarg.1
0x192cc  box      Microsoft.SharePoint.Spx.WebSite.ImageryService.MapStyle
0x192d1  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x192d6  brtrue.s loc_192EA
0x192d8  ldarg.0
0x192d9  ldarg.1
0x192da  stfld    valuetype Microsoft.SharePoint.Spx.WebSite.ImageryService.MapStyle Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::StyleField
0x192df  ldarg.0
0x192e0  ldstr    aStyle// "Style"
0x192e5  call     instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::RaisePropertyChanged(string propertyName)
0x192ea  ret
```
