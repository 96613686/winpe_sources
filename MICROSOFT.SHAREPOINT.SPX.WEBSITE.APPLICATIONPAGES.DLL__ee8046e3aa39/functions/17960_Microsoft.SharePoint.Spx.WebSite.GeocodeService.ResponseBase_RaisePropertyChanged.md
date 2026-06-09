# Microsoft.SharePoint.Spx.WebSite.GeocodeService.ResponseBase::RaisePropertyChanged

- ea: `0x17960`
- end: `0x17978`
- name: `Microsoft.SharePoint.Spx.WebSite.GeocodeService.ResponseBase::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x17890`
- `0x178d0`
- `0x17bb0`

## callees

- `0x17960`

## pseudocode

```c

```

## disassembly

```asm
0x17960  ldarg.0
0x17961  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.GeocodeService.ResponseBase::PropertyChanged
0x17966  stloc.0
0x17967  ldloc.0
0x17968  brfalse.s loc_17977
0x1796a  ldloc.0
0x1796b  ldarg.0
0x1796c  ldarg.1
0x1796d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x17972  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x17977  ret
```
