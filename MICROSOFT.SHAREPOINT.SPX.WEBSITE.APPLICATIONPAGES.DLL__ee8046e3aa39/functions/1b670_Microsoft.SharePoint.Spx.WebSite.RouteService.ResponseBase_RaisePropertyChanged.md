# Microsoft.SharePoint.Spx.WebSite.RouteService.ResponseBase::RaisePropertyChanged

- ea: `0x1b670`
- end: `0x1b688`
- name: `Microsoft.SharePoint.Spx.WebSite.RouteService.ResponseBase::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1b5a0`
- `0x1b5e0`
- `0x1b8c0`
- `0x1b900`
- `0x1b960`

## callees

- `0x1b670`

## pseudocode

```c

```

## disassembly

```asm
0x1b670  ldarg.0
0x1b671  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.RouteService.ResponseBase::PropertyChanged
0x1b676  stloc.0
0x1b677  ldloc.0
0x1b678  brfalse.s loc_1B687
0x1b67a  ldloc.0
0x1b67b  ldarg.0
0x1b67c  ldarg.1
0x1b67d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1b682  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1b687  ret
```
