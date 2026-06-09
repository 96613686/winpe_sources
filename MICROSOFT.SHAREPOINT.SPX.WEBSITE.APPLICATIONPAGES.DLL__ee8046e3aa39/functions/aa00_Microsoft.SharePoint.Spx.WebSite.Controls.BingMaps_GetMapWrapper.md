# Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::GetMapWrapper

- ea: `0xaa00`
- end: `0xaad0`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::GetMapWrapper`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xaa00`
- `0xabd0`
- `0xac20`
- `0xac30`

## string_xrefs

- `0xaa00`: `GetMapWrapper(string cultureName, double mapLat, double mapLong)`
- `0xaa77`: `PushPinUri`

## pseudocode

```c

```

## disassembly

```asm
0xaa00  ldstr    aGetmapwrapperS// "GetMapWrapper(string cultureName, doubl"...
0xaa05  stloc.0
0xaa06  call     string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_BingMapKey()
0xaa0b  stloc.1
0xaa0c  ldarg.0
0xaa0d  stloc.2
0xaa0e  ldarg.1
0xaa0f  stloc.3
0xaa10  call     string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_BingMapsUrl()
0xaa15  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xaa1a  brtrue.s loc_AA93
0xaa1c  call     string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_BingMapsUrl()
0xaa21  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xaa26  brtrue.s loc_AA93
0xaa28  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaa2d  call     string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_BingMapsPushpin()
0xaa32  ldc.i4.4
0xaa33  newarr   [mscorlib]System.Object
0xaa38  stloc.s  7
0xaa3a  ldloc.s  7
0xaa3c  ldc.i4.0
0xaa3d  call     string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_BingMapsUrl()
0xaa42  stelem.ref
0xaa43  ldloc.s  7
0xaa45  ldc.i4.1
0xaa46  ldloc.1
0xaa47  stelem.ref
0xaa48  ldloc.s  7
0xaa4a  ldc.i4.2
0xaa4b  ldloc.2
0xaa4c  box      [mscorlib]System.Double
0xaa51  stelem.ref
0xaa52  ldloc.s  7
0xaa54  ldc.i4.3
0xaa55  ldloc.3
0xaa56  box      [mscorlib]System.Double
0xaa5b  stelem.ref
0xaa5c  ldloc.s  7
0xaa5e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xaa63  stloc.s  4
0xaa65  ldc.i4.0
0xaa66  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0xaa6b  ldc.i4.s 0x64
0xaa6d  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::CLID
0xaa72  ldstr    aGetmapwrapperN// "GetMapWrapper(no culture)"
0xaa77  ldstr    aPushpinuri// "PushPinUri"
0xaa7c  ldloc.s  4
0xaa7e  call     string [mscorlib]System.String::Concat(string, string)
0xaa83  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0xaa88  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0xaa8d  ldloc.s  4
0xaa8f  stloc.s  6
0xaa91  leave.s  loc_AACD
0xaa93  leave.s  loc_AACB
0xaa95  stloc.s  5
0xaa97  ldc.i4.0
0xaa98  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0xaa9d  ldc.i4.s 0x32
0xaa9f  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::CLID
0xaaa4  ldloc.0
0xaaa5  ldstr    aGetmapwrapperN_0// "GetMapWrapper(no culture) failed: {0}"
0xaaaa  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0xaaaf  ldc.i4.1
0xaab0  newarr   [mscorlib]System.Object
0xaab5  stloc.s  8
0xaab7  ldloc.s  8
0xaab9  ldc.i4.0
0xaaba  ldloc.s  5
0xaabc  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetExceptionString(class [mscorlib]System.Exception)
0xaac1  stelem.ref
0xaac2  ldloc.s  8
0xaac4  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xaac9  leave.s  loc_AACB
0xaacb  ldnull
0xaacc  ret
0xaacd  ldloc.s  6
0xaacf  ret
```
