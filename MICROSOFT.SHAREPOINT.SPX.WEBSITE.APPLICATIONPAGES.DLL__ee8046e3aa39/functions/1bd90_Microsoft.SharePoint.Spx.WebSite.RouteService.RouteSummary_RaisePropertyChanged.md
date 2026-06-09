# Microsoft.SharePoint.Spx.WebSite.RouteService.RouteSummary::RaisePropertyChanged

- ea: `0x1bd90`
- end: `0x1bda8`
- name: `Microsoft.SharePoint.Spx.WebSite.RouteService.RouteSummary::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1bc80`
- `0x1bcc0`
- `0x1bd00`

## callees

- `0x1bd90`

## pseudocode

```c

```

## disassembly

```asm
0x1bd90  ldarg.0
0x1bd91  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.RouteService.RouteSummary::PropertyChanged
0x1bd96  stloc.0
0x1bd97  ldloc.0
0x1bd98  brfalse.s loc_1BDA7
0x1bd9a  ldloc.0
0x1bd9b  ldarg.0
0x1bd9c  ldarg.1
0x1bd9d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1bda2  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1bda7  ret
```
