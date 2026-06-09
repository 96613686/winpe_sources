# Microsoft.SharePoint.Spx.WebSite.GeocodeService.ResponseSummary::set_Copyright

- ea: `0x17a10`
- end: `0x17a31`
- name: `Microsoft.SharePoint.Spx.WebSite.GeocodeService.ResponseSummary::set_Copyright`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x17a10`
- `0x17b60`

## string_xrefs

- `0x17a26`: `Copyright`

## pseudocode

```c

```

## disassembly

```asm
0x17a10  ldarg.0
0x17a11  ldfld    string Microsoft.SharePoint.Spx.WebSite.GeocodeService.ResponseSummary::CopyrightField
0x17a16  ldarg.1
0x17a17  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x17a1c  brtrue.s loc_17A30
0x17a1e  ldarg.0
0x17a1f  ldarg.1
0x17a20  stfld    string Microsoft.SharePoint.Spx.WebSite.GeocodeService.ResponseSummary::CopyrightField
0x17a25  ldarg.0
0x17a26  ldstr    aCopyright// "Copyright"
0x17a2b  call     instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.ResponseSummary::RaisePropertyChanged(string propertyName)
0x17a30  ret
```
