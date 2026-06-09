# Microsoft.SharePoint.Spx.WebSite.SearchService.ResponseSummary::set_Copyright

- ea: `0x1f5c0`
- end: `0x1f5e1`
- name: `Microsoft.SharePoint.Spx.WebSite.SearchService.ResponseSummary::set_Copyright`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1f5c0`
- `0x1f710`

## string_xrefs

- `0x1f5d6`: `Copyright`

## pseudocode

```c

```

## disassembly

```asm
0x1f5c0  ldarg.0
0x1f5c1  ldfld    string Microsoft.SharePoint.Spx.WebSite.SearchService.ResponseSummary::CopyrightField
0x1f5c6  ldarg.1
0x1f5c7  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x1f5cc  brtrue.s loc_1F5E0
0x1f5ce  ldarg.0
0x1f5cf  ldarg.1
0x1f5d0  stfld    string Microsoft.SharePoint.Spx.WebSite.SearchService.ResponseSummary::CopyrightField
0x1f5d5  ldarg.0
0x1f5d6  ldstr    aCopyright// "Copyright"
0x1f5db  call     instance void Microsoft.SharePoint.Spx.WebSite.SearchService.ResponseSummary::RaisePropertyChanged(string propertyName)
0x1f5e0  ret
```
