# Microsoft.SharePoint.Spx.WebSite.ImageryService.Credentials::set_Token

- ea: `0x181a0`
- end: `0x181c1`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.Credentials::set_Token`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x181a0`
- `0x18230`

## string_xrefs

- `0x181b6`: `Token`

## pseudocode

```c

```

## disassembly

```asm
0x181a0  ldarg.0
0x181a1  ldfld    string Microsoft.SharePoint.Spx.WebSite.ImageryService.Credentials::TokenField
0x181a6  ldarg.1
0x181a7  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x181ac  brtrue.s loc_181C0
0x181ae  ldarg.0
0x181af  ldarg.1
0x181b0  stfld    string Microsoft.SharePoint.Spx.WebSite.ImageryService.Credentials::TokenField
0x181b5  ldarg.0
0x181b6  ldstr    aToken// "Token"
0x181bb  call     instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Credentials::RaisePropertyChanged(string propertyName)
0x181c0  ret
```
