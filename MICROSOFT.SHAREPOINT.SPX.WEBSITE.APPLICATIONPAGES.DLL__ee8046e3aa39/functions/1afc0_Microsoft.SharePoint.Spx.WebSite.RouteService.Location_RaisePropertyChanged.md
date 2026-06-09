# Microsoft.SharePoint.Spx.WebSite.RouteService.Location::RaisePropertyChanged

- ea: `0x1afc0`
- end: `0x1afd8`
- name: `Microsoft.SharePoint.Spx.WebSite.RouteService.Location::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1aeb0`
- `0x1aef0`
- `0x1af30`
- `0x1b010`
- `0x1b290`

## callees

- `0x1afc0`

## pseudocode

```c

```

## disassembly

```asm
0x1afc0  ldarg.0
0x1afc1  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.RouteService.Location::PropertyChanged
0x1afc6  stloc.0
0x1afc7  ldloc.0
0x1afc8  brfalse.s loc_1AFD7
0x1afca  ldloc.0
0x1afcb  ldarg.0
0x1afcc  ldarg.1
0x1afcd  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1afd2  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1afd7  ret
```
