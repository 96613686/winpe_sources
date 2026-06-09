# Microsoft.SharePoint.Spx.WebSite.ImageryService.ShapeBase::RaisePropertyChanged

- ea: `0x18d30`
- end: `0x18d48`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.ShapeBase::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18f50`
- `0x18fb0`
- `0x18ff0`
- `0x19030`
- `0x19090`
- `0x190d0`
- `0x19130`

## callees

- `0x18d30`

## pseudocode

```c

```

## disassembly

```asm
0x18d30  ldarg.0
0x18d31  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.ImageryService.ShapeBase::PropertyChanged
0x18d36  stloc.0
0x18d37  ldloc.0
0x18d38  brfalse.s loc_18D47
0x18d3a  ldloc.0
0x18d3b  ldarg.0
0x18d3c  ldarg.1
0x18d3d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x18d42  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x18d47  ret
```
