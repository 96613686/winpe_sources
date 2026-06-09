# Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::.cctor

- ea: `0xac90`
- end: `0xad18`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::.cctor`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0xacbd`: `bing.com/maps`

## pseudocode

```c

```

## disassembly

```asm
0xac90  ldstr    aBingmapkey// "BingMapKey"
0xac95  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.WebConfigManager::GetConfigData(string)
0xac9a  stsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::bingMapKey
0xac9f  ldstr    aMapsource// "MapSource"
0xaca4  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.WebConfigManager::GetConfigData(string)
0xaca9  stsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::mapSource
0xacae  ldstr    aMapsite// "MapSite"
0xacb3  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.WebConfigManager::GetConfigData(string)
0xacb8  stsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::mapSite
0xacbd  ldstr    aBingComMaps// "bing.com/maps"
0xacc2  stsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::defaultMapSite
0xacc7  ldstr    aBingmapsurl// "BingMapsUrl"
0xaccc  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.WebConfigManager::GetConfigData(string)
0xacd1  stsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::bingMapsUrl
0xacd6  ldstr    aBingmapspushpi// "BingMapsPushpin"
0xacdb  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.WebConfigManager::GetConfigData(string)
0xace0  stsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::bingMapsPushpin
0xace5  ldstr    aBingmapsgeocod// "BingMapsGeoCode"
0xacea  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.WebConfigManager::GetConfigData(string)
0xacef  stsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::bingMapsGeoCode
0xacf4  ldstr    aCountryspecifi// "CountrySpecific"
0xacf9  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.WebConfigManager::GetConfigData(string)
0xacfe  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xad03  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xad08  ldstr    aFalse_0// "FALSE"
0xad0d  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xad12  stsfld   bool Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::countryspecific
0xad17  ret
```
