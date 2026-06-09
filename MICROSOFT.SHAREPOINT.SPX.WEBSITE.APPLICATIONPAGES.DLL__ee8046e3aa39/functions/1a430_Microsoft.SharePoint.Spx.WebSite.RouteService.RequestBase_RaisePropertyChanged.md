# Microsoft.SharePoint.Spx.WebSite.RouteService.RequestBase::RaisePropertyChanged

- ea: `0x1a430`
- end: `0x1a448`
- name: `Microsoft.SharePoint.Spx.WebSite.RouteService.RequestBase::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a2e0`
- `0x1a320`
- `0x1a360`
- `0x1a3a0`
- `0x1a950`
- `0x1a990`
- `0x1a9f0`
- `0x1aa30`

## callees

- `0x1a430`

## pseudocode

```c

```

## disassembly

```asm
0x1a430  ldarg.0
0x1a431  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.RouteService.RequestBase::PropertyChanged
0x1a436  stloc.0
0x1a437  ldloc.0
0x1a438  brfalse.s loc_1A447
0x1a43a  ldloc.0
0x1a43b  ldarg.0
0x1a43c  ldarg.1
0x1a43d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1a442  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1a447  ret
```
