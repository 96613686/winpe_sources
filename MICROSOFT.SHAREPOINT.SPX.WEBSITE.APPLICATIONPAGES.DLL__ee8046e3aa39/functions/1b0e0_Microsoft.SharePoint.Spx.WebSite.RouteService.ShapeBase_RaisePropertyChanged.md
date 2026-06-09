# Microsoft.SharePoint.Spx.WebSite.RouteService.ShapeBase::RaisePropertyChanged

- ea: `0x1b0e0`
- end: `0x1b0f8`
- name: `Microsoft.SharePoint.Spx.WebSite.RouteService.ShapeBase::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1b300`
- `0x1b340`
- `0x1b3a0`
- `0x1b3e0`
- `0x1b420`
- `0x1b480`

## callees

- `0x1b0e0`

## pseudocode

```c

```

## disassembly

```asm
0x1b0e0  ldarg.0
0x1b0e1  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.RouteService.ShapeBase::PropertyChanged
0x1b0e6  stloc.0
0x1b0e7  ldloc.0
0x1b0e8  brfalse.s loc_1B0F7
0x1b0ea  ldloc.0
0x1b0eb  ldarg.0
0x1b0ec  ldarg.1
0x1b0ed  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1b0f2  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1b0f7  ret
```
