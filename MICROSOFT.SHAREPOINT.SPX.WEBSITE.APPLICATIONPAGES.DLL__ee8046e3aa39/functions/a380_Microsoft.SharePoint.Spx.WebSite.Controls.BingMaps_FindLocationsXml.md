# Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::FindLocationsXml

- ea: `0xa380`
- end: `0xa4a8`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::FindLocationsXml`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0xd170`

## callees

- `0xa380`
- `0xa4b0`
- `0xa570`
- `0xaad0`
- `0xabd0`
- `0xac60`

## string_xrefs

- `0xa399`: `FindLocationXML`
- `0xa435`: `FindLocationXML`
- `0xa475`: `FindLocationXML`
- `0xa3eb`: `http://dev.virtualearth.net/REST/v1/Locations/{0}?o=xml&c=`
- `0xa47a`: `FindLocationXML failed: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xa380  ldnull
0xa381  stloc.0
0xa382  ldarg.3
0xa383  brtrue.s loc_A38C
0xa385  ldsfld   string [mscorlib]System.String::Empty
0xa38a  starg.s  3
0xa38c  ldc.i4.0
0xa38d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0xa392  ldc.i4.s 0x64
0xa394  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::CLID
0xa399  ldstr    aFindlocationxm// "FindLocationXML"
0xa39e  ldstr    aInputs// "inputs: "
0xa3a3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa3a8  ldstr    aCulture0Ds1Reg// "Culture={0} :DS={1} :region={2}"
0xa3ad  ldc.i4.3
0xa3ae  newarr   [mscorlib]System.Object
0xa3b3  stloc.s  4
0xa3b5  ldloc.s  4
0xa3b7  ldc.i4.0
0xa3b8  ldarg.0
0xa3b9  stelem.ref
0xa3ba  ldloc.s  4
0xa3bc  ldc.i4.1
0xa3bd  ldarg.1
0xa3be  stelem.ref
0xa3bf  ldloc.s  4
0xa3c1  ldc.i4.2
0xa3c2  ldarg.2
0xa3c3  stelem.ref
0xa3c4  ldloc.s  4
0xa3c6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa3cb  call     string [mscorlib]System.String::Concat(string, string)
0xa3d0  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0xa3d5  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0xa3da  call     bool Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_CountrySpecific()
0xa3df  brtrue.s loc_A3E4
0xa3e1  ldarg.0
0xa3e2  br.s     loc_A3E5
0xa3e4  ldarg.1
0xa3e5  stloc.1
0xa3e6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa3eb  ldstr    aHttpDevVirtual// "http://dev.virtualearth.net/REST/v1/Loc"...
0xa3f0  ldloc.1
0xa3f1  ldstr    aKey1// "&key={1}"
0xa3f6  call     string [mscorlib]System.String::Concat(string, string, string)
0xa3fb  ldc.i4.2
0xa3fc  newarr   [mscorlib]System.Object
0xa401  stloc.s  5
0xa403  ldloc.s  5
0xa405  ldc.i4.0
0xa406  ldarg.3
0xa407  call     string [mscorlib]System.Environment::get_NewLine()
0xa40c  ldstr    asc_2030E// ","
0xa411  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xa416  stelem.ref
0xa417  ldloc.s  5
0xa419  ldc.i4.1
0xa41a  call     string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_BingMapKey()
0xa41f  stelem.ref
0xa420  ldloc.s  5
0xa422  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa427  stloc.2
0xa428  ldc.i4.0
0xa429  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0xa42e  ldc.i4.s 0x64
0xa430  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::CLID
0xa435  ldstr    aFindlocationxm// "FindLocationXML"
0xa43a  ldstr    aRequesturl// "requestURL: "
0xa43f  ldloc.2
0xa440  call     string [mscorlib]System.String::Concat(string, string)
0xa445  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0xa44a  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0xa44f  ldloc.2
0xa450  call     class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::GetXmlResponse(string requestUrl)
0xa455  call     string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::BuildLocationXml(class [System.Xml]System.Xml.XmlDocument xmlResponse)
0xa45a  stloc.0
0xa45b  ldloc.0
0xa45c  brtrue.s loc_A465
0xa45e  ldarg.3
0xa45f  call     string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::FindLocationsXml(string address)
0xa464  pop
0xa465  leave.s  loc_A4A6
0xa467  stloc.3
0xa468  ldc.i4.0
0xa469  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0xa46e  ldc.i4.s 0x32
0xa470  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::CLID
0xa475  ldstr    aFindlocationxm// "FindLocationXML"
0xa47a  ldstr    aFindlocationxm_0// "FindLocationXML failed: {0}"
0xa47f  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0xa484  ldc.i4.1
0xa485  newarr   [mscorlib]System.Object
0xa48a  stloc.s  6
0xa48c  ldloc.s  6
0xa48e  ldc.i4.0
0xa48f  ldloc.3
0xa490  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetExceptionString(class [mscorlib]System.Exception)
0xa495  stelem.ref
0xa496  ldloc.s  6
0xa498  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xa49d  ldarg.3
0xa49e  call     string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::FindLocationsXml(string address)
0xa4a3  stloc.0
0xa4a4  leave.s  loc_A4A6
0xa4a6  ldloc.0
0xa4a7  ret
```
