# Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::RaisePropertyChanged

- ea: `0x18c10`
- end: `0x18c28`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18b00`
- `0x18b40`
- `0x18b80`
- `0x18c60`
- `0x18ee0`

## callees

- `0x18c10`

## pseudocode

```c

```

## disassembly

```asm
0x18c10  ldarg.0
0x18c11  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::PropertyChanged
0x18c16  stloc.0
0x18c17  ldloc.0
0x18c18  brfalse.s loc_18C27
0x18c1a  ldloc.0
0x18c1b  ldarg.0
0x18c1c  ldarg.1
0x18c1d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x18c22  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x18c27  ret
```
