# Microsoft.SharePoint.Spx.WebSite.GeocodeService.RequestBase::set_Credentials

- ea: `0x16440`
- end: `0x16461`
- name: `Microsoft.SharePoint.Spx.WebSite.GeocodeService.RequestBase::set_Credentials`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9d30`
- `0xa1e0`

## callees

- `0x16440`
- `0x16590`

## pseudocode

```c

```

## disassembly

```asm
0x16440  ldarg.0
0x16441  ldfld    class Microsoft.SharePoint.Spx.WebSite.GeocodeService.Credentials Microsoft.SharePoint.Spx.WebSite.GeocodeService.RequestBase::CredentialsField
0x16446  ldarg.1
0x16447  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x1644c  brtrue.s loc_16460
0x1644e  ldarg.0
0x1644f  ldarg.1
0x16450  stfld    class Microsoft.SharePoint.Spx.WebSite.GeocodeService.Credentials Microsoft.SharePoint.Spx.WebSite.GeocodeService.RequestBase::CredentialsField
0x16455  ldarg.0
0x16456  ldstr    aCredentials// "Credentials"
0x1645b  call     instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.RequestBase::RaisePropertyChanged(string propertyName)
0x16460  ret
```
