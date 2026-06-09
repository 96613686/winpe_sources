# Microsoft.SharePoint.Spx.WebSite.ImageryService.Credentials::set_ApplicationId

- ea: `0x18160`
- end: `0x18181`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.Credentials::set_ApplicationId`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9a40`
- `0x9b90`

## callees

- `0x18160`
- `0x18230`

## pseudocode

```c

```

## disassembly

```asm
0x18160  ldarg.0
0x18161  ldfld    string Microsoft.SharePoint.Spx.WebSite.ImageryService.Credentials::ApplicationIdField
0x18166  ldarg.1
0x18167  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x1816c  brtrue.s loc_18180
0x1816e  ldarg.0
0x1816f  ldarg.1
0x18170  stfld    string Microsoft.SharePoint.Spx.WebSite.ImageryService.Credentials::ApplicationIdField
0x18175  ldarg.0
0x18176  ldstr    aApplicationid// "ApplicationId"
0x1817b  call     instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Credentials::RaisePropertyChanged(string propertyName)
0x18180  ret
```
