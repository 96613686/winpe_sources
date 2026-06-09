# Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryMetadataOptions::RaisePropertyChanged

- ea: `0x18980`
- end: `0x18998`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryMetadataOptions::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x187f0`
- `0x18830`
- `0x18870`
- `0x188b0`
- `0x188f0`

## callees

- `0x18980`

## pseudocode

```c

```

## disassembly

```asm
0x18980  ldarg.0
0x18981  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryMetadataOptions::PropertyChanged
0x18986  stloc.0
0x18987  ldloc.0
0x18988  brfalse.s loc_18997
0x1898a  ldloc.0
0x1898b  ldarg.0
0x1898c  ldarg.1
0x1898d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x18992  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x18997  ret
```
