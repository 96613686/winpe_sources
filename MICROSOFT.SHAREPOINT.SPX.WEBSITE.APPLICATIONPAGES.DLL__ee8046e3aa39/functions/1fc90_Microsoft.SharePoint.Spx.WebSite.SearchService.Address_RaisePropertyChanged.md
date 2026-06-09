# Microsoft.SharePoint.Spx.WebSite.SearchService.Address::RaisePropertyChanged

- ea: `0x1fc90`
- end: `0x1fca8`
- name: `Microsoft.SharePoint.Spx.WebSite.SearchService.Address::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1fa40`
- `0x1fa80`
- `0x1fac0`
- `0x1fb00`
- `0x1fb40`
- `0x1fb80`
- `0x1fbc0`
- `0x1fc00`

## callees

- `0x1fc90`

## pseudocode

```c

```

## disassembly

```asm
0x1fc90  ldarg.0
0x1fc91  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.SearchService.Address::PropertyChanged
0x1fc96  stloc.0
0x1fc97  ldloc.0
0x1fc98  brfalse.s loc_1FCA7
0x1fc9a  ldloc.0
0x1fc9b  ldarg.0
0x1fc9c  ldarg.1
0x1fc9d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1fca2  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1fca7  ret
```
