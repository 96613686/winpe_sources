# Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::RaisePropertyChanged

- ea: `0x193d0`
- end: `0x193e8`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x191c0`
- `0x19200`
- `0x19240`
- `0x19280`
- `0x192c0`
- `0x19300`
- `0x19340`

## callees

- `0x193d0`

## pseudocode

```c

```

## disassembly

```asm
0x193d0  ldarg.0
0x193d1  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::PropertyChanged
0x193d6  stloc.0
0x193d7  ldloc.0
0x193d8  brfalse.s loc_193E7
0x193da  ldloc.0
0x193db  ldarg.0
0x193dc  ldarg.1
0x193dd  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x193e2  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x193e7  ret
```
