# Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::set_UriScheme

- ea: `0x19300`
- end: `0x1932b`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::set_UriScheme`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x19300`
- `0x193d0`

## string_xrefs

- `0x19320`: `UriScheme`

## pseudocode

```c

```

## disassembly

```asm
0x19300  ldarg.0
0x19301  ldfld    valuetype Microsoft.SharePoint.Spx.WebSite.ImageryService.UriScheme Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::UriSchemeField
0x19306  box      Microsoft.SharePoint.Spx.WebSite.ImageryService.UriScheme
0x1930b  ldarg.1
0x1930c  box      Microsoft.SharePoint.Spx.WebSite.ImageryService.UriScheme
0x19311  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x19316  brtrue.s loc_1932A
0x19318  ldarg.0
0x19319  ldarg.1
0x1931a  stfld    valuetype Microsoft.SharePoint.Spx.WebSite.ImageryService.UriScheme Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::UriSchemeField
0x1931f  ldarg.0
0x19320  ldstr    aUrischeme// "UriScheme"
0x19325  call     instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::RaisePropertyChanged(string propertyName)
0x1932a  ret
```
