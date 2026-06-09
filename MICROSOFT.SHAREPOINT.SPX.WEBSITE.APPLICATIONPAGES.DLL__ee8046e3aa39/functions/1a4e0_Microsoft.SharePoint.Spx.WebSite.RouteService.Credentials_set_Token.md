# Microsoft.SharePoint.Spx.WebSite.RouteService.Credentials::set_Token

- ea: `0x1a4e0`
- end: `0x1a501`
- name: `Microsoft.SharePoint.Spx.WebSite.RouteService.Credentials::set_Token`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1a4e0`
- `0x1a570`

## string_xrefs

- `0x1a4f6`: `Token`

## pseudocode

```c

```

## disassembly

```asm
0x1a4e0  ldarg.0
0x1a4e1  ldfld    string Microsoft.SharePoint.Spx.WebSite.RouteService.Credentials::TokenField
0x1a4e6  ldarg.1
0x1a4e7  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x1a4ec  brtrue.s loc_1A500
0x1a4ee  ldarg.0
0x1a4ef  ldarg.1
0x1a4f0  stfld    string Microsoft.SharePoint.Spx.WebSite.RouteService.Credentials::TokenField
0x1a4f5  ldarg.0
0x1a4f6  ldstr    aToken// "Token"
0x1a4fb  call     instance void Microsoft.SharePoint.Spx.WebSite.RouteService.Credentials::RaisePropertyChanged(string propertyName)
0x1a500  ret
```
