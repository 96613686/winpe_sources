# Microsoft.SharePoint.Spx.WebSite.ImageryService.ResponseBase::set_BrandLogoUri

- ea: `0x195e0`
- end: `0x19601`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.ResponseBase::set_BrandLogoUri`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x195e0`
- `0x196b0`

## string_xrefs

- `0x195f6`: `BrandLogoUri`

## pseudocode

```c

```

## disassembly

```asm
0x195e0  ldarg.0
0x195e1  ldfld    class [System]System.Uri Microsoft.SharePoint.Spx.WebSite.ImageryService.ResponseBase::BrandLogoUriField
0x195e6  ldarg.1
0x195e7  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x195ec  brtrue.s loc_19600
0x195ee  ldarg.0
0x195ef  ldarg.1
0x195f0  stfld    class [System]System.Uri Microsoft.SharePoint.Spx.WebSite.ImageryService.ResponseBase::BrandLogoUriField
0x195f5  ldarg.0
0x195f6  ldstr    aBrandlogouri// "BrandLogoUri"
0x195fb  call     instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.ResponseBase::RaisePropertyChanged(string propertyName)
0x19600  ret
```
