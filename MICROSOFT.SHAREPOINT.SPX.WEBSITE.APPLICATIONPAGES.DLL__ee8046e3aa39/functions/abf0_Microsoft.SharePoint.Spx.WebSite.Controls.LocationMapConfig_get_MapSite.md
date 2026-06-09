# Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_MapSite

- ea: `0xabf0`
- end: `0xac1f`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_MapSite`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xc4b0`

## callees

- `0xabe0`
- `0xabf0`

## pseudocode

```c

```

## disassembly

```asm
0xabf0  call     string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_MapSource()
0xabf5  dup
0xabf6  stloc.0
0xabf7  brfalse.s loc_AC19
0xabf9  ldloc.0
0xabfa  ldstr    aBingmaps// "BingMaps"
0xabff  call     bool [mscorlib]System.String::op_Equality(string, string)
0xac04  brfalse.s loc_AC19
0xac06  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::mapSite
0xac0b  brtrue.s loc_AC13
0xac0d  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::defaultMapSite
0xac12  ret
0xac13  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::mapSite
0xac18  ret
0xac19  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::defaultMapSite
0xac1e  ret
```
