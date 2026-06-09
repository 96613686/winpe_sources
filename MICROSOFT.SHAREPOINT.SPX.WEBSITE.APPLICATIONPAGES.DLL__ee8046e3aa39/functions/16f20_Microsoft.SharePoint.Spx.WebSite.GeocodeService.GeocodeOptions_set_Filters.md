# Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeOptions::set_Filters

- ea: `0x16f20`
- end: `0x16f41`
- name: `Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeOptions::set_Filters`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9d30`

## callees

- `0x16f20`
- `0x16fb0`

## pseudocode

```c

```

## disassembly

```asm
0x16f20  ldarg.0
0x16f21  ldfld    class Microsoft.SharePoint.Spx.WebSite.GeocodeService.FilterBase[] Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeOptions::FiltersField
0x16f26  ldarg.1
0x16f27  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x16f2c  brtrue.s loc_16F40
0x16f2e  ldarg.0
0x16f2f  ldarg.1
0x16f30  stfld    class Microsoft.SharePoint.Spx.WebSite.GeocodeService.FilterBase[] Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeOptions::FiltersField
0x16f35  ldarg.0
0x16f36  ldstr    aFilters// "Filters"
0x16f3b  call     instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeOptions::RaisePropertyChanged(string propertyName)
0x16f40  ret
```
