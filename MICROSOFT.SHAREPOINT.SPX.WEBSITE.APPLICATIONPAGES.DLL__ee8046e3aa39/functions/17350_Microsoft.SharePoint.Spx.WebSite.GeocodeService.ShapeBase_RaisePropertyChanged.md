# Microsoft.SharePoint.Spx.WebSite.GeocodeService.ShapeBase::RaisePropertyChanged

- ea: `0x17350`
- end: `0x17368`
- name: `Microsoft.SharePoint.Spx.WebSite.GeocodeService.ShapeBase::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x17570`
- `0x175b0`
- `0x17610`
- `0x17650`
- `0x17690`
- `0x176f0`

## callees

- `0x17350`

## pseudocode

```c

```

## disassembly

```asm
0x17350  ldarg.0
0x17351  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.GeocodeService.ShapeBase::PropertyChanged
0x17356  stloc.0
0x17357  ldloc.0
0x17358  brfalse.s loc_17367
0x1735a  ldloc.0
0x1735b  ldarg.0
0x1735c  ldarg.1
0x1735d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x17362  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x17367  ret
```
