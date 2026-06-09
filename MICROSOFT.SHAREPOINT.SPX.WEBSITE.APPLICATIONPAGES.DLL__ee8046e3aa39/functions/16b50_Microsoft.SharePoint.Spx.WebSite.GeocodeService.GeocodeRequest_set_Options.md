# Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeRequest::set_Options

- ea: `0x16b50`
- end: `0x16b71`
- name: `Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeRequest::set_Options`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9d30`

## callees

- `0x16590`
- `0x16b50`

## pseudocode

```c

```

## disassembly

```asm
0x16b50  ldarg.0
0x16b51  ldfld    class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeOptions Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeRequest::OptionsField
0x16b56  ldarg.1
0x16b57  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x16b5c  brtrue.s loc_16B70
0x16b5e  ldarg.0
0x16b5f  ldarg.1
0x16b60  stfld    class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeOptions Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeRequest::OptionsField
0x16b65  ldarg.0
0x16b66  ldstr    aOptions// "Options"
0x16b6b  call     instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.RequestBase::RaisePropertyChanged(string propertyName)
0x16b70  ret
```
