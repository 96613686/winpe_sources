# Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryMetadataResult::RaisePropertyChanged

- ea: `0x19bb0`
- end: `0x19bc8`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryMetadataResult::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x199e0`
- `0x19a20`
- `0x19a60`
- `0x19aa0`
- `0x19ae0`
- `0x19b20`
- `0x19ea0`
- `0x19ee0`
- `0x19f20`

## callees

- `0x19bb0`

## pseudocode

```c

```

## disassembly

```asm
0x19bb0  ldarg.0
0x19bb1  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryMetadataResult::PropertyChanged
0x19bb6  stloc.0
0x19bb7  ldloc.0
0x19bb8  brfalse.s loc_19BC7
0x19bba  ldloc.0
0x19bbb  ldarg.0
0x19bbc  ldarg.1
0x19bbd  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x19bc2  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x19bc7  ret
```
