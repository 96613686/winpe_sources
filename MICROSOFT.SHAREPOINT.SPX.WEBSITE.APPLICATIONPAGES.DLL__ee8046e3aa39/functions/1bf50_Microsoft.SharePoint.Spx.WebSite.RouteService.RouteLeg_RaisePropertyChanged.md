# Microsoft.SharePoint.Spx.WebSite.RouteService.RouteLeg::RaisePropertyChanged

- ea: `0x1bf50`
- end: `0x1bf68`
- name: `Microsoft.SharePoint.Spx.WebSite.RouteService.RouteLeg::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1be00`
- `0x1be40`
- `0x1be80`
- `0x1bec0`

## callees

- `0x1bf50`

## pseudocode

```c

```

## disassembly

```asm
0x1bf50  ldarg.0
0x1bf51  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.RouteService.RouteLeg::PropertyChanged
0x1bf56  stloc.0
0x1bf57  ldloc.0
0x1bf58  brfalse.s loc_1BF67
0x1bf5a  ldloc.0
0x1bf5b  ldarg.0
0x1bf5c  ldarg.1
0x1bf5d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1bf62  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1bf67  ret
```
