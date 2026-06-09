# Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult::RaisePropertyChanged

- ea: `0x17e50`
- end: `0x17e68`
- name: `Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x17c40`
- `0x17c80`
- `0x17cc0`
- `0x17d00`
- `0x17d40`
- `0x17d80`
- `0x17dc0`

## callees

- `0x17e50`

## pseudocode

```c

```

## disassembly

```asm
0x17e50  ldarg.0
0x17e51  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult::PropertyChanged
0x17e56  stloc.0
0x17e57  ldloc.0
0x17e58  brfalse.s loc_17E67
0x17e5a  ldloc.0
0x17e5b  ldarg.0
0x17e5c  ldarg.1
0x17e5d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x17e62  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x17e67  ret
```
