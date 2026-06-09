# Microsoft.SharePoint.Spx.WebSite.SearchService.ResponseBase::RaisePropertyChanged

- ea: `0x1df10`
- end: `0x1df28`
- name: `Microsoft.SharePoint.Spx.WebSite.SearchService.ResponseBase::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1de40`
- `0x1de80`
- `0x1df60`
- `0x1dfa0`

## callees

- `0x1df10`

## pseudocode

```c

```

## disassembly

```asm
0x1df10  ldarg.0
0x1df11  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.SearchService.ResponseBase::PropertyChanged
0x1df16  stloc.0
0x1df17  ldloc.0
0x1df18  brfalse.s loc_1DF27
0x1df1a  ldloc.0
0x1df1b  ldarg.0
0x1df1c  ldarg.1
0x1df1d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1df22  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1df27  ret
```
