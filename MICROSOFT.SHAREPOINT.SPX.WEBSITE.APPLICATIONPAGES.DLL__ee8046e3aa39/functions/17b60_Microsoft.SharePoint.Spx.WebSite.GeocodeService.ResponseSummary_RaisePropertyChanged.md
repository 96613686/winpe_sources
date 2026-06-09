# Microsoft.SharePoint.Spx.WebSite.GeocodeService.ResponseSummary::RaisePropertyChanged

- ea: `0x17b60`
- end: `0x17b78`
- name: `Microsoft.SharePoint.Spx.WebSite.GeocodeService.ResponseSummary::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x179d0`
- `0x17a10`
- `0x17a50`
- `0x17a90`
- `0x17ad0`

## callees

- `0x17b60`

## pseudocode

```c

```

## disassembly

```asm
0x17b60  ldarg.0
0x17b61  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.GeocodeService.ResponseSummary::PropertyChanged
0x17b66  stloc.0
0x17b67  ldloc.0
0x17b68  brfalse.s loc_17B77
0x17b6a  ldloc.0
0x17b6b  ldarg.0
0x17b6c  ldarg.1
0x17b6d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x17b72  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x17b77  ret
```
