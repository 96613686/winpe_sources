# Microsoft.SharePoint.Spx.WebSite.RouteService.RouteResult::RaisePropertyChanged

- ea: `0x1baf0`
- end: `0x1bb08`
- name: `Microsoft.SharePoint.Spx.WebSite.RouteService.RouteResult::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1b9e0`
- `0x1ba20`
- `0x1ba60`

## callees

- `0x1baf0`

## pseudocode

```c

```

## disassembly

```asm
0x1baf0  ldarg.0
0x1baf1  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.RouteService.RouteResult::PropertyChanged
0x1baf6  stloc.0
0x1baf7  ldloc.0
0x1baf8  brfalse.s loc_1BB07
0x1bafa  ldloc.0
0x1bafb  ldarg.0
0x1bafc  ldarg.1
0x1bafd  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1bb02  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1bb07  ret
```
