# Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::FindAddress

- ea: `0x9d30`
- end: `0x9dde`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::FindAddress`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0xc060`

## callees

- `0x9d30`
- `0xabd0`
- `0x16430`
- `0x16440`
- `0x16600`
- `0x166f0`
- `0x16b50`
- `0x16b90`
- `0x16bc0`
- `0x16f20`
- `0x16fd0`
- `0x17810`
- `0x17840`
- `0x17f00`
- `0x17f40`

## string_xrefs

- `0x9d84`: `BasicHttpBinding_IGeocodeService`

## pseudocode

```c

```

## disassembly

```asm
0x9d30  newobj   instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeRequest::.ctor()
0x9d35  stloc.0
0x9d36  ldloc.0
0x9d37  newobj   instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.Credentials::.ctor()
0x9d3c  callvirt instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.RequestBase::set_Credentials(class Microsoft.SharePoint.Spx.WebSite.GeocodeService.Credentials value)
0x9d41  ldloc.0
0x9d42  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.Credentials Microsoft.SharePoint.Spx.WebSite.GeocodeService.RequestBase::get_Credentials()
0x9d47  call     string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_BingMapKey()
0x9d4c  callvirt instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.Credentials::set_ApplicationId(string value)
0x9d51  ldloc.0
0x9d52  ldarg.0
0x9d53  callvirt instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeRequest::set_Query(string value)
0x9d58  ldc.i4.1
0x9d59  newarr   Microsoft.SharePoint.Spx.WebSite.GeocodeService.ConfidenceFilter
0x9d5e  stloc.1
0x9d5f  ldloc.1
0x9d60  ldc.i4.0
0x9d61  newobj   instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.ConfidenceFilter::.ctor()
0x9d66  stelem.ref
0x9d67  ldloc.1
0x9d68  ldc.i4.0
0x9d69  ldelem.ref
0x9d6a  ldc.i4.0
0x9d6b  callvirt instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.ConfidenceFilter::set_MinimumConfidence(valuetype Microsoft.SharePoint.Spx.WebSite.GeocodeService.Confidence value)
0x9d70  newobj   instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeOptions::.ctor()
0x9d75  stloc.2
0x9d76  ldloc.2
0x9d77  ldloc.1
0x9d78  callvirt instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeOptions::set_Filters(class Microsoft.SharePoint.Spx.WebSite.GeocodeService.FilterBase[] value)
0x9d7d  ldloc.0
0x9d7e  ldloc.2
0x9d7f  callvirt instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeRequest::set_Options(class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeOptions value)
0x9d84  ldstr    aBasichttpbindi_0// "BasicHttpBinding_IGeocodeService"
0x9d89  newobj   instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeServiceClient::.ctor(string endpointConfigurationName)
0x9d8e  stloc.3
0x9d8f  ldloc.3
0x9d90  ldloc.0
0x9d91  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResponse Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeServiceClient::Geocode(class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeRequest request)
0x9d96  stloc.s  4
0x9d98  ldloc.s  4
0x9d9a  stloc.s  6
0x9d9c  leave.s  loc_9DDB
0x9d9e  stloc.s  5
0x9da0  ldc.i4.0
0x9da1  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0x9da6  ldc.i4.s 0x32
0x9da8  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::CLID
0x9dad  ldstr    aFindaddress// "FindAddress"
0x9db2  ldstr    aFailedFindaddr// "Failed FindAddress: {0}"
0x9db7  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0x9dbc  ldc.i4.1
0x9dbd  newarr   [mscorlib]System.Object
0x9dc2  stloc.s  7
0x9dc4  ldloc.s  7
0x9dc6  ldc.i4.0
0x9dc7  ldloc.s  5
0x9dc9  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetExceptionString(class [mscorlib]System.Exception)
0x9dce  stelem.ref
0x9dcf  ldloc.s  7
0x9dd1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x9dd6  ldnull
0x9dd7  stloc.s  6
0x9dd9  leave.s  loc_9DDB
0x9ddb  ldloc.s  6
0x9ddd  ret
```
