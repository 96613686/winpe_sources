# Microsoft.SharePoint.Spx.WebSite.GeocodeService.Location::RaisePropertyChanged

- ea: `0x17230`
- end: `0x17248`
- name: `Microsoft.SharePoint.Spx.WebSite.GeocodeService.Location::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x17120`
- `0x17160`
- `0x171a0`
- `0x17280`
- `0x17500`

## callees

- `0x17230`

## pseudocode

```c

```

## disassembly

```asm
0x17230  ldarg.0
0x17231  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.GeocodeService.Location::PropertyChanged
0x17236  stloc.0
0x17237  ldloc.0
0x17238  brfalse.s loc_17247
0x1723a  ldloc.0
0x1723b  ldarg.0
0x1723c  ldarg.1
0x1723d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x17242  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x17247  ret
```
