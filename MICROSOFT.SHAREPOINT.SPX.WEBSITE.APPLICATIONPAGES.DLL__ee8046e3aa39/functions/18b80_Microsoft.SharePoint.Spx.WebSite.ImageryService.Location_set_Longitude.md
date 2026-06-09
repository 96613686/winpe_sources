# Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::set_Longitude

- ea: `0x18b80`
- end: `0x18ba1`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::set_Longitude`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9a40`
- `0x9b90`

## callees

- `0x18b80`
- `0x18c10`

## pseudocode

```c

```

## disassembly

```asm
0x18b80  ldarg.0
0x18b81  ldflda   float64 Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::LongitudeField
0x18b86  ldarg.1
0x18b87  call     instance bool [mscorlib]System.Double::Equals(float64)
0x18b8c  brtrue.s loc_18BA0
0x18b8e  ldarg.0
0x18b8f  ldarg.1
0x18b90  stfld    float64 Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::LongitudeField
0x18b95  ldarg.0
0x18b96  ldstr    aLongitude_1// "Longitude"
0x18b9b  call     instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::RaisePropertyChanged(string propertyName)
0x18ba0  ret
```
