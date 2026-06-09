# Microsoft.SharePoint.Spx.WebSite.GeocodeService.Credentials::RaisePropertyChanged

- ea: `0x166d0`
- end: `0x166e8`
- name: `Microsoft.SharePoint.Spx.WebSite.GeocodeService.Credentials::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x16600`
- `0x16640`

## callees

- `0x166d0`

## pseudocode

```c

```

## disassembly

```asm
0x166d0  ldarg.0
0x166d1  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.GeocodeService.Credentials::PropertyChanged
0x166d6  stloc.0
0x166d7  ldloc.0
0x166d8  brfalse.s loc_166E7
0x166da  ldloc.0
0x166db  ldarg.0
0x166dc  ldarg.1
0x166dd  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x166e2  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x166e7  ret
```
