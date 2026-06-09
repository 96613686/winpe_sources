# Microsoft.SharePoint.Spx.WebSite.RouteService.ItineraryItem::set_CompassDirection

- ea: `0x1bfd0`
- end: `0x1bff1`
- name: `Microsoft.SharePoint.Spx.WebSite.RouteService.ItineraryItem::set_CompassDirection`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1bfd0`
- `0x1c1e0`

## string_xrefs

- `0x1bfe6`: `CompassDirection`

## pseudocode

```c

```

## disassembly

```asm
0x1bfd0  ldarg.0
0x1bfd1  ldfld    string Microsoft.SharePoint.Spx.WebSite.RouteService.ItineraryItem::CompassDirectionField
0x1bfd6  ldarg.1
0x1bfd7  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x1bfdc  brtrue.s loc_1BFF0
0x1bfde  ldarg.0
0x1bfdf  ldarg.1
0x1bfe0  stfld    string Microsoft.SharePoint.Spx.WebSite.RouteService.ItineraryItem::CompassDirectionField
0x1bfe5  ldarg.0
0x1bfe6  ldstr    aCompassdirecti// "CompassDirection"
0x1bfeb  call     instance void Microsoft.SharePoint.Spx.WebSite.RouteService.ItineraryItem::RaisePropertyChanged(string propertyName)
0x1bff0  ret
```
