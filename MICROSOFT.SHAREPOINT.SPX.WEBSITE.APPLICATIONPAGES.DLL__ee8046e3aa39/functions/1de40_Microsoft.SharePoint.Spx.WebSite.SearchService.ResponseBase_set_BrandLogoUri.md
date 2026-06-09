# Microsoft.SharePoint.Spx.WebSite.SearchService.ResponseBase::set_BrandLogoUri

- ea: `0x1de40`
- end: `0x1de61`
- name: `Microsoft.SharePoint.Spx.WebSite.SearchService.ResponseBase::set_BrandLogoUri`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1de40`
- `0x1df10`

## string_xrefs

- `0x1de56`: `BrandLogoUri`

## pseudocode

```c

```

## disassembly

```asm
0x1de40  ldarg.0
0x1de41  ldfld    class [System]System.Uri Microsoft.SharePoint.Spx.WebSite.SearchService.ResponseBase::BrandLogoUriField
0x1de46  ldarg.1
0x1de47  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x1de4c  brtrue.s loc_1DE60
0x1de4e  ldarg.0
0x1de4f  ldarg.1
0x1de50  stfld    class [System]System.Uri Microsoft.SharePoint.Spx.WebSite.SearchService.ResponseBase::BrandLogoUriField
0x1de55  ldarg.0
0x1de56  ldstr    aBrandlogouri// "BrandLogoUri"
0x1de5b  call     instance void Microsoft.SharePoint.Spx.WebSite.SearchService.ResponseBase::RaisePropertyChanged(string propertyName)
0x1de60  ret
```
