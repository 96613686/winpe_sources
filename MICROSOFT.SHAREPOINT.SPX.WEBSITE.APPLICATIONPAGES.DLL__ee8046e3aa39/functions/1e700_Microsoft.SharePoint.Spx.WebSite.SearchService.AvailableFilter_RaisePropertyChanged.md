# Microsoft.SharePoint.Spx.WebSite.SearchService.AvailableFilter::RaisePropertyChanged

- ea: `0x1e700`
- end: `0x1e718`
- name: `Microsoft.SharePoint.Spx.WebSite.SearchService.AvailableFilter::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1e630`
- `0x1e670`
- `0x1e750`
- `0x1ea30`
- `0x1ea70`

## callees

- `0x1e700`

## pseudocode

```c

```

## disassembly

```asm
0x1e700  ldarg.0
0x1e701  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.SearchService.AvailableFilter::PropertyChanged
0x1e706  stloc.0
0x1e707  ldloc.0
0x1e708  brfalse.s loc_1E717
0x1e70a  ldloc.0
0x1e70b  ldarg.0
0x1e70c  ldarg.1
0x1e70d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1e712  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1e717  ret
```
