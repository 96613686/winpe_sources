# Microsoft.SharePoint.Spx.WebSite.RouteService.ResponseSummary::set_Copyright

- ea: `0x1b720`
- end: `0x1b741`
- name: `Microsoft.SharePoint.Spx.WebSite.RouteService.ResponseSummary::set_Copyright`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1b720`
- `0x1b870`

## string_xrefs

- `0x1b736`: `Copyright`

## pseudocode

```c

```

## disassembly

```asm
0x1b720  ldarg.0
0x1b721  ldfld    string Microsoft.SharePoint.Spx.WebSite.RouteService.ResponseSummary::CopyrightField
0x1b726  ldarg.1
0x1b727  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x1b72c  brtrue.s loc_1B740
0x1b72e  ldarg.0
0x1b72f  ldarg.1
0x1b730  stfld    string Microsoft.SharePoint.Spx.WebSite.RouteService.ResponseSummary::CopyrightField
0x1b735  ldarg.0
0x1b736  ldstr    aCopyright// "Copyright"
0x1b73b  call     instance void Microsoft.SharePoint.Spx.WebSite.RouteService.ResponseSummary::RaisePropertyChanged(string propertyName)
0x1b740  ret
```
