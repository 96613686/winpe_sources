# Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::MakeReverseGeocodeRequest

- ea: `0xa1e0`
- end: `0xa27d`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::MakeReverseGeocodeRequest`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x9ef0`

## callees

- `0xa1e0`
- `0x16430`
- `0x16440`
- `0x16600`
- `0x166f0`
- `0x16ab0`
- `0x16ae0`
- `0x17160`
- `0x171a0`
- `0x17250`
- `0x17be0`
- `0x17f00`
- `0x17f50`

## string_xrefs

- `0xa22e`: `BasicHttpBinding_IGeocodeService`

## pseudocode

```c

```

## disassembly

```asm
0xa1e0  ldstr    aMakereversegeo// "MakeReverseGeocodeRequest"
0xa1e5  stloc.0
0xa1e6  newobj   instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResponse::.ctor()
0xa1eb  stloc.1
0xa1ec  ldstr    aBingMapsKey// "Bing Maps Key"
0xa1f1  stloc.2
0xa1f2  newobj   instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.ReverseGeocodeRequest::.ctor()
0xa1f7  stloc.3
0xa1f8  ldloc.3
0xa1f9  newobj   instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.Credentials::.ctor()
0xa1fe  callvirt instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.RequestBase::set_Credentials(class Microsoft.SharePoint.Spx.WebSite.GeocodeService.Credentials value)
0xa203  ldloc.3
0xa204  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.Credentials Microsoft.SharePoint.Spx.WebSite.GeocodeService.RequestBase::get_Credentials()
0xa209  ldloc.2
0xa20a  callvirt instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.Credentials::set_ApplicationId(string value)
0xa20f  newobj   instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.Location::.ctor()
0xa214  stloc.s  4
0xa216  ldloc.s  4
0xa218  ldarg.0
0xa219  callvirt instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.Location::set_Latitude(float64 value)
0xa21e  ldloc.s  4
0xa220  ldarg.1
0xa221  callvirt instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.Location::set_Longitude(float64 value)
0xa226  ldloc.3
0xa227  ldloc.s  4
0xa229  callvirt instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.ReverseGeocodeRequest::set_Location(class Microsoft.SharePoint.Spx.WebSite.GeocodeService.Location value)
0xa22e  ldstr    aBasichttpbindi_0// "BasicHttpBinding_IGeocodeService"
0xa233  newobj   instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeServiceClient::.ctor(string endpointConfigurationName)
0xa238  stloc.s  5
0xa23a  ldloc.s  5
0xa23c  ldloc.3
0xa23d  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResponse Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeServiceClient::ReverseGeocode(class Microsoft.SharePoint.Spx.WebSite.GeocodeService.ReverseGeocodeRequest request)
0xa242  stloc.1
0xa243  leave.s  loc_A27B
0xa245  stloc.s  6
0xa247  ldc.i4.0
0xa248  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0xa24d  ldc.i4.s 0x32
0xa24f  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::CLID
0xa254  ldloc.0
0xa255  ldstr    aReversegeocode// "ReverseGeocodeRequest failed: {0}"
0xa25a  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0xa25f  ldc.i4.1
0xa260  newarr   [mscorlib]System.Object
0xa265  stloc.s  7
0xa267  ldloc.s  7
0xa269  ldc.i4.0
0xa26a  ldloc.s  6
0xa26c  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetExceptionString(class [mscorlib]System.Exception)
0xa271  stelem.ref
0xa272  ldloc.s  7
0xa274  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xa279  leave.s  loc_A27B
0xa27b  ldloc.1
0xa27c  ret
```
