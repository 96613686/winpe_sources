# Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::set_ZoomLevel

- ea: `0x19340`
- end: `0x1936c`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::set_ZoomLevel`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9a40`
- `0x9b90`

## callees

- `0x19340`
- `0x193d0`

## pseudocode

```c

```

## disassembly

```asm
0x19340  ldarg.0
0x19341  ldflda   valuetype [mscorlib]System.Nullable`1<int32> Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::ZoomLevelField
0x19346  ldarg.1
0x19347  box      valuetype [mscorlib]System.Nullable`1<int32>
0x1934c  constrained. valuetype [mscorlib]System.Nullable`1<int32>
0x19352  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x19357  brtrue.s loc_1936B
0x19359  ldarg.0
0x1935a  ldarg.1
0x1935b  stfld    valuetype [mscorlib]System.Nullable`1<int32> Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::ZoomLevelField
0x19360  ldarg.0
0x19361  ldstr    aZoomlevel// "ZoomLevel"
0x19366  call     instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::RaisePropertyChanged(string propertyName)
0x1936b  ret
```
