# Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::FindLocationsXml_0

- ea: `0xa4b0`
- end: `0xa565`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::FindLocationsXml_0`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa380`

## callees

- `0xa4b0`
- `0xa570`
- `0xaad0`
- `0xabd0`

## string_xrefs

- `0xa53c`: `FindLocationXML failed: {0}`
- `0xa4c1`: `http://dev.virtualearth.net/REST/v1/Locations/{0}?o=xml&key={1}`
- `0xa508`: `FindLocationXML(no culture)`
- `0xa537`: `BingMaps.FindLocationXML.result(NoCulture)`

## pseudocode

```c

```

## disassembly

```asm
0xa4b0  ldnull
0xa4b1  stloc.0
0xa4b2  ldarg.0
0xa4b3  brtrue.s loc_A4BC
0xa4b5  ldsfld   string [mscorlib]System.String::Empty
0xa4ba  starg.s  0
0xa4bc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa4c1  ldstr    aHttpDevVirtual_0// "http://dev.virtualearth.net/REST/v1/Loc"...
0xa4c6  ldc.i4.2
0xa4c7  newarr   [mscorlib]System.Object
0xa4cc  stloc.3
0xa4cd  ldloc.3
0xa4ce  ldc.i4.0
0xa4cf  ldarg.0
0xa4d0  call     string [mscorlib]System.Environment::get_NewLine()
0xa4d5  ldstr    asc_2030E// ","
0xa4da  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xa4df  stelem.ref
0xa4e0  ldloc.3
0xa4e1  ldc.i4.1
0xa4e2  call     string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_BingMapKey()
0xa4e7  stelem.ref
0xa4e8  ldloc.3
0xa4e9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa4ee  stloc.1
0xa4ef  ldloc.1
0xa4f0  call     class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::GetXmlResponse(string requestUrl)
0xa4f5  call     string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::BuildLocationXml(class [System.Xml]System.Xml.XmlDocument xmlResponse)
0xa4fa  stloc.0
0xa4fb  ldc.i4.0
0xa4fc  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0xa501  ldc.i4.s 0x64
0xa503  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::CLID
0xa508  ldstr    aFindlocationxm_1// "FindLocationXML(no culture)"
0xa50d  ldstr    aResult_0// "result: "
0xa512  ldloc.0
0xa513  callvirt instance string [mscorlib]System.Object::ToString()
0xa518  call     string [mscorlib]System.String::Concat(string, string)
0xa51d  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0xa522  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0xa527  leave.s  loc_A563
0xa529  stloc.2
0xa52a  ldc.i4.0
0xa52b  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0xa530  ldc.i4.s 0x32
0xa532  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::CLID
0xa537  ldstr    aBingmapsFindlo_0// "BingMaps.FindLocationXML.result(NoCultu"...
0xa53c  ldstr    aFindlocationxm_0// "FindLocationXML failed: {0}"
0xa541  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0xa546  ldc.i4.1
0xa547  newarr   [mscorlib]System.Object
0xa54c  stloc.s  4
0xa54e  ldloc.s  4
0xa550  ldc.i4.0
0xa551  ldloc.2
0xa552  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetExceptionString(class [mscorlib]System.Exception)
0xa557  stelem.ref
0xa558  ldloc.s  4
0xa55a  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xa55f  ldnull
0xa560  stloc.0
0xa561  leave.s  loc_A563
0xa563  ldloc.0
0xa564  ret
```
