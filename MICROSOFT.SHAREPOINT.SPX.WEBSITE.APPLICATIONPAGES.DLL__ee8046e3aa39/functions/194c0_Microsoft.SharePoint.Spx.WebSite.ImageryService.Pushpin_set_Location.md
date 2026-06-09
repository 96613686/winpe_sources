# Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin::set_Location

- ea: `0x194c0`
- end: `0x194e1`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin::set_Location`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9a40`
- `0x9b90`

## callees

- `0x194c0`
- `0x19550`

## pseudocode

```c

```

## disassembly

```asm
0x194c0  ldarg.0
0x194c1  ldfld    class Microsoft.SharePoint.Spx.WebSite.ImageryService.Location Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin::LocationField
0x194c6  ldarg.1
0x194c7  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x194cc  brtrue.s loc_194E0
0x194ce  ldarg.0
0x194cf  ldarg.1
0x194d0  stfld    class Microsoft.SharePoint.Spx.WebSite.ImageryService.Location Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin::LocationField
0x194d5  ldarg.0
0x194d6  ldstr    aLocation_0// "Location"
0x194db  call     instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin::RaisePropertyChanged(string propertyName)
0x194e0  ret
```
