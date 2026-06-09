# Microsoft.SharePoint.Spx.WebSite.SearchService.CategoryCount::RaisePropertyChanged

- ea: `0x1ec00`
- end: `0x1ec18`
- name: `Microsoft.SharePoint.Spx.WebSite.SearchService.CategoryCount::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1eaf0`
- `0x1eb30`
- `0x1eb70`

## callees

- `0x1ec00`

## pseudocode

```c

```

## disassembly

```asm
0x1ec00  ldarg.0
0x1ec01  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.SearchService.CategoryCount::PropertyChanged
0x1ec06  stloc.0
0x1ec07  ldloc.0
0x1ec08  brfalse.s loc_1EC17
0x1ec0a  ldloc.0
0x1ec0b  ldarg.0
0x1ec0c  ldarg.1
0x1ec0d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1ec12  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1ec17  ret
```
