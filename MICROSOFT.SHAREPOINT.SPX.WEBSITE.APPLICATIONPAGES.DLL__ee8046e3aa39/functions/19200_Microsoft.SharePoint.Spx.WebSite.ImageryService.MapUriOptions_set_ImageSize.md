# Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::set_ImageSize

- ea: `0x19200`
- end: `0x19221`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::set_ImageSize`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9a40`
- `0x9b90`

## callees

- `0x19200`
- `0x193d0`

## pseudocode

```c

```

## disassembly

```asm
0x19200  ldarg.0
0x19201  ldfld    class Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::ImageSizeField
0x19206  ldarg.1
0x19207  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x1920c  brtrue.s loc_19220
0x1920e  ldarg.0
0x1920f  ldarg.1
0x19210  stfld    class Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::ImageSizeField
0x19215  ldarg.0
0x19216  ldstr    aImagesize// "ImageSize"
0x1921b  call     instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::RaisePropertyChanged(string propertyName)
0x19220  ret
```
