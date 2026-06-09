# Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_BingMapsGeoCode

- ea: `0xac40`
- end: `0xac53`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_BingMapsGeoCode`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xac40`

## string_xrefs

- `0xac4d`: `http://{0}/REST/v1/Locations/{2}?o=xml&amp;key={1}`

## pseudocode

```c

```

## disassembly

```asm
0xac40  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::bingMapsGeoCode
0xac45  brfalse.s loc_AC4D
0xac47  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::bingMapsGeoCode
0xac4c  ret
0xac4d  ldstr    aHttp0RestV1Loc// "http://{0}/REST/v1/Locations/{2}?o=xml&"...
0xac52  ret
```
