# Microsoft.SharePoint.Spx.WebSite.ImageryService.ResponseSummary::RaisePropertyChanged

- ea: `0x198b0`
- end: `0x198c8`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.ResponseSummary::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x19720`
- `0x19760`
- `0x197a0`
- `0x197e0`
- `0x19820`

## callees

- `0x198b0`

## pseudocode

```c

```

## disassembly

```asm
0x198b0  ldarg.0
0x198b1  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.ImageryService.ResponseSummary::PropertyChanged
0x198b6  stloc.0
0x198b7  ldloc.0
0x198b8  brfalse.s loc_198C7
0x198ba  ldloc.0
0x198bb  ldarg.0
0x198bc  ldarg.1
0x198bd  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x198c2  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x198c7  ret
```
