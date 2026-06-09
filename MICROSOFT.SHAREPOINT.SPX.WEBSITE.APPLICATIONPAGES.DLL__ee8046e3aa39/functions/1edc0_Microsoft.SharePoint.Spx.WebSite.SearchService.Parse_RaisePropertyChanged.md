# Microsoft.SharePoint.Spx.WebSite.SearchService.Parse::RaisePropertyChanged

- ea: `0x1edc0`
- end: `0x1edd8`
- name: `Microsoft.SharePoint.Spx.WebSite.SearchService.Parse::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ec70`
- `0x1ecb0`
- `0x1ecf0`
- `0x1ed30`

## callees

- `0x1edc0`

## pseudocode

```c

```

## disassembly

```asm
0x1edc0  ldarg.0
0x1edc1  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.SearchService.Parse::PropertyChanged
0x1edc6  stloc.0
0x1edc7  ldloc.0
0x1edc8  brfalse.s loc_1EDD7
0x1edca  ldloc.0
0x1edcb  ldarg.0
0x1edcc  ldarg.1
0x1edcd  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1edd2  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1edd7  ret
```
