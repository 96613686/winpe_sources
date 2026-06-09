# Microsoft.SharePoint.Spx.WebSite.RouteService.UserProfile::RaisePropertyChanged

- ea: `0x1a900`
- end: `0x1a918`
- name: `Microsoft.SharePoint.Spx.WebSite.RouteService.UserProfile::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a6f0`
- `0x1a730`
- `0x1a770`
- `0x1a7b0`
- `0x1a7f0`
- `0x1a830`
- `0x1a870`

## callees

- `0x1a900`

## pseudocode

```c

```

## disassembly

```asm
0x1a900  ldarg.0
0x1a901  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.RouteService.UserProfile::PropertyChanged
0x1a906  stloc.0
0x1a907  ldloc.0
0x1a908  brfalse.s loc_1A917
0x1a90a  ldloc.0
0x1a90b  ldarg.0
0x1a90c  ldarg.1
0x1a90d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1a912  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1a917  ret
```
