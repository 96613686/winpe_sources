# Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeOptions::RaisePropertyChanged

- ea: `0x16fb0`
- end: `0x16fc8`
- name: `Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeOptions::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x16ee0`
- `0x16f20`

## callees

- `0x16fb0`

## pseudocode

```c

```

## disassembly

```asm
0x16fb0  ldarg.0
0x16fb1  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeOptions::PropertyChanged
0x16fb6  stloc.0
0x16fb7  ldloc.0
0x16fb8  brfalse.s loc_16FC7
0x16fba  ldloc.0
0x16fbb  ldarg.0
0x16fbc  ldarg.1
0x16fbd  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x16fc2  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x16fc7  ret
```
