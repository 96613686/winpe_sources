# Microsoft.SharePoint.Spx.WebSite.ImageryService.ResponseBase::RaisePropertyChanged

- ea: `0x196b0`
- end: `0x196c8`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.ResponseBase::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x195e0`
- `0x19620`
- `0x19900`
- `0x19960`

## callees

- `0x196b0`

## pseudocode

```c

```

## disassembly

```asm
0x196b0  ldarg.0
0x196b1  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.ImageryService.ResponseBase::PropertyChanged
0x196b6  stloc.0
0x196b7  ldloc.0
0x196b8  brfalse.s loc_196C7
0x196ba  ldloc.0
0x196bb  ldarg.0
0x196bc  ldarg.1
0x196bd  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x196c2  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x196c7  ret
```
