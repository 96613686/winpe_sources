# Microsoft.SharePoint.Spx.WebSite.RouteService.ItineraryItem::RaisePropertyChanged

- ea: `0x1c1e0`
- end: `0x1c1f8`
- name: `Microsoft.SharePoint.Spx.WebSite.RouteService.ItineraryItem::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1bfd0`
- `0x1c010`
- `0x1c050`
- `0x1c090`
- `0x1c0d0`
- `0x1c110`
- `0x1c150`

## callees

- `0x1c1e0`

## pseudocode

```c

```

## disassembly

```asm
0x1c1e0  ldarg.0
0x1c1e1  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.RouteService.ItineraryItem::PropertyChanged
0x1c1e6  stloc.0
0x1c1e7  ldloc.0
0x1c1e8  brfalse.s loc_1C1F7
0x1c1ea  ldloc.0
0x1c1eb  ldarg.0
0x1c1ec  ldarg.1
0x1c1ed  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1c1f2  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1c1f7  ret
```
