# Microsoft.SharePoint.Spx.WebSite.ImageryService.UserProfile::RaisePropertyChanged

- ea: `0x185c0`
- end: `0x185d8`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.UserProfile::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x183b0`
- `0x183f0`
- `0x18430`
- `0x18470`
- `0x184b0`
- `0x184f0`
- `0x18530`

## callees

- `0x185c0`

## pseudocode

```c

```

## disassembly

```asm
0x185c0  ldarg.0
0x185c1  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.ImageryService.UserProfile::PropertyChanged
0x185c6  stloc.0
0x185c7  ldloc.0
0x185c8  brfalse.s loc_185D7
0x185ca  ldloc.0
0x185cb  ldarg.0
0x185cc  ldarg.1
0x185cd  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x185d2  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x185d7  ret
```
