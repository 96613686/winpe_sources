# Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_CountrySpecific

- ea: `0xac60`
- end: `0xac87`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_CountrySpecific`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa380`

## callees

- `0xabe0`
- `0xac60`

## pseudocode

```c

```

## disassembly

```asm
0xac60  call     string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_MapSource()
0xac65  dup
0xac66  stloc.0
0xac67  brfalse.s loc_AC83
0xac69  ldloc.0
0xac6a  ldstr    aBingmaps// "BingMaps"
0xac6f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xac74  brfalse.s loc_AC83
0xac76  ldsfld   bool Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::countryspecific
0xac7b  brtrue.s loc_AC85
0xac7d  ldsfld   bool Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::countryspecific
0xac82  ret
0xac83  ldc.i4.1
0xac84  ret
0xac85  ldc.i4.1
0xac86  ret
```
