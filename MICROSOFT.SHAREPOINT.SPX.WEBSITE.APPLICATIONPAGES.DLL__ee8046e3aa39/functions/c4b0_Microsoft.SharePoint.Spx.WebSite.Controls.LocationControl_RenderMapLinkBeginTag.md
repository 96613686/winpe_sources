# Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::RenderMapLinkBeginTag

- ea: `0xc4b0`
- end: `0xc6a5`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::RenderMapLinkBeginTag`
- size: `501`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0xba60`

## callees

- `0xabe0`
- `0xabf0`
- `0xae30`
- `0xb0c0`
- `0xb140`
- `0xbfb0`
- `0xc020`
- `0xc4b0`
- `0xfa30`
- `0xfa50`
- `0xfc00`
- `0xfc40`
- `0xfde0`
- `0xfe00`
- `0xfe40`
- `0xfe60`

## pseudocode

```c

```

## disassembly

```asm
0xc4b0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xc4b5  stloc.0
0xc4b6  ldloc.0
0xc4b7  ldstr    aHttp// "http://"
0xc4bc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc4c1  pop
0xc4c2  call     string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_MapSource()
0xc4c7  dup
0xc4c8  stloc.2
0xc4c9  brfalse  loc_C5AB
0xc4ce  ldloc.2
0xc4cf  ldstr    aBingmaps// "BingMaps"
0xc4d4  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc4d9  brfalse  loc_C5AB
0xc4de  ldloc.0
0xc4df  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc4e4  ldstr    a0DefaultAspx// "{0}/default.aspx"
0xc4e9  ldc.i4.1
0xc4ea  newarr   [mscorlib]System.Object
0xc4ef  stloc.3
0xc4f0  ldloc.3
0xc4f1  ldc.i4.0
0xc4f2  call     string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_MapSite()
0xc4f7  stelem.ref
0xc4f8  ldloc.3
0xc4f9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xc4fe  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc503  pop
0xc504  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xc509  stloc.1
0xc50a  ldloc.1
0xc50b  ldstr    aV2StyleRLvl16C// "?v=2&style=r&lvl=16&cnty1="
0xc510  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc515  pop
0xc516  ldloc.1
0xc517  ldarg.0
0xc518  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::get_CountryRegionIso2Code()
0xc51d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc522  pop
0xc523  ldloc.1
0xc524  ldstr    aWhere1// "&where1="
0xc529  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc52e  pop
0xc52f  ldloc.1
0xc530  ldarg.0
0xc531  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::get_FormattedAddress()
0xc536  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc53b  pop
0xc53c  ldloc.1
0xc53d  ldstr    aCp_0// "&cp="
0xc542  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc547  pop
0xc548  ldloc.1
0xc549  ldarg.2
0xc54a  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.LatLong Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Location::get_LatLong()
0xc54f  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.LatLong::get_Latitude()
0xc554  stloc.s  4
0xc556  ldloca.s 4
0xc558  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc55d  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0xc562  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc567  pop
0xc568  ldloc.1
0xc569  ldstr    asc_2666E// "~"
0xc56e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc573  pop
0xc574  ldloc.1
0xc575  ldarg.2
0xc576  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.LatLong Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Location::get_LatLong()
0xc57b  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.LatLong::get_Longitude()
0xc580  stloc.s  5
0xc582  ldloca.s 5
0xc584  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc589  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0xc58e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc593  pop
0xc594  ldloc.0
0xc595  ldloc.1
0xc596  callvirt instance string [mscorlib]System.Object::ToString()
0xc59b  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::UrlEncode(string)
0xc5a0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc5a5  pop
0xc5a6  br       loc_C673
0xc5ab  ldloc.0
0xc5ac  ldarg.0
0xc5ad  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::get_CultureName()
0xc5b2  call     string Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::GetMapPointSite(string culture)
0xc5b7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc5bc  pop
0xc5bd  ldloc.0
0xc5be  ldstr    aHomeAspx// "/home.aspx"
0xc5c3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc5c8  pop
0xc5c9  ldloc.0
0xc5ca  ldstr    aStrt1// "?strt1="
0xc5cf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc5d4  pop
0xc5d5  ldloc.0
0xc5d6  ldarg.2
0xc5d7  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Address Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Location::get_Address()
0xc5dc  callvirt instance string Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Address::get_AddressLine()
0xc5e1  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::UrlEncode(string)
0xc5e6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc5eb  pop
0xc5ec  ldloc.0
0xc5ed  ldstr    aCity1// "&city1="
0xc5f2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc5f7  pop
0xc5f8  ldloc.0
0xc5f9  ldarg.2
0xc5fa  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Address Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Location::get_Address()
0xc5ff  callvirt instance string Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Address::get_PrimaryCity()
0xc604  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::UrlEncode(string)
0xc609  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc60e  pop
0xc60f  ldloc.0
0xc610  ldstr    aStnm1// "&stnm1="
0xc615  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc61a  pop
0xc61b  ldloc.0
0xc61c  ldarg.2
0xc61d  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Address Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Location::get_Address()
0xc622  callvirt instance string Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Address::get_Subdivision()
0xc627  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::UrlEncode(string)
0xc62c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc631  pop
0xc632  ldloc.0
0xc633  ldstr    aZipc1// "&zipc1="
0xc638  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc63d  pop
0xc63e  ldloc.0
0xc63f  ldarg.2
0xc640  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Address Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Location::get_Address()
0xc645  callvirt instance string Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Address::get_PostalCode()
0xc64a  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::UrlEncode(string)
0xc64f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc654  pop
0xc655  ldloc.0
0xc656  ldstr    aCnty1// "&cnty1="
0xc65b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc660  pop
0xc661  ldloc.0
0xc662  ldarg.0
0xc663  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::get_CountryRegionIso2Code()
0xc668  call     int32 Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::GetMsnMapsCountryCode(string iso2CountryCode)
0xc66d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int32)
0xc672  pop
0xc673  ldarg.1
0xc674  ldc.i4.s 0x21
0xc676  ldstr    aBlank// "_blank"
0xc67b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0xc680  ldarg.1
0xc681  ldc.i4.s 0x10
0xc683  ldloc.0
0xc684  callvirt instance string [mscorlib]System.Object::ToString()
0xc689  ldstr    a0d0a// "%0d%0a"
0xc68e  ldstr    a2c20// "%2c%20"
0xc693  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xc698  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0xc69d  ldarg.1
0xc69e  ldc.i4.1
0xc69f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0xc6a4  ret
```
