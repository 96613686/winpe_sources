# Microsoft.SharePoint.Spx.WebSite.SearchService.FilterExpressionBase::RaisePropertyChanged

- ea: `0x1d970`
- end: `0x1d988`
- name: `Microsoft.SharePoint.Spx.WebSite.SearchService.FilterExpressionBase::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1d9e0`
- `0x1da20`
- `0x1da60`
- `0x1dac0`
- `0x1db00`

## callees

- `0x1d970`

## pseudocode

```c

```

## disassembly

```asm
0x1d970  ldarg.0
0x1d971  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.SearchService.FilterExpressionBase::PropertyChanged
0x1d976  stloc.0
0x1d977  ldloc.0
0x1d978  brfalse.s loc_1D987
0x1d97a  ldloc.0
0x1d97b  ldarg.0
0x1d97c  ldarg.1
0x1d97d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1d982  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1d987  ret
```
