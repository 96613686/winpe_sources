# Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::RenderContents

- ea: `0x15990`
- end: `0x162aa`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::RenderContents`
- size: `2330`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x7bc0`
- `0x7d80`
- `0x7db0`
- `0x15540`
- `0x15620`
- `0x15720`
- `0x15780`
- `0x157d0`
- `0x157f0`
- `0x15820`
- `0x15890`
- `0x15990`
- `0x162b0`
- `0x162e0`
- `0x16370`
- `0x163c0`

## string_xrefs

- `0x15c6d`: `temperature`
- `0x15e5b`: `WeatherControl.HighTemp.Label`
- `0x15e8b`: `WeatherControl.LowTemp.Label`
- `0x161fc`: `WeatherControl.MSN.LinkText`

## pseudocode

```c

```

## disassembly

```asm
0x15990  ldarg.1
0x15991  ldc.i4.s 0x52
0x15993  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x15998  ldarg.1
0x15999  ldc.i4.s 0x5A
0x1599b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x159a0  ldarg.1
0x159a1  ldc.i4.s 0x54
0x159a3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x159a8  ldnull
0x159a9  stloc.0
0x159aa  ldarg.0
0x159ab  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_LocationCode()
0x159b0  brfalse.s loc_159DC
0x159b2  ldarg.0
0x159b3  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_LocationCode()
0x159b8  callvirt instance int32 [mscorlib]System.String::get_Length()
0x159bd  brfalse.s loc_159DC
0x159bf  ldarg.0
0x159c0  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_LocationCode()
0x159c5  ldarg.0
0x159c6  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_CultureName()
0x159cb  ldarg.0
0x159cc  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_UnitType()
0x159d1  call     string Microsoft.SharePoint.Spx.WebSite.Controls.MsnWeatherService::GetWeatherDataXml(string locationCode, string cultureName, string units)
0x159d6  stloc.0
0x159d7  br       loc_15ABB
0x159dc  ldarg.0
0x159dd  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_LocationName()
0x159e2  brfalse  loc_15ABB
0x159e7  ldarg.0
0x159e8  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_LocationName()
0x159ed  callvirt instance int32 [mscorlib]System.String::get_Length()
0x159f2  brfalse  loc_15ABB
0x159f7  ldarg.0
0x159f8  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_LocationName()
0x159fd  ldarg.0
0x159fe  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_CultureName()
0x15a03  ldarg.0
0x15a04  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_UnitType()
0x15a09  call     string Microsoft.SharePoint.Spx.WebSite.Controls.MsnWeatherService::FindWeatherLocationsXml(string searchStr, string cultureName, string units)
0x15a0e  stloc.1
0x15a0f  ldloc.1
0x15a10  brfalse  loc_15ABB
0x15a15  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x15a1a  stloc.2
0x15a1b  ldloc.2
0x15a1c  ldnull
0x15a1d  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x15a22  ldloc.1
0x15a23  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x15a28  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader)
0x15a2d  stloc.3
0x15a2e  ldloc.2
0x15a2f  ldloc.3
0x15a30  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [System.Xml]System.Xml.XmlReader)
0x15a35  leave.s  loc_15A41
0x15a37  ldloc.3
0x15a38  brfalse.s loc_15A40
0x15a3a  ldloc.3
0x15a3b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15a40  endfinally
0x15a41  ldloc.2
0x15a42  ldstr    aDescendantWeat// "descendant::weather"
0x15a47  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x15a4c  stloc.s  4
0x15a4e  ldloc.s  4
0x15a50  ldstr    aWeatherlocatio// "weatherlocationcode"
0x15a55  call     string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x15a5a  stloc.s  5
0x15a5c  ldloc.s  5
0x15a5e  brfalse.s loc_15ABB
0x15a60  ldloc.s  5
0x15a62  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15a67  brfalse.s loc_15ABB
0x15a69  ldloc.s  4
0x15a6b  ldstr    aSearchscore// "searchscore"
0x15a70  call     string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x15a75  stloc.s  6
0x15a77  ldloc.s  6
0x15a79  brfalse.s loc_15ABB
0x15a7b  ldloc.s  6
0x15a7d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15a82  brfalse.s loc_15ABB
0x15a84  ldloc.s  6
0x15a86  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x15a8b  call     float64 [mscorlib]System.Double::Parse(string, class [mscorlib]System.IFormatProvider)
0x15a90  ldc.r8   0.1
0x15a99  ble.un.s loc_15ABB
0x15a9b  ldarg.0
0x15a9c  ldloc.s  5
0x15a9e  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::set_LocationCode(string value)
0x15aa3  ldarg.0
0x15aa4  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_LocationCode()
0x15aa9  ldarg.0
0x15aaa  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_CultureName()
0x15aaf  ldarg.0
0x15ab0  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_UnitType()
0x15ab5  call     string Microsoft.SharePoint.Spx.WebSite.Controls.MsnWeatherService::GetWeatherDataXml(string locationCode, string cultureName, string units)
0x15aba  stloc.0
0x15abb  leave.s  loc_15AFB
0x15abd  stloc.s  7
0x15abf  ldc.i4   0x6736396F
0x15ac4  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0x15ac9  ldc.i4.s 0x32
0x15acb  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::classId
0x15ad0  ldstr    aRendercontents// "RenderContents"
0x15ad5  ldstr    aGettingWeather// "Getting Weather Data Failed. "
0x15ada  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0x15adf  ldc.i4.1
0x15ae0  newarr   [mscorlib]System.Object
0x15ae5  stloc.s  0x22
0x15ae7  ldloc.s  0x22
0x15ae9  ldc.i4.0
0x15aea  ldloc.s  7
0x15aec  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetExceptionString(class [mscorlib]System.Exception)
0x15af1  stelem.ref
0x15af2  ldloc.s  0x22
0x15af4  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x15af9  leave.s  loc_15AFB
0x15afb  ldloc.0
0x15afc  brtrue   loc_15B8A
0x15b01  ldarg.0
0x15b02  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_LocationCode()
0x15b07  brfalse.s loc_15B3B
0x15b09  ldarg.0
0x15b0a  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_LocationCode()
0x15b0f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15b14  brfalse.s loc_15B3B
0x15b16  ldarg.1
0x15b17  ldstr    aWeathercontrol_0// "WeatherControl.ErrMsg.NoDataForLocation"...
0x15b1c  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x15b21  ldstr    a0_0// "{0}"
0x15b26  ldarg.0
0x15b27  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_LocationCode()
0x15b2c  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x15b31  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEncodedText(string)
0x15b36  br       loc_16297
0x15b3b  ldarg.0
0x15b3c  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_LocationName()
0x15b41  brfalse.s loc_15B75
0x15b43  ldarg.0
0x15b44  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_LocationName()
0x15b49  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15b4e  brfalse.s loc_15B75
0x15b50  ldarg.1
0x15b51  ldstr    aWeathercontrol_1// "WeatherControl.ErrMsg.NoDataForLocation"...
0x15b56  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x15b5b  ldstr    a0_0// "{0}"
0x15b60  ldarg.0
0x15b61  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_LocationName()
0x15b66  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x15b6b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEncodedText(string)
0x15b70  br       loc_16297
0x15b75  ldarg.1
0x15b76  ldstr    aWeathercontrol_2// "WeatherControl.ErrMsg.MissingLocation"
0x15b7b  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x15b80  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEncodedText(string)
0x15b85  br       loc_16297
0x15b8a  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x15b8f  stloc.s  8
0x15b91  ldloc.s  8
0x15b93  ldnull
0x15b94  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x15b99  ldloc.0
0x15b9a  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x15b9f  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader)
0x15ba4  stloc.s  9
0x15ba6  ldloc.s  8
0x15ba8  ldloc.s  9
0x15baa  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [System.Xml]System.Xml.XmlReader)
0x15baf  leave.s  loc_15BBD
0x15bb1  ldloc.s  9
0x15bb3  brfalse.s loc_15BBC
0x15bb5  ldloc.s  9
0x15bb7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15bbc  endfinally
0x15bbd  ldloc.s  8
0x15bbf  ldstr    aDescendantWeat// "descendant::weather"
0x15bc4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x15bc9  stloc.s  0xA
0x15bcb  ldloc.s  0xA
0x15bcd  ldstr    aErrormessage// "errormessage"
0x15bd2  call     string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x15bd7  stloc.s  0xB
0x15bd9  ldloc.s  0xB
0x15bdb  brfalse.s loc_15BEA
0x15bdd  ldarg.1
0x15bde  ldloc.s  0xB
0x15be0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEncodedText(string)
0x15be5  br       loc_16297
0x15bea  ldnull
0x15beb  stloc.s  0xC
0x15bed  ldarg.0
0x15bee  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_CultureName()
0x15bf3  ldstr    aJaJp// "ja-JP"
0x15bf8  ldc.i4.5
0x15bf9  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x15bfe  brfalse.s loc_15C0E
0x15c00  ldloc.s  0xA
0x15c02  ldstr    aWeathercitynam// "weathercityname"
0x15c07  call     string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x15c0c  stloc.s  0xC
0x15c0e  ldloc.s  0xC
0x15c10  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15c15  brfalse.s loc_15C25
0x15c17  ldloc.s  0xA
0x15c19  ldstr    aWeatherlocatio_0// "weatherlocationname"
0x15c1e  call     string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x15c23  stloc.s  0xC
0x15c25  ldloc.s  0xA
0x15c27  ldstr    aUrl_0// "url"
0x15c2c  call     string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x15c31  stloc.s  0xD
0x15c33  ldloc.s  0xA
0x15c35  ldstr    aImagerelativeu// "imagerelativeurl"
0x15c3a  call     string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x15c3f  stloc.s  0xE
0x15c41  ldloc.s  0xA
0x15c43  ldstr    aDegreetype// "degreetype"
0x15c48  call     string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x15c4d  stloc.s  0xF
0x15c4f  ldloc.s  0xA
0x15c51  ldstr    aAttribution// "attribution"
0x15c56  call     string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x15c5b  stloc.s  0x10
0x15c5d  ldloc.s  0xA
0x15c5f  ldstr    aDescendantCurr// "descendant::current"
0x15c64  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x15c69  stloc.s  0x11
0x15c6b  ldloc.s  0x11
0x15c6d  ldstr    aTemperature// "temperature"
0x15c72  call     string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x15c77  stloc.s  0x12
0x15c79  ldloc.s  0x11
0x15c7b  ldstr    aSkycode// "skycode"
0x15c80  call     string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x15c85  stloc.s  0x13
0x15c87  ldloc.s  0x11
0x15c89  ldstr    aSkytext// "skytext"
0x15c8e  call     string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x15c93  stloc.s  0x14
0x15c95  ldloc.s  0x11
0x15c97  ldstr    aDate// "date"
0x15c9c  call     string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x15ca1  stloc.s  0x15
0x15ca3  ldloc.s  0x11
0x15ca5  ldstr    aObservationtim// "observationtime"
0x15caa  call     string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x15caf  stloc.s  0x16
0x15cb1  ldloc.s  0x11
0x15cb3  ldstr    aHumidity// "humidity"
0x15cb8  call     string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x15cbd  stloc.s  0x17
0x15cbf  ldloc.s  0x11
0x15cc1  ldstr    aWindspeed// "windspeed"
0x15cc6  call     string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x15ccb  stloc.s  0x18
0x15ccd  ldloc.s  0xA
0x15ccf  ldstr    aDescendantFore// "descendant::forecast"
0x15cd4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x15cd9  stloc.s  0x19
0x15cdb  ldloc.s  0x19
0x15cdd  ldstr    aLow// "low"
0x15ce2  call     string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x15ce7  stloc.s  0x1A
0x15ce9  ldloc.s  0x19
0x15ceb  ldstr    aHigh// "high"
0x15cf0  call     string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x15cf5  stloc.s  0x1B
0x15cf7  ldloc.s  0x19
0x15cf9  ldstr    aSkycodeday// "skycodeday"
0x15cfe  call     string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x15d03  stloc.s  0x1C
0x15d05  ldloc.s  0x19
0x15d07  ldstr    aSkytextday// "skytextday"
0x15d0c  call     string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x15d11  stloc.s  0x1D
0x15d13  ldloc.s  0x19
0x15d15  ldstr    aDay// "day"
0x15d1a  call     string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attribute)
0x15d1f  stloc.s  0x1E
0x15d21  ldarg.1
0x15d22  ldc.i4.8
0x15d23  ldstr    a160// "160%"
0x15d28  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddStyleAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x15d2d  ldarg.1
0x15d2e  ldc.i4.s 0x4C
0x15d30  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x15d35  ldarg.0
0x15d36  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_DisplayName()
0x15d3b  brfalse.s loc_15D4A
0x15d3d  ldarg.0
0x15d3e  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_DisplayName()
0x15d43  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15d48  brtrue.s loc_15D54
0x15d4a  ldarg.1
0x15d4b  ldloc.s  0xC
0x15d4d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEncodedText(string)
0x15d52  br.s     loc_15D60
  ... truncated ...
```
