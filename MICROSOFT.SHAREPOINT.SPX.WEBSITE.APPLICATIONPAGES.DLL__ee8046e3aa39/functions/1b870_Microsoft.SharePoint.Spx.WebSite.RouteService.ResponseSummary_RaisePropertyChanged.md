# Microsoft.SharePoint.Spx.WebSite.RouteService.ResponseSummary::RaisePropertyChanged

- ea: `0x1b870`
- end: `0x1b888`
- name: `Microsoft.SharePoint.Spx.WebSite.RouteService.ResponseSummary::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1b6e0`
- `0x1b720`
- `0x1b760`
- `0x1b7a0`
- `0x1b7e0`

## callees

- `0x1b870`

## pseudocode

```c

```

## disassembly

```asm
0x1b870  ldarg.0
0x1b871  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.RouteService.ResponseSummary::PropertyChanged
0x1b876  stloc.0
0x1b877  ldloc.0
0x1b878  brfalse.s loc_1B887
0x1b87a  ldloc.0
0x1b87b  ldarg.0
0x1b87c  ldarg.1
0x1b87d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1b882  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1b887  ret
```
