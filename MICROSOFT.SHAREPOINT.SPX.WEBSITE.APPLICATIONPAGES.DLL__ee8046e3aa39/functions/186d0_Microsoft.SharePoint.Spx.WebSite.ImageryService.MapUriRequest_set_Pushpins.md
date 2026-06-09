# Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::set_Pushpins

- ea: `0x186d0`
- end: `0x186f1`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::set_Pushpins`
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
- `0x186d0`

## pseudocode

```c

```

## disassembly

```asm
0x186d0  ldarg.0
0x186d1  ldfld    class Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin[] Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::PushpinsField
0x186d6  ldarg.1
0x186d7  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x186dc  brtrue.s loc_186F0
0x186de  ldarg.0
0x186df  ldarg.1
0x186e0  stfld    class Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin[] Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::PushpinsField
0x186e5  ldarg.0
0x186e6  ldstr    aPushpins// "Pushpins"
0x186eb  call     instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.RequestBase::RaisePropertyChanged(string propertyName)
0x186f0  ret
```
