# Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryMetadataResult::set_ImageUriSubdomains

- ea: `0x19a60`
- end: `0x19a81`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryMetadataResult::set_ImageUriSubdomains`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x19a60`
- `0x19bb0`

## string_xrefs

- `0x19a76`: `ImageUriSubdomains`

## pseudocode

```c

```

## disassembly

```asm
0x19a60  ldarg.0
0x19a61  ldfld    string[] Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryMetadataResult::ImageUriSubdomainsField
0x19a66  ldarg.1
0x19a67  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x19a6c  brtrue.s loc_19A80
0x19a6e  ldarg.0
0x19a6f  ldarg.1
0x19a70  stfld    string[] Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryMetadataResult::ImageUriSubdomainsField
0x19a75  ldarg.0
0x19a76  ldstr    aImageurisubdom// "ImageUriSubdomains"
0x19a7b  call     instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryMetadataResult::RaisePropertyChanged(string propertyName)
0x19a80  ret
```
