# Microsoft.SharePoint.Spx.WebSite.GeocodeService.Credentials::set_Token

- ea: `0x16640`
- end: `0x16661`
- name: `Microsoft.SharePoint.Spx.WebSite.GeocodeService.Credentials::set_Token`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x16640`
- `0x166d0`

## string_xrefs

- `0x16656`: `Token`

## pseudocode

```c

```

## disassembly

```asm
0x16640  ldarg.0
0x16641  ldfld    string Microsoft.SharePoint.Spx.WebSite.GeocodeService.Credentials::TokenField
0x16646  ldarg.1
0x16647  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x1664c  brtrue.s loc_16660
0x1664e  ldarg.0
0x1664f  ldarg.1
0x16650  stfld    string Microsoft.SharePoint.Spx.WebSite.GeocodeService.Credentials::TokenField
0x16655  ldarg.0
0x16656  ldstr    aToken// "Token"
0x1665b  call     instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.Credentials::RaisePropertyChanged(string propertyName)
0x16660  ret
```
