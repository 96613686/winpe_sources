# Microsoft.SharePoint.Spx.WebSite.Controls.MapPoint::FindLocationsXml

- ea: `0xd170`
- end: `0xd496`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPoint::FindLocationsXml`
- size: `806`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0xb50`

## callees

- `0xa380`
- `0xabe0`
- `0xcf00`
- `0xd170`
- `0xd800`
- `0xd810`
- `0xd830`
- `0xd850`
- `0xd870`
- `0xd890`
- `0xd8b0`
- `0xd8d0`
- `0xd8f0`
- `0xd900`
- `0xd910`
- `0xd920`
- `0xd930`
- `0xd940`

## pseudocode

```c

```

## disassembly

```asm
0xd170  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xd175  stloc.0
0xd176  call     string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_MapSource()
0xd17b  ldstr    aBingmaps// "BingMaps"
0xd180  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd185  brfalse.s loc_D191
0xd187  ldarg.0
0xd188  ldarg.1
0xd189  ldarg.2
0xd18a  ldarg.3
0xd18b  call     string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::FindLocationsXml(string cultureName, string dataSourceName, string countryRegion, string address)
0xd190  ret
0xd191  ldarg.0
0xd192  ldarg.1
0xd193  ldarg.2
0xd194  ldarg.3
0xd195  call     class [mscorlib]System.Collections.ArrayList Microsoft.SharePoint.Spx.WebSite.Controls.MapPoint::FindLocations(string cultureName, string dataSourceName, string countryRegion, string address)
0xd19a  stloc.1
0xd19b  ldloc.0
0xd19c  ldstr    aLocations// "<locations>"
0xd1a1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd1a6  pop
0xd1a7  ldloc.1
0xd1a8  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0xd1ad  stloc.3
0xd1ae  br       loc_D462
0xd1b3  ldloc.3
0xd1b4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xd1b9  castclass Microsoft.SharePoint.Spx.WebSite.Controls.MapPointLocation
0xd1be  stloc.2
0xd1bf  ldloc.0
0xd1c0  ldstr    aLocation// "<location"
0xd1c5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd1ca  pop
0xd1cb  ldloc.0
0xd1cc  ldstr    aScore// " Score=\""
0xd1d1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd1d6  pop
0xd1d7  ldloc.0
0xd1d8  ldloc.2
0xd1d9  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.Controls.MapPointLocation::get_Score()
0xd1de  stloc.s  4
0xd1e0  ldloca.s 4
0xd1e2  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.SharePoint.Spx.WebSite.Controls.MapPoint::xmlNumericCI
0xd1e7  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0xd1ec  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd1f1  pop
0xd1f2  ldloc.0
0xd1f3  ldstr    asc_25ADE// "\""
0xd1f8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd1fd  pop
0xd1fe  ldloc.0
0xd1ff  ldstr    aFormattedaddre// " FormattedAddress=\""
0xd204  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd209  pop
0xd20a  ldloc.0
0xd20b  ldloc.2
0xd20c  callvirt instance string Microsoft.SharePoint.Spx.WebSite.Controls.MapPointLocation::get_FormattedAddress()
0xd211  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::HtmlEncode(string)
0xd216  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd21b  pop
0xd21c  ldloc.0
0xd21d  ldstr    asc_25ADE// "\""
0xd222  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd227  pop
0xd228  ldloc.0
0xd229  ldstr    aAddressline// " AddressLine=\""
0xd22e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd233  pop
0xd234  ldloc.0
0xd235  ldloc.2
0xd236  callvirt instance string Microsoft.SharePoint.Spx.WebSite.Controls.MapPointLocation::get_AddressLine()
0xd23b  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::HtmlEncode(string)
0xd240  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd245  pop
0xd246  ldloc.0
0xd247  ldstr    asc_25ADE// "\""
0xd24c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd251  pop
0xd252  ldloc.0
0xd253  ldstr    aPrimarycity// " PrimaryCity=\""
0xd258  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd25d  pop
0xd25e  ldloc.0
0xd25f  ldloc.2
0xd260  callvirt instance string Microsoft.SharePoint.Spx.WebSite.Controls.MapPointLocation::get_PrimaryCity()
0xd265  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::HtmlEncode(string)
0xd26a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd26f  pop
0xd270  ldloc.0
0xd271  ldstr    asc_25ADE// "\""
0xd276  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd27b  pop
0xd27c  ldloc.0
0xd27d  ldstr    aSecondarycity// " SecondaryCity=\""
0xd282  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd287  pop
0xd288  ldloc.0
0xd289  ldloc.2
0xd28a  callvirt instance string Microsoft.SharePoint.Spx.WebSite.Controls.MapPointLocation::get_SecondaryCity()
0xd28f  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::HtmlEncode(string)
0xd294  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd299  pop
0xd29a  ldloc.0
0xd29b  ldstr    asc_25ADE// "\""
0xd2a0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd2a5  pop
0xd2a6  ldloc.0
0xd2a7  ldstr    aSubdivision// " Subdivision=\""
0xd2ac  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd2b1  pop
0xd2b2  ldloc.0
0xd2b3  ldloc.2
0xd2b4  callvirt instance string Microsoft.SharePoint.Spx.WebSite.Controls.MapPointLocation::get_Subdivision()
0xd2b9  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::HtmlEncode(string)
0xd2be  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd2c3  pop
0xd2c4  ldloc.0
0xd2c5  ldstr    asc_25ADE// "\""
0xd2ca  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd2cf  pop
0xd2d0  ldloc.0
0xd2d1  ldstr    aPostalcode// " PostalCode=\""
0xd2d6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd2db  pop
0xd2dc  ldloc.0
0xd2dd  ldloc.2
0xd2de  callvirt instance string Microsoft.SharePoint.Spx.WebSite.Controls.MapPointLocation::get_PostalCode()
0xd2e3  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::HtmlEncode(string)
0xd2e8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd2ed  pop
0xd2ee  ldloc.0
0xd2ef  ldstr    asc_25ADE// "\""
0xd2f4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd2f9  pop
0xd2fa  ldloc.0
0xd2fb  ldstr    aCountryregion_0// " CountryRegion=\""
0xd300  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd305  pop
0xd306  ldloc.0
0xd307  ldloc.2
0xd308  callvirt instance string Microsoft.SharePoint.Spx.WebSite.Controls.MapPointLocation::get_CountryRegion()
0xd30d  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::HtmlEncode(string)
0xd312  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd317  pop
0xd318  ldloc.0
0xd319  ldstr    asc_25ADE// "\""
0xd31e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd323  pop
0xd324  ldloc.0
0xd325  ldstr    aLatitude// " Latitude=\""
0xd32a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd32f  pop
0xd330  ldloc.0
0xd331  ldloc.2
0xd332  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.Controls.MapPointLocation::get_Latitude()
0xd337  stloc.s  5
0xd339  ldloca.s 5
0xd33b  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.SharePoint.Spx.WebSite.Controls.MapPoint::xmlNumericCI
0xd340  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0xd345  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd34a  pop
0xd34b  ldloc.0
0xd34c  ldstr    asc_25ADE// "\""
0xd351  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd356  pop
0xd357  ldloc.0
0xd358  ldstr    aLongitude// " Longitude=\""
0xd35d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd362  pop
0xd363  ldloc.0
0xd364  ldloc.2
0xd365  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.Controls.MapPointLocation::get_Longitude()
0xd36a  stloc.s  6
0xd36c  ldloca.s 6
0xd36e  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.SharePoint.Spx.WebSite.Controls.MapPoint::xmlNumericCI
0xd373  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0xd378  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd37d  pop
0xd37e  ldloc.0
0xd37f  ldstr    asc_25ADE// "\""
0xd384  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd389  pop
0xd38a  ldloc.0
0xd38b  ldstr    aNorthlatitude// " NorthLatitude=\""
0xd390  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd395  pop
0xd396  ldloc.0
0xd397  ldloc.2
0xd398  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.Controls.MapPointLocation::get_NorthLatitude()
0xd39d  stloc.s  7
0xd39f  ldloca.s 7
0xd3a1  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.SharePoint.Spx.WebSite.Controls.MapPoint::xmlNumericCI
0xd3a6  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0xd3ab  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd3b0  pop
0xd3b1  ldloc.0
0xd3b2  ldstr    asc_25ADE// "\""
0xd3b7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd3bc  pop
0xd3bd  ldloc.0
0xd3be  ldstr    aEastlongitude// " EastLongitude=\""
0xd3c3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd3c8  pop
0xd3c9  ldloc.0
0xd3ca  ldloc.2
0xd3cb  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.Controls.MapPointLocation::get_EastLongitude()
0xd3d0  stloc.s  8
0xd3d2  ldloca.s 8
0xd3d4  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.SharePoint.Spx.WebSite.Controls.MapPoint::xmlNumericCI
0xd3d9  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0xd3de  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd3e3  pop
0xd3e4  ldloc.0
0xd3e5  ldstr    asc_25ADE// "\""
0xd3ea  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd3ef  pop
0xd3f0  ldloc.0
0xd3f1  ldstr    aSouthlatitude// " SouthLatitude=\""
0xd3f6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd3fb  pop
0xd3fc  ldloc.0
0xd3fd  ldloc.2
0xd3fe  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.Controls.MapPointLocation::get_SouthLatitude()
0xd403  stloc.s  9
0xd405  ldloca.s 9
0xd407  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.SharePoint.Spx.WebSite.Controls.MapPoint::xmlNumericCI
0xd40c  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0xd411  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd416  pop
0xd417  ldloc.0
0xd418  ldstr    asc_25ADE// "\""
0xd41d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd422  pop
0xd423  ldloc.0
0xd424  ldstr    aWestlongitude// " WestLongitude=\""
0xd429  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd42e  pop
0xd42f  ldloc.0
0xd430  ldloc.2
0xd431  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.Controls.MapPointLocation::get_WestLongitude()
0xd436  stloc.s  0xA
0xd438  ldloca.s 0xA
0xd43a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.SharePoint.Spx.WebSite.Controls.MapPoint::xmlNumericCI
0xd43f  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0xd444  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd449  pop
0xd44a  ldloc.0
0xd44b  ldstr    asc_25ADE// "\""
0xd450  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd455  pop
0xd456  ldloc.0
0xd457  ldstr    asc_25EE0// "/>"
0xd45c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd461  pop
0xd462  ldloc.3
0xd463  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd468  brtrue   loc_D1B3
0xd46d  leave.s  loc_D483
0xd46f  ldloc.3
0xd470  isinst   [mscorlib]System.IDisposable
0xd475  stloc.s  0xB
0xd477  ldloc.s  0xB
0xd479  brfalse.s loc_D482
0xd47b  ldloc.s  0xB
0xd47d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd482  endfinally
0xd483  ldloc.0
0xd484  ldstr    aLocations_0// "</locations>"
0xd489  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd48e  pop
0xd48f  ldloc.0
0xd490  callvirt instance string [mscorlib]System.Object::ToString()
0xd495  ret
```
