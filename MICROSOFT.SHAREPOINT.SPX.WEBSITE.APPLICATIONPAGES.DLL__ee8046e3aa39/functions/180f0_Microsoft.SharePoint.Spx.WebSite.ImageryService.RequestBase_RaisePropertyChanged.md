# Microsoft.SharePoint.Spx.WebSite.ImageryService.RequestBase::RaisePropertyChanged

- ea: `0x180f0`
- end: `0x18108`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.RequestBase::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x17fa0`
- `0x17fe0`
- `0x18020`
- `0x18060`
- `0x18610`
- `0x18650`
- `0x18690`
- `0x186d0`
- `0x18730`
- `0x18770`

## callees

- `0x180f0`

## pseudocode

```c

```

## disassembly

```asm
0x180f0  ldarg.0
0x180f1  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.ImageryService.RequestBase::PropertyChanged
0x180f6  stloc.0
0x180f7  ldloc.0
0x180f8  brfalse.s loc_18107
0x180fa  ldloc.0
0x180fb  ldarg.0
0x180fc  ldarg.1
0x180fd  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x18102  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x18107  ret
```
