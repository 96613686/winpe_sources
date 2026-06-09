# Microsoft.SharePoint.Spx.WebSite.GeocodeService.RequestBase::RaisePropertyChanged

- ea: `0x16590`
- end: `0x165a8`
- name: `Microsoft.SharePoint.Spx.WebSite.GeocodeService.RequestBase::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x16440`
- `0x16480`
- `0x164c0`
- `0x16500`
- `0x16ab0`
- `0x16b10`
- `0x16b50`
- `0x16b90`

## callees

- `0x16590`

## pseudocode

```c

```

## disassembly

```asm
0x16590  ldarg.0
0x16591  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.GeocodeService.RequestBase::PropertyChanged
0x16596  stloc.0
0x16597  ldloc.0
0x16598  brfalse.s loc_165A7
0x1659a  ldloc.0
0x1659b  ldarg.0
0x1659c  ldarg.1
0x1659d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x165a2  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x165a7  ret
```
