# Microsoft.SharePoint.Spx.WebSite.SearchService.SearchResultBase::RaisePropertyChanged

- ea: `0x1ef80`
- end: `0x1ef98`
- name: `Microsoft.SharePoint.Spx.WebSite.SearchService.SearchResultBase::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `18`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ee30`
- `0x1ee70`
- `0x1eeb0`
- `0x1eef0`
- `0x1f150`
- `0x1f190`
- `0x1f200`
- `0x1f240`
- `0x1f280`
- `0x1f2c0`
- `0x1f300`
- `0x1f340`
- `0x1f380`
- `0x1f3c0`
- `0x1f400`
- `0x1f440`
- `0x1f4a0`
- `0x1f4e0`

## callees

- `0x1ef80`

## pseudocode

```c

```

## disassembly

```asm
0x1ef80  ldarg.0
0x1ef81  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.SearchService.SearchResultBase::PropertyChanged
0x1ef86  stloc.0
0x1ef87  ldloc.0
0x1ef88  brfalse.s loc_1EF97
0x1ef8a  ldloc.0
0x1ef8b  ldarg.0
0x1ef8c  ldarg.1
0x1ef8d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1ef92  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1ef97  ret
```
