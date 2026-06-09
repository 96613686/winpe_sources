# Microsoft.SharePoint.Spx.WebSite.SearchService.RequestBase::RaisePropertyChanged

- ea: `0x1c7a0`
- end: `0x1c7b8`
- name: `Microsoft.SharePoint.Spx.WebSite.SearchService.RequestBase::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1c650`
- `0x1c690`
- `0x1c6d0`
- `0x1c710`
- `0x1ccc0`
- `0x1cd00`
- `0x1cd40`

## callees

- `0x1c7a0`

## pseudocode

```c

```

## disassembly

```asm
0x1c7a0  ldarg.0
0x1c7a1  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.SearchService.RequestBase::PropertyChanged
0x1c7a6  stloc.0
0x1c7a7  ldloc.0
0x1c7a8  brfalse.s loc_1C7B7
0x1c7aa  ldloc.0
0x1c7ab  ldarg.0
0x1c7ac  ldarg.1
0x1c7ad  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1c7b2  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1c7b7  ret
```
