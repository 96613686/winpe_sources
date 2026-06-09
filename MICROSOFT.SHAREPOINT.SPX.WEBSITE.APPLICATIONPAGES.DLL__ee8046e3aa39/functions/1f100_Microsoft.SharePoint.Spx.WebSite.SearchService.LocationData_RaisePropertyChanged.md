# Microsoft.SharePoint.Spx.WebSite.SearchService.LocationData::RaisePropertyChanged

- ea: `0x1f100`
- end: `0x1f118`
- name: `Microsoft.SharePoint.Spx.WebSite.SearchService.LocationData::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1eff0`
- `0x1f030`
- `0x1f070`

## callees

- `0x1f100`

## pseudocode

```c

```

## disassembly

```asm
0x1f100  ldarg.0
0x1f101  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.SearchService.LocationData::PropertyChanged
0x1f106  stloc.0
0x1f107  ldloc.0
0x1f108  brfalse.s loc_1F117
0x1f10a  ldloc.0
0x1f10b  ldarg.0
0x1f10c  ldarg.1
0x1f10d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1f112  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1f117  ret
```
