# Microsoft.SharePoint.Spx.WebSite.RouteService.ResponseBase::set_BrandLogoUri

- ea: `0x1b5a0`
- end: `0x1b5c1`
- name: `Microsoft.SharePoint.Spx.WebSite.RouteService.ResponseBase::set_BrandLogoUri`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1b5a0`
- `0x1b670`

## string_xrefs

- `0x1b5b6`: `BrandLogoUri`

## pseudocode

```c

```

## disassembly

```asm
0x1b5a0  ldarg.0
0x1b5a1  ldfld    class [System]System.Uri Microsoft.SharePoint.Spx.WebSite.RouteService.ResponseBase::BrandLogoUriField
0x1b5a6  ldarg.1
0x1b5a7  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x1b5ac  brtrue.s loc_1B5C0
0x1b5ae  ldarg.0
0x1b5af  ldarg.1
0x1b5b0  stfld    class [System]System.Uri Microsoft.SharePoint.Spx.WebSite.RouteService.ResponseBase::BrandLogoUriField
0x1b5b5  ldarg.0
0x1b5b6  ldstr    aBrandlogouri// "BrandLogoUri"
0x1b5bb  call     instance void Microsoft.SharePoint.Spx.WebSite.RouteService.ResponseBase::RaisePropertyChanged(string propertyName)
0x1b5c0  ret
```
