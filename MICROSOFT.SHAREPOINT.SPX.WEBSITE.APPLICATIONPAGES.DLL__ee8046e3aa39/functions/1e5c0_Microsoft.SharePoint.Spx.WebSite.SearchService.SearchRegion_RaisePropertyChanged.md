# Microsoft.SharePoint.Spx.WebSite.SearchService.SearchRegion::RaisePropertyChanged

- ea: `0x1e5c0`
- end: `0x1e5d8`
- name: `Microsoft.SharePoint.Spx.WebSite.SearchService.SearchRegion::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1e4b0`
- `0x1e4f0`
- `0x1e530`

## callees

- `0x1e5c0`

## pseudocode

```c

```

## disassembly

```asm
0x1e5c0  ldarg.0
0x1e5c1  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.SearchService.SearchRegion::PropertyChanged
0x1e5c6  stloc.0
0x1e5c7  ldloc.0
0x1e5c8  brfalse.s loc_1E5D7
0x1e5ca  ldloc.0
0x1e5cb  ldarg.0
0x1e5cc  ldarg.1
0x1e5cd  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1e5d2  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1e5d7  ret
```
