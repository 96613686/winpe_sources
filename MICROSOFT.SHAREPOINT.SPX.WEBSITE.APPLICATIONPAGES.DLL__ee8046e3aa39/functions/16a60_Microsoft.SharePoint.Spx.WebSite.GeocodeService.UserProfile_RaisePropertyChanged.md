# Microsoft.SharePoint.Spx.WebSite.GeocodeService.UserProfile::RaisePropertyChanged

- ea: `0x16a60`
- end: `0x16a78`
- name: `Microsoft.SharePoint.Spx.WebSite.GeocodeService.UserProfile::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x16850`
- `0x16890`
- `0x168d0`
- `0x16910`
- `0x16950`
- `0x16990`
- `0x169d0`

## callees

- `0x16a60`

## pseudocode

```c

```

## disassembly

```asm
0x16a60  ldarg.0
0x16a61  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.GeocodeService.UserProfile::PropertyChanged
0x16a66  stloc.0
0x16a67  ldloc.0
0x16a68  brfalse.s loc_16A77
0x16a6a  ldloc.0
0x16a6b  ldarg.0
0x16a6c  ldarg.1
0x16a6d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x16a72  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x16a77  ret
```
