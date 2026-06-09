# Microsoft.SharePoint.Spx.WebSite.SearchService.ShapeBase::RaisePropertyChanged

- ea: `0x1d500`
- end: `0x1d518`
- name: `Microsoft.SharePoint.Spx.WebSite.SearchService.ShapeBase::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1d720`
- `0x1d760`
- `0x1d7c0`
- `0x1d820`
- `0x1d860`
- `0x1d8a0`

## callees

- `0x1d500`

## pseudocode

```c

```

## disassembly

```asm
0x1d500  ldarg.0
0x1d501  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.SearchService.ShapeBase::PropertyChanged
0x1d506  stloc.0
0x1d507  ldloc.0
0x1d508  brfalse.s loc_1D517
0x1d50a  ldloc.0
0x1d50b  ldarg.0
0x1d50c  ldarg.1
0x1d50d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1d512  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1d517  ret
```
