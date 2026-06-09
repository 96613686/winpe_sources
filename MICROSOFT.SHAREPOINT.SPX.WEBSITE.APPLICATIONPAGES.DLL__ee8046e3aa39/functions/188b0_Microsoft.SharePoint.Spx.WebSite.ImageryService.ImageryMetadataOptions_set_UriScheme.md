# Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryMetadataOptions::set_UriScheme

- ea: `0x188b0`
- end: `0x188db`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryMetadataOptions::set_UriScheme`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x188b0`
- `0x18980`

## string_xrefs

- `0x188d0`: `UriScheme`

## pseudocode

```c

```

## disassembly

```asm
0x188b0  ldarg.0
0x188b1  ldfld    valuetype Microsoft.SharePoint.Spx.WebSite.ImageryService.UriScheme Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryMetadataOptions::UriSchemeField
0x188b6  box      Microsoft.SharePoint.Spx.WebSite.ImageryService.UriScheme
0x188bb  ldarg.1
0x188bc  box      Microsoft.SharePoint.Spx.WebSite.ImageryService.UriScheme
0x188c1  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x188c6  brtrue.s loc_188DA
0x188c8  ldarg.0
0x188c9  ldarg.1
0x188ca  stfld    valuetype Microsoft.SharePoint.Spx.WebSite.ImageryService.UriScheme Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryMetadataOptions::UriSchemeField
0x188cf  ldarg.0
0x188d0  ldstr    aUrischeme// "UriScheme"
0x188d5  call     instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryMetadataOptions::RaisePropertyChanged(string propertyName)
0x188da  ret
```
