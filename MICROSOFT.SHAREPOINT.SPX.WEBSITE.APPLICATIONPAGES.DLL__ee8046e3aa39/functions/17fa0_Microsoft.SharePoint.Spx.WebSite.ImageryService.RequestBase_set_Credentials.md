# Microsoft.SharePoint.Spx.WebSite.ImageryService.RequestBase::set_Credentials

- ea: `0x17fa0`
- end: `0x17fc1`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.RequestBase::set_Credentials`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9a40`
- `0x9b90`

## callees

- `0x17fa0`
- `0x180f0`

## pseudocode

```c

```

## disassembly

```asm
0x17fa0  ldarg.0
0x17fa1  ldfld    class Microsoft.SharePoint.Spx.WebSite.ImageryService.Credentials Microsoft.SharePoint.Spx.WebSite.ImageryService.RequestBase::CredentialsField
0x17fa6  ldarg.1
0x17fa7  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x17fac  brtrue.s loc_17FC0
0x17fae  ldarg.0
0x17faf  ldarg.1
0x17fb0  stfld    class Microsoft.SharePoint.Spx.WebSite.ImageryService.Credentials Microsoft.SharePoint.Spx.WebSite.ImageryService.RequestBase::CredentialsField
0x17fb5  ldarg.0
0x17fb6  ldstr    aCredentials// "Credentials"
0x17fbb  call     instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.RequestBase::RaisePropertyChanged(string propertyName)
0x17fc0  ret
```
