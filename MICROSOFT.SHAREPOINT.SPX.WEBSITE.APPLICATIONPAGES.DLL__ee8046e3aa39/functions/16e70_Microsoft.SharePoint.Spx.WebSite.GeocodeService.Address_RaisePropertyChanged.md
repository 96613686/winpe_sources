# Microsoft.SharePoint.Spx.WebSite.GeocodeService.Address::RaisePropertyChanged

- ea: `0x16e70`
- end: `0x16e88`
- name: `Microsoft.SharePoint.Spx.WebSite.GeocodeService.Address::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x16c20`
- `0x16c60`
- `0x16ca0`
- `0x16ce0`
- `0x16d20`
- `0x16d60`
- `0x16da0`
- `0x16de0`

## callees

- `0x16e70`

## pseudocode

```c

```

## disassembly

```asm
0x16e70  ldarg.0
0x16e71  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.GeocodeService.Address::PropertyChanged
0x16e76  stloc.0
0x16e77  ldloc.0
0x16e78  brfalse.s loc_16E87
0x16e7a  ldloc.0
0x16e7b  ldarg.0
0x16e7c  ldarg.1
0x16e7d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x16e82  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x16e87  ret
```
