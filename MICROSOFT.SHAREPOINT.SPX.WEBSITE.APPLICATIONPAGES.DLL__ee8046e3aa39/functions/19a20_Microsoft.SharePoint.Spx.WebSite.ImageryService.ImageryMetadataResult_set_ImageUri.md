# Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryMetadataResult::set_ImageUri

- ea: `0x19a20`
- end: `0x19a41`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryMetadataResult::set_ImageUri`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x19a20`
- `0x19bb0`

## string_xrefs

- `0x19a36`: `ImageUri`

## pseudocode

```c

```

## disassembly

```asm
0x19a20  ldarg.0
0x19a21  ldfld    string Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryMetadataResult::ImageUriField
0x19a26  ldarg.1
0x19a27  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x19a2c  brtrue.s loc_19A40
0x19a2e  ldarg.0
0x19a2f  ldarg.1
0x19a30  stfld    string Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryMetadataResult::ImageUriField
0x19a35  ldarg.0
0x19a36  ldstr    aImageuri// "ImageUri"
0x19a3b  call     instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryMetadataResult::RaisePropertyChanged(string propertyName)
0x19a40  ret
```
