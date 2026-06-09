# Microsoft.SharePoint.Spx.WebSite.RouteService.RouteOptions::RaisePropertyChanged

- ea: `0x1ac00`
- end: `0x1ac18`
- name: `Microsoft.SharePoint.Spx.WebSite.RouteService.RouteOptions::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1aab0`
- `0x1aaf0`
- `0x1ab30`
- `0x1ab70`
- `0x1b4e0`

## callees

- `0x1ac00`

## pseudocode

```c

```

## disassembly

```asm
0x1ac00  ldarg.0
0x1ac01  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.RouteService.RouteOptions::PropertyChanged
0x1ac06  stloc.0
0x1ac07  ldloc.0
0x1ac08  brfalse.s loc_1AC17
0x1ac0a  ldloc.0
0x1ac0b  ldarg.0
0x1ac0c  ldarg.1
0x1ac0d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1ac12  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1ac17  ret
```
