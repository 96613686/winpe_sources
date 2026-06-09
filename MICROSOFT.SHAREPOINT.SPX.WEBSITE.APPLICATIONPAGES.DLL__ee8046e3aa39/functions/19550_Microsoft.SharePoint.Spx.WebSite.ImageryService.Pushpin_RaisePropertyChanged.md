# Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin::RaisePropertyChanged

- ea: `0x19550`
- end: `0x19568`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x19440`
- `0x19480`
- `0x194c0`

## callees

- `0x19550`

## pseudocode

```c

```

## disassembly

```asm
0x19550  ldarg.0
0x19551  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin::PropertyChanged
0x19556  stloc.0
0x19557  ldloc.0
0x19558  brfalse.s loc_19567
0x1955a  ldloc.0
0x1955b  ldarg.0
0x1955c  ldarg.1
0x1955d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x19562  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x19567  ret
```
