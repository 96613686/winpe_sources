# Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::RenderContents

- ea: `0xba60`
- end: `0xbfa2`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::RenderContents`
- size: `1346`
- prototype: ``
- caller_count: `0`
- callee_count: `45`
- tags: `broker_com_uri`

## callees

- `0x7bc0`
- `0x9a40`
- `0xabe0`
- `0xb140`
- `0xb180`
- `0xb6f0`
- `0xb790`
- `0xb870`
- `0xba60`
- `0xc060`
- `0xc3f0`
- `0xc4b0`
- `0xc6b0`
- `0xc7a0`
- `0xcbe0`
- `0xf930`
- `0xfa30`
- `0xfa50`
- `0xfa80`
- `0xfac0`
- `0xfae0`
- `0xfc00`
- `0xfc60`
- `0xffd0`
- `0x10030`
- `0x10050`
- `0x10970`
- `0x10990`
- `0x109a0`
- `0x109b0`
- `0x10a40`
- `0x10a60`
- `0x10a80`
- `0x10aa0`
- `0x10ac0`
- `0x10b30`
- `0x10b60`
- `0x10c20`
- `0x10c30`
- `0x10c70`
- `0x10f00`
- `0x10f60`
- `0x10f80`
- `0x10fc0`
- `0x10fd0`

## string_xrefs

- `0xbac2`: `LocationControl.DirectionsLinkText`
- `0xbceb`: `LocationControl.MapLink.ToolTip`

## pseudocode

```c

```

## disassembly

```asm
0xba60  ldc.i4.0
0xba61  stloc.0
0xba62  ldnull
0xba63  stloc.1
0xba64  ldarg.0
0xba65  ldfld    bool Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::showAddress
0xba6a  brfalse.s loc_BA75
0xba6c  ldarg.0
0xba6d  ldarg.1
0xba6e  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::RenderAddress(class [System.Web]System.Web.UI.HtmlTextWriter output)
0xba73  ldc.i4.1
0xba74  stloc.0
0xba75  ldarg.0
0xba76  ldfld    bool Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::showDirections
0xba7b  brfalse.s loc_BAD9
0xba7d  ldloc.1
0xba7e  brtrue.s loc_BA87
0xba80  ldarg.0
0xba81  call     instance class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Location Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::GetLocation()
0xba86  stloc.1
0xba87  ldloc.1
0xba88  brtrue.s loc_BAB0
0xba8a  ldarg.0
0xba8b  ldfld    bool Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::showMap
0xba90  brtrue.s loc_BAD9
0xba92  ldloc.0
0xba93  brfalse.s loc_BA9B
0xba95  ldarg.1
0xba96  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBreak()
0xba9b  ldarg.0
0xba9c  ldarg.1
0xba9d  ldstr    aLocationcontro_1// "LocationControl.FindAddressErrorMsg"
0xbaa2  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0xbaa7  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::RenderErrorMessage(class [System.Web]System.Web.UI.HtmlTextWriter output, string message)
0xbaac  ldc.i4.1
0xbaad  stloc.0
0xbaae  br.s     loc_BAD9
0xbab0  ldloc.0
0xbab1  brfalse.s loc_BAB9
0xbab3  ldarg.1
0xbab4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBreak()
0xbab9  ldarg.0
0xbaba  ldarg.1
0xbabb  ldloc.1
0xbabc  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::RenderDirectionsLinkBeginTag(class [System.Web]System.Web.UI.HtmlTextWriter output, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Location location)
0xbac1  ldarg.1
0xbac2  ldstr    aLocationcontro_2// "LocationControl.DirectionsLinkText"
0xbac7  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0xbacc  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEncodedText(string)
0xbad1  ldarg.1
0xbad2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0xbad7  ldc.i4.1
0xbad8  stloc.0
0xbad9  ldarg.0
0xbada  ldfld    bool Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::showMap
0xbadf  brtrue.s loc_BAF7
0xbae1  ldarg.0
0xbae2  ldfld    bool Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::showAddress
0xbae7  brtrue   loc_BFA1
0xbaec  ldarg.0
0xbaed  ldfld    bool Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::showDirections
0xbaf2  brtrue   loc_BFA1
0xbaf7  ldloc.0
0xbaf8  brfalse.s loc_BB00
0xbafa  ldarg.1
0xbafb  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBreak()
0xbb00  ldc.i4.1
0xbb01  stloc.0
0xbb02  ldloc.1
0xbb03  brtrue.s loc_BB0C
0xbb05  ldarg.0
0xbb06  call     instance class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Location Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::GetLocation()
0xbb0b  stloc.1
0xbb0c  ldloc.1
0xbb0d  brtrue.s loc_BB21
0xbb0f  ldarg.0
0xbb10  ldarg.1
0xbb11  ldstr    aLocationcontro_1// "LocationControl.FindAddressErrorMsg"
0xbb16  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0xbb1b  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::RenderErrorMessage(class [System.Web]System.Web.UI.HtmlTextWriter output, string message)
0xbb20  ret
0xbb21  ldc.i4.1
0xbb22  newarr   Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.MapView
0xbb27  stloc.2
0xbb28  ldloc.2
0xbb29  ldc.i4.0
0xbb2a  ldloc.1
0xbb2b  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.MapViewRepresentations Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Location::get_BestMapView()
0xbb30  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.ViewByBoundingRectangle Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.MapViewRepresentations::get_ByBoundingRectangle()
0xbb35  stelem.ref
0xbb36  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.MapOptions::.ctor()
0xbb3b  stloc.3
0xbb3c  ldloc.3
0xbb3d  ldc.i4.1
0xbb3e  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.MapOptions::set_ReturnType(valuetype Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.MapReturnType value)
0xbb43  ldloc.3
0xbb44  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.ImageFormat::.ctor()
0xbb49  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.MapOptions::set_Format(class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.ImageFormat value)
0xbb4e  ldloc.3
0xbb4f  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.ImageFormat Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.MapOptions::get_Format()
0xbb54  ldarg.0
0xbb55  ldfld    int32 Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::imgHeight
0xbb5a  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.ImageFormat::set_Height(int32 value)
0xbb5f  ldloc.3
0xbb60  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.ImageFormat Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.MapOptions::get_Format()
0xbb65  ldarg.0
0xbb66  ldfld    int32 Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::imgWidth
0xbb6b  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.ImageFormat::set_Width(int32 value)
0xbb70  ldnull
0xbb71  stloc.s  4
0xbb73  ldarg.0
0xbb74  call     instance bool Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::get_ShowLocationMark()
0xbb79  brfalse.s loc_BBD3
0xbb7b  ldc.i4.1
0xbb7c  newarr   Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Pushpin
0xbb81  stloc.s  4
0xbb83  ldloc.s  4
0xbb85  ldc.i4.0
0xbb86  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Pushpin::.ctor()
0xbb8b  stelem.ref
0xbb8c  ldloc.s  4
0xbb8e  ldc.i4.0
0xbb8f  ldelem.ref
0xbb90  ldstr    aPin0// "pin0"
0xbb95  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Pushpin::set_PinID(string value)
0xbb9a  ldloc.s  4
0xbb9c  ldc.i4.0
0xbb9d  ldelem.ref
0xbb9e  ldsfld   string [mscorlib]System.String::Empty
0xbba3  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Pushpin::set_Label(string value)
0xbba8  ldloc.s  4
0xbbaa  ldc.i4.0
0xbbab  ldelem.ref
0xbbac  ldstr    a0// "0"
0xbbb1  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Pushpin::set_IconName(string value)
0xbbb6  ldloc.s  4
0xbbb8  ldc.i4.0
0xbbb9  ldelem.ref
0xbbba  ldstr    aMappointIcons// "MapPoint.Icons"
0xbbbf  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Pushpin::set_IconDataSource(string value)
0xbbc4  ldloc.s  4
0xbbc6  ldc.i4.0
0xbbc7  ldelem.ref
0xbbc8  ldloc.1
0xbbc9  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.LatLong Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Location::get_LatLong()
0xbbce  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Pushpin::set_LatLong(class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.LatLong value)
0xbbd3  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.MapSpecification::.ctor()
0xbbd8  stloc.s  5
0xbbda  ldloc.s  5
0xbbdc  ldloc.3
0xbbdd  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.MapSpecification::set_Options(class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.MapOptions value)
0xbbe2  ldloc.s  5
0xbbe4  ldloc.2
0xbbe5  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.MapSpecification::set_Views(class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.MapView[] value)
0xbbea  ldloc.s  5
0xbbec  ldloc.s  4
0xbbee  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.MapSpecification::set_Pushpins(class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Pushpin[] value)
0xbbf3  ldloc.s  5
0xbbf5  ldarg.0
0xbbf6  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::get_DataSourceName()
0xbbfb  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.MapSpecification::set_DataSourceName(string value)
0xbc00  ldnull
0xbc01  stloc.s  6
0xbc03  call     string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_MapSource()
0xbc08  dup
0xbc09  stloc.s  8
0xbc0b  brfalse.s loc_BC56
0xbc0d  ldloc.s  8
0xbc0f  ldstr    aBingmaps// "BingMaps"
0xbc14  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbc19  brfalse.s loc_BC56
0xbc1b  ldc.i4.1
0xbc1c  newarr   Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.MapImage
0xbc21  stloc.s  9
0xbc23  ldloc.s  9
0xbc25  ldc.i4.0
0xbc26  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.MapImage::.ctor()
0xbc2b  stelem.ref
0xbc2c  ldloc.s  9
0xbc2e  stloc.s  6
0xbc30  ldloc.s  6
0xbc32  ldc.i4.0
0xbc33  ldelem.ref
0xbc34  ldloc.1
0xbc35  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.LatLong Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Location::get_LatLong()
0xbc3a  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.LatLong::get_Latitude()
0xbc3f  ldloc.1
0xbc40  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.LatLong Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Location::get_LatLong()
0xbc45  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.LatLong::get_Longitude()
0xbc4a  call     string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::RequestImage(float64 _Latitude, float64 _Longitude)
0xbc4f  callvirt instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.MapImage::set_Url(string value)
0xbc54  br.s     loc_BC65
0xbc56  ldarg.0
0xbc57  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::get_CultureName()
0xbc5c  ldloc.s  5
0xbc5e  call     class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.MapImage[] Microsoft.SharePoint.Spx.WebSite.Controls.MapPoint::GetMap(string cultureName, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.MapSpecification mapSpec)
0xbc63  stloc.s  6
0xbc65  leave.s  loc_BCBF
0xbc67  stloc.s  7
0xbc69  ldc.i4.0
0xbc6a  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0xbc6f  ldc.i4.s 0x32
0xbc71  ldstr    aLocationcontro_3// "LocationControl"
0xbc76  ldstr    aRendercontents// "RenderContents"
0xbc7b  ldstr    aFailedToRetrie// "failed to retrieve map. Exception: {0}"
0xbc80  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0xbc85  ldc.i4.1
0xbc86  newarr   [mscorlib]System.Object
0xbc8b  stloc.s  0xA
0xbc8d  ldloc.s  0xA
0xbc8f  ldc.i4.0
0xbc90  ldloc.s  7
0xbc92  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetExceptionString(class [mscorlib]System.Exception)
0xbc97  stelem.ref
0xbc98  ldloc.s  0xA
0xbc9a  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xbc9f  ldarg.0
0xbca0  ldloc.s  7
0xbca2  callvirt instance string [mscorlib]System.Exception::get_Message()
0xbca7  ldstr    asc_263C0// "\r\n\r\n"
0xbcac  ldloc.s  7
0xbcae  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0xbcb3  call     string [mscorlib]System.String::Concat(string, string, string)
0xbcb8  stfld    string Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::extendedErrorMsg
0xbcbd  leave.s  loc_BCBF
0xbcbf  ldloc.s  6
0xbcc1  brtrue.s loc_BCD9
0xbcc3  ldarg.0
0xbcc4  ldarg.1
0xbcc5  ldstr    aLocationcontro_4// "LocationControl.RenderErrorMsg"
0xbcca  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0xbccf  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::RenderErrorMessage(class [System.Web]System.Web.UI.HtmlTextWriter output, string message)
0xbcd4  br       loc_BD5C
0xbcd9  ldarg.0
0xbcda  ldfld    bool Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::enableMapLink
0xbcdf  brfalse.s loc_BCFA
0xbce1  ldarg.0
0xbce2  ldarg.1
0xbce3  ldloc.1
0xbce4  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::RenderMapLinkBeginTag(class [System.Web]System.Web.UI.HtmlTextWriter output, class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Location location)
0xbce9  ldarg.1
0xbcea  ldc.i4.2
0xbceb  ldstr    aLocationcontro_5// "LocationControl.MapLink.ToolTip"
0xbcf0  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0xbcf5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0xbcfa  ldarg.1
0xbcfb  ldc.i4.s 0x1E
0xbcfd  ldloc.s  6
0xbcff  ldc.i4.0
0xbd00  ldelem.ref
0xbd01  callvirt instance string Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.MapImage::get_Url()
0xbd06  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0xbd0b  ldarg.1
0xbd0c  ldc.i4.s 0xF
0xbd0e  ldarg.0
0xbd0f  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::get_ImgHeight()
0xbd14  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0xbd19  ldarg.1
0xbd1a  ldc.i4.s 0x26
0xbd1c  ldarg.0
0xbd1d  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::get_ImgWidth()
0xbd22  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0xbd27  ldarg.1
0xbd28  ldc.i4.2
0xbd29  ldstr    asc_21500// ""
0xbd2e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0xbd33  ldarg.1
0xbd34  ldc.i4.s 0x1E
0xbd36  ldstr    a5px// "5px"
0xbd3b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0xbd40  ldarg.1
0xbd41  ldc.i4.s 0x2E
0xbd43  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0xbd48  ldarg.1
0xbd49  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0xbd4e  ldarg.0
0xbd4f  ldfld    bool Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::enableMapLink
0xbd54  brfalse.s loc_BD5C
0xbd56  ldarg.1
0xbd57  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0xbd5c  ldarg.0
0xbd5d  ldfld    bool Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::showMapInfo
0xbd62  brfalse  loc_BFA1
0xbd67  ldarg.1
0xbd68  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBreak()
0xbd6d  ldarg.1
0xbd6e  ldstr    aLatitude_0// "Latitude=\""
0xbd73  ldloc.1
0xbd74  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.LatLong Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Location::get_LatLong()
0xbd79  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.LatLong::get_Latitude()
0xbd7e  box      [mscorlib]System.Double
0xbd83  ldstr    asc_25ADE// "\""
0xbd88  call     string [mscorlib]System.String::Concat(object, object, object)
0xbd8d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEncodedText(string)
0xbd92  ldarg.1
0xbd93  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBreak()
0xbd98  ldarg.1
0xbd99  ldstr    aLongitude_0// "Longitude=\""
0xbd9e  ldloc.1
0xbd9f  callvirt instance class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.LatLong Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.Location::get_LatLong()
  ... truncated ...
```
