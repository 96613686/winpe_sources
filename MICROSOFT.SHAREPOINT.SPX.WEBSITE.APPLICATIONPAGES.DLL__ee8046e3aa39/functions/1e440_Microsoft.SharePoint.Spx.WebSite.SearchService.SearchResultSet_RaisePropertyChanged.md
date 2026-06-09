# Microsoft.SharePoint.Spx.WebSite.SearchService.SearchResultSet::RaisePropertyChanged

- ea: `0x1e440`
- end: `0x1e458`
- name: `Microsoft.SharePoint.Spx.WebSite.SearchService.SearchResultSet::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1e170`
- `0x1e1b0`
- `0x1e1f0`
- `0x1e230`
- `0x1e270`
- `0x1e2b0`
- `0x1e2f0`
- `0x1e330`
- `0x1e370`
- `0x1e3b0`

## callees

- `0x1e440`

## pseudocode

```c

```

## disassembly

```asm
0x1e440  ldarg.0
0x1e441  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.SearchService.SearchResultSet::PropertyChanged
0x1e446  stloc.0
0x1e447  ldloc.0
0x1e448  brfalse.s loc_1E457
0x1e44a  ldloc.0
0x1e44b  ldarg.0
0x1e44c  ldarg.1
0x1e44d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1e452  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1e457  ret
```
