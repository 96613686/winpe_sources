# Microsoft.SharePoint.Spx.WebSite.SearchService.Neighborhood::RaisePropertyChanged

- ea: `0x1dc90`
- end: `0x1dca8`
- name: `Microsoft.SharePoint.Spx.WebSite.SearchService.Neighborhood::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1db80`
- `0x1dbc0`
- `0x1dc00`

## callees

- `0x1dc90`

## pseudocode

```c

```

## disassembly

```asm
0x1dc90  ldarg.0
0x1dc91  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.SearchService.Neighborhood::PropertyChanged
0x1dc96  stloc.0
0x1dc97  ldloc.0
0x1dc98  brfalse.s loc_1DCA7
0x1dc9a  ldloc.0
0x1dc9b  ldarg.0
0x1dc9c  ldarg.1
0x1dc9d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1dca2  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1dca7  ret
```
