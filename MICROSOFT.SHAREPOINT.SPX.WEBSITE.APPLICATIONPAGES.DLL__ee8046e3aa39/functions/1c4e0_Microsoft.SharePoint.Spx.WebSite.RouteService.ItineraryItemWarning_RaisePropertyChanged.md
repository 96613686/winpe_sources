# Microsoft.SharePoint.Spx.WebSite.RouteService.ItineraryItemWarning::RaisePropertyChanged

- ea: `0x1c4e0`
- end: `0x1c4f8`
- name: `Microsoft.SharePoint.Spx.WebSite.RouteService.ItineraryItemWarning::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1c3d0`
- `0x1c410`
- `0x1c450`

## callees

- `0x1c4e0`

## pseudocode

```c

```

## disassembly

```asm
0x1c4e0  ldarg.0
0x1c4e1  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.RouteService.ItineraryItemWarning::PropertyChanged
0x1c4e6  stloc.0
0x1c4e7  ldloc.0
0x1c4e8  brfalse.s loc_1C4F7
0x1c4ea  ldloc.0
0x1c4eb  ldarg.0
0x1c4ec  ldarg.1
0x1c4ed  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1c4f2  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1c4f7  ret
```
