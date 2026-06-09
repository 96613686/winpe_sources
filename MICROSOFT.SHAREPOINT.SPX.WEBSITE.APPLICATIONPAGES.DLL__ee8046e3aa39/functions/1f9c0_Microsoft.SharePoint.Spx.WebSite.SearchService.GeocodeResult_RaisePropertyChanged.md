# Microsoft.SharePoint.Spx.WebSite.SearchService.GeocodeResult::RaisePropertyChanged

- ea: `0x1f9c0`
- end: `0x1f9d8`
- name: `Microsoft.SharePoint.Spx.WebSite.SearchService.GeocodeResult::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f7b0`
- `0x1f7f0`
- `0x1f830`
- `0x1f870`
- `0x1f8b0`
- `0x1f8f0`
- `0x1f930`

## callees

- `0x1f9c0`

## pseudocode

```c

```

## disassembly

```asm
0x1f9c0  ldarg.0
0x1f9c1  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.SearchService.GeocodeResult::PropertyChanged
0x1f9c6  stloc.0
0x1f9c7  ldloc.0
0x1f9c8  brfalse.s loc_1F9D7
0x1f9ca  ldloc.0
0x1f9cb  ldarg.0
0x1f9cc  ldarg.1
0x1f9cd  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1f9d2  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1f9d7  ret
```
