# Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::RenderDirectionsLinkBeginTag

- ea: `0xc6b0`
- end: `0xc79c`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::RenderDirectionsLinkBeginTag`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0xba60`

## callees

- `0xaf90`
- `0xafc0`
- `0xb020`
- `0xb050`
- `0xb0c0`
- `0xfa30`
- `0xfa50`
- `0xfc00`

## string_xrefs

- `0xc6b0`: `bing.com/maps`
- `0xc78a`: `HyperLinkdir`

## pseudocode

```c

```

## disassembly

```asm
0xc6b0  ldstr    aBingComMaps// "bing.com/maps"
0xc6b5  stloc.0
0xc6b6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc6bb  ldstr    a01234_1// "{0} {1} {2} {3} {4}"
0xc6c0  ldc.i4.5
0xc6c1  newarr   [mscorlib]System.Object
0xc6c6  stloc.3
0xc6c7  ldloc.3
0xc6c8  ldc.i4.0
0xc6c9  ldarg.0
0xc6ca  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::get_AddressLine()
0xc6cf  stelem.ref
0xc6d0  ldloc.3
0xc6d1  ldc.i4.1
0xc6d2  ldarg.0
0xc6d3  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::get_PrimaryCity()
0xc6d8  stelem.ref
0xc6d9  ldloc.3
0xc6da  ldc.i4.2
0xc6db  ldarg.0
0xc6dc  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::get_Subdivision()
0xc6e1  stelem.ref
0xc6e2  ldloc.3
0xc6e3  ldc.i4.3
0xc6e4  ldarg.0
0xc6e5  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::get_PostalCode()
0xc6ea  stelem.ref
0xc6eb  ldloc.3
0xc6ec  ldc.i4.4
0xc6ed  ldarg.0
0xc6ee  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::get_CountryRegionIso2Code()
0xc6f3  stelem.ref
0xc6f4  ldloc.3
0xc6f5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xc6fa  stloc.1
0xc6fb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc700  ldstr    aHttp0DefaultAs// "http://{0}/default.aspx?rtp={1}{2}_{3}_"...
0xc705  ldc.i4.5
0xc706  newarr   [mscorlib]System.Object
0xc70b  stloc.s  4
0xc70d  ldloc.s  4
0xc70f  ldc.i4.0
0xc710  ldloc.0
0xc711  stelem.ref
0xc712  ldloc.s  4
0xc714  ldc.i4.1
0xc715  ldstr    aPos// "~pos."
0xc71a  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::UrlEncode(string)
0xc71f  stelem.ref
0xc720  ldloc.s  4
0xc722  ldc.i4.2
0xc723  ldarg.2
0xc724  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.LatLong Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Location::get_LatLong()
0xc729  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.LatLong::get_Latitude()
0xc72e  stloc.s  5
0xc730  ldloca.s 5
0xc732  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc737  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0xc73c  stelem.ref
0xc73d  ldloc.s  4
0xc73f  ldc.i4.3
0xc740  ldarg.2
0xc741  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.LatLong Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Location::get_LatLong()
0xc746  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.LatLong::get_Longitude()
0xc74b  stloc.s  6
0xc74d  ldloca.s 6
0xc74f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc754  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0xc759  stelem.ref
0xc75a  ldloc.s  4
0xc75c  ldc.i4.4
0xc75d  ldloc.1
0xc75e  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::UrlEncode(string)
0xc763  stelem.ref
0xc764  ldloc.s  4
0xc766  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xc76b  stloc.2
0xc76c  ldarg.1
0xc76d  ldc.i4.s 0x21
0xc76f  ldstr    aBlank// "_blank"
0xc774  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0xc779  ldarg.1
0xc77a  ldc.i4.s 0x10
0xc77c  ldloc.2
0xc77d  callvirt instance string [mscorlib]System.Object::ToString()
0xc782  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0xc787  ldarg.1
0xc788  ldc.i4.s 0x11
0xc78a  ldstr    aHyperlinkdir// "HyperLinkdir"
0xc78f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0xc794  ldarg.1
0xc795  ldc.i4.1
0xc796  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0xc79b  ret
```
