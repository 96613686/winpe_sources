# Microsoft.SharePoint.Spx.WebSite.GeocodeService.ResponseBase::set_BrandLogoUri

- ea: `0x17890`
- end: `0x178b1`
- name: `Microsoft.SharePoint.Spx.WebSite.GeocodeService.ResponseBase::set_BrandLogoUri`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x17890`
- `0x17960`

## string_xrefs

- `0x178a6`: `BrandLogoUri`

## pseudocode

```c

```

## disassembly

```asm
0x17890  ldarg.0
0x17891  ldfld    class [System]System.Uri Microsoft.SharePoint.Spx.WebSite.GeocodeService.ResponseBase::BrandLogoUriField
0x17896  ldarg.1
0x17897  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x1789c  brtrue.s loc_178B0
0x1789e  ldarg.0
0x1789f  ldarg.1
0x178a0  stfld    class [System]System.Uri Microsoft.SharePoint.Spx.WebSite.GeocodeService.ResponseBase::BrandLogoUriField
0x178a5  ldarg.0
0x178a6  ldstr    aBrandlogouri// "BrandLogoUri"
0x178ab  call     instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.ResponseBase::RaisePropertyChanged(string propertyName)
0x178b0  ret
```
