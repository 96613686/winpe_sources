# Microsoft.SharePoint.Spx.WebSite.SearchService.ResponseSummary::RaisePropertyChanged

- ea: `0x1f710`
- end: `0x1f728`
- name: `Microsoft.SharePoint.Spx.WebSite.SearchService.ResponseSummary::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f580`
- `0x1f5c0`
- `0x1f600`
- `0x1f640`
- `0x1f680`

## callees

- `0x1f710`

## pseudocode

```c

```

## disassembly

```asm
0x1f710  ldarg.0
0x1f711  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.SearchService.ResponseSummary::PropertyChanged
0x1f716  stloc.0
0x1f717  ldloc.0
0x1f718  brfalse.s loc_1F727
0x1f71a  ldloc.0
0x1f71b  ldarg.0
0x1f71c  ldarg.1
0x1f71d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1f722  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1f727  ret
```
