# Microsoft.SharePoint.Spx.WebSite.GeocodeService.Location::set_Latitude

- ea: `0x17160`
- end: `0x17181`
- name: `Microsoft.SharePoint.Spx.WebSite.GeocodeService.Location::set_Latitude`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xa1e0`

## callees

- `0x17160`
- `0x17230`

## pseudocode

```c

```

## disassembly

```asm
0x17160  ldarg.0
0x17161  ldflda   float64 Microsoft.SharePoint.Spx.WebSite.GeocodeService.Location::LatitudeField
0x17166  ldarg.1
0x17167  call     instance bool [mscorlib]System.Double::Equals(float64)
0x1716c  brtrue.s loc_17180
0x1716e  ldarg.0
0x1716f  ldarg.1
0x17170  stfld    float64 Microsoft.SharePoint.Spx.WebSite.GeocodeService.Location::LatitudeField
0x17175  ldarg.0
0x17176  ldstr    aLatitude_1// "Latitude"
0x1717b  call     instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.Location::RaisePropertyChanged(string propertyName)
0x17180  ret
```
