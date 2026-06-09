# Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::set_Latitude

- ea: `0x18b40`
- end: `0x18b61`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::set_Latitude`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9a40`
- `0x9b90`

## callees

- `0x18b40`
- `0x18c10`

## pseudocode

```c

```

## disassembly

```asm
0x18b40  ldarg.0
0x18b41  ldflda   float64 Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::LatitudeField
0x18b46  ldarg.1
0x18b47  call     instance bool [mscorlib]System.Double::Equals(float64)
0x18b4c  brtrue.s loc_18B60
0x18b4e  ldarg.0
0x18b4f  ldarg.1
0x18b50  stfld    float64 Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::LatitudeField
0x18b55  ldarg.0
0x18b56  ldstr    aLatitude_1// "Latitude"
0x18b5b  call     instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::RaisePropertyChanged(string propertyName)
0x18b60  ret
```
