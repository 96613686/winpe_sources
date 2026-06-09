# Microsoft.SharePoint.Spx.WebSite.SearchService.SearchOptions::RaisePropertyChanged

- ea: `0x1d020`
- end: `0x1d038`
- name: `Microsoft.SharePoint.Spx.WebSite.SearchService.SearchOptions::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1cdd0`
- `0x1ce10`
- `0x1ce50`
- `0x1ce90`
- `0x1ced0`
- `0x1cf10`
- `0x1cf50`
- `0x1cf90`

## callees

- `0x1d020`

## pseudocode

```c

```

## disassembly

```asm
0x1d020  ldarg.0
0x1d021  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.SearchService.SearchOptions::PropertyChanged
0x1d026  stloc.0
0x1d027  ldloc.0
0x1d028  brfalse.s loc_1D037
0x1d02a  ldloc.0
0x1d02b  ldarg.0
0x1d02c  ldarg.1
0x1d02d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1d032  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1d037  ret
```
