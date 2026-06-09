# Microsoft.SharePoint.Spx.WebSite.SearchService.Credentials::set_Token

- ea: `0x1c850`
- end: `0x1c871`
- name: `Microsoft.SharePoint.Spx.WebSite.SearchService.Credentials::set_Token`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1c850`
- `0x1c8e0`

## string_xrefs

- `0x1c866`: `Token`

## pseudocode

```c

```

## disassembly

```asm
0x1c850  ldarg.0
0x1c851  ldfld    string Microsoft.SharePoint.Spx.WebSite.SearchService.Credentials::TokenField
0x1c856  ldarg.1
0x1c857  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x1c85c  brtrue.s loc_1C870
0x1c85e  ldarg.0
0x1c85f  ldarg.1
0x1c860  stfld    string Microsoft.SharePoint.Spx.WebSite.SearchService.Credentials::TokenField
0x1c865  ldarg.0
0x1c866  ldstr    aToken// "Token"
0x1c86b  call     instance void Microsoft.SharePoint.Spx.WebSite.SearchService.Credentials::RaisePropertyChanged(string propertyName)
0x1c870  ret
```
