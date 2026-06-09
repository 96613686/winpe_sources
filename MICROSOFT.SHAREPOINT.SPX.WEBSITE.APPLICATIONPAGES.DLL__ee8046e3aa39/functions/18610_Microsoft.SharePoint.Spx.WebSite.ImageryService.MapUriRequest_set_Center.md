# Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::set_Center

- ea: `0x18610`
- end: `0x18631`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::set_Center`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9a40`
- `0x9b90`

## callees

- `0x180f0`
- `0x18610`

## pseudocode

```c

```

## disassembly

```asm
0x18610  ldarg.0
0x18611  ldfld    class Microsoft.SharePoint.Spx.WebSite.ImageryService.Location Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::CenterField
0x18616  ldarg.1
0x18617  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x1861c  brtrue.s loc_18630
0x1861e  ldarg.0
0x1861f  ldarg.1
0x18620  stfld    class Microsoft.SharePoint.Spx.WebSite.ImageryService.Location Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::CenterField
0x18625  ldarg.0
0x18626  ldstr    aCenter_0// "Center"
0x1862b  call     instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.RequestBase::RaisePropertyChanged(string propertyName)
0x18630  ret
```
