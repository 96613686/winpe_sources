# Microsoft.SharePoint.Spx.WebSite.SearchService.Location::RaisePropertyChanged

- ea: `0x1d3e0`
- end: `0x1d3f8`
- name: `Microsoft.SharePoint.Spx.WebSite.SearchService.Location::RaisePropertyChanged`
- size: `24`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1d2d0`
- `0x1d310`
- `0x1d350`
- `0x1d430`
- `0x1d6b0`

## callees

- `0x1d3e0`

## pseudocode

```c

```

## disassembly

```asm
0x1d3e0  ldarg.0
0x1d3e1  ldfld    class [System]System.ComponentModel.PropertyChangedEventHandler Microsoft.SharePoint.Spx.WebSite.SearchService.Location::PropertyChanged
0x1d3e6  stloc.0
0x1d3e7  ldloc.0
0x1d3e8  brfalse.s loc_1D3F7
0x1d3ea  ldloc.0
0x1d3eb  ldarg.0
0x1d3ec  ldarg.1
0x1d3ed  newobj   instance void [System]System.ComponentModel.PropertyChangedEventArgs::.ctor(string)
0x1d3f2  callvirt instance void [System]System.ComponentModel.PropertyChangedEventHandler::Invoke(object, class [System]System.ComponentModel.PropertyChangedEventArgs)
0x1d3f7  ret
```
