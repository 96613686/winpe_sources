# Microsoft.SharePoint.Spx.WebSite.SearchService.UserProfile::RaisePropertyChanged

- ea: `0x1cc70`
- end: `0x1cc88`
- name: `Microsoft.SharePoint.Spx.WebSite.SearchService.UserProfile::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ca60`
- `0x1caa0`
- `0x1cae0`
- `0x1cb20`
- `0x1cb60`
- `0x1cba0`
- `0x1cbe0`

## callees

- `0x1cc70`

## pseudocode

```c

```

## disassembly

```asm
0x1cc70  ldarg.0
0x1cc71  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.SearchService.UserProfile::PropertyChanged
0x1cc76  stloc.0
0x1cc77  ldloc.0
0x1cc78  brfalse.s loc_1CC87
0x1cc7a  ldloc.0
0x1cc7b  ldarg.0
0x1cc7c  ldarg.1
0x1cc7d  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1cc82  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1cc87  ret
```
