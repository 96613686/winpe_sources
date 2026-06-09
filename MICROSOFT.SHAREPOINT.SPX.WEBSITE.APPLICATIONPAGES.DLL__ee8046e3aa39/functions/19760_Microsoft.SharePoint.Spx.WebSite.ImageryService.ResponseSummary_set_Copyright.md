# Microsoft.SharePoint.Spx.WebSite.ImageryService.ResponseSummary::set_Copyright

- ea: `0x19760`
- end: `0x19781`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.ResponseSummary::set_Copyright`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x19760`
- `0x198b0`

## string_xrefs

- `0x19776`: `Copyright`

## pseudocode

```c

```

## disassembly

```asm
0x19760  ldarg.0
0x19761  ldfld    string Microsoft.SharePoint.Spx.WebSite.ImageryService.ResponseSummary::CopyrightField
0x19766  ldarg.1
0x19767  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x1976c  brtrue.s loc_19780
0x1976e  ldarg.0
0x1976f  ldarg.1
0x19770  stfld    string Microsoft.SharePoint.Spx.WebSite.ImageryService.ResponseSummary::CopyrightField
0x19775  ldarg.0
0x19776  ldstr    aCopyright// "Copyright"
0x1977b  call     instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.ResponseSummary::RaisePropertyChanged(string propertyName)
0x19780  ret
```
