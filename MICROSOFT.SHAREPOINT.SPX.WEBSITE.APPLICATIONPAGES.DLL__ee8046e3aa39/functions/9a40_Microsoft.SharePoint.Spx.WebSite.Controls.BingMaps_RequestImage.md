# Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::RequestImage

- ea: `0x9a40`
- end: `0x9b85`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::RequestImage`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `service_task, broker_com_uri`

## callers

- `0xba60`

## callees

- `0x9a40`
- `0xabd0`
- `0x17f90`
- `0x17fa0`
- `0x18160`
- `0x18250`
- `0x18600`
- `0x18610`
- `0x18690`
- `0x186d0`
- `0x18700`
- `0x18b40`
- `0x18b80`
- `0x18c30`
- `0x18da0`
- `0x18de0`
- `0x18e90`
- `0x191f0`
- `0x19200`
- `0x192c0`
- `0x19340`
- `0x193f0`
- `0x194b0`
- `0x194c0`
- `0x19570`
- `0x198f0`
- `0x1a240`
- `0x1a290`

## string_xrefs

- `0x9b22`: `BasicHttpBinding_IImageryService`
- `0x9b6e`: `Result Uri: `

## pseudocode

```c

```

## disassembly

```asm
0x9a40  ldstr    asc_21500// ""
0x9a45  stloc.0
0x9a46  newobj   instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::.ctor()
0x9a4b  stloc.1
0x9a4c  ldloc.1
0x9a4d  newobj   instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Credentials::.ctor()
0x9a52  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.RequestBase::set_Credentials(class Microsoft.SharePoint.Spx.WebSite.ImageryService.Credentials value)
0x9a57  ldloc.1
0x9a58  callvirt instance class Microsoft.SharePoint.Spx.WebSite.ImageryService.Credentials Microsoft.SharePoint.Spx.WebSite.ImageryService.RequestBase::get_Credentials()
0x9a5d  call     string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_BingMapKey()
0x9a62  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Credentials::set_ApplicationId(string value)
0x9a67  ldloc.1
0x9a68  newobj   instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::.ctor()
0x9a6d  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::set_Center(class Microsoft.SharePoint.Spx.WebSite.ImageryService.Location value)
0x9a72  ldloc.1
0x9a73  callvirt instance class Microsoft.SharePoint.Spx.WebSite.ImageryService.Location Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::get_Center()
0x9a78  ldarg.0
0x9a79  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::set_Latitude(float64 value)
0x9a7e  ldloc.1
0x9a7f  callvirt instance class Microsoft.SharePoint.Spx.WebSite.ImageryService.Location Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::get_Center()
0x9a84  ldarg.1
0x9a85  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::set_Longitude(float64 value)
0x9a8a  newobj   instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin::.ctor()
0x9a8f  stloc.2
0x9a90  ldloc.2
0x9a91  newobj   instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::.ctor()
0x9a96  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin::set_Location(class Microsoft.SharePoint.Spx.WebSite.ImageryService.Location value)
0x9a9b  ldloc.2
0x9a9c  callvirt instance class Microsoft.SharePoint.Spx.WebSite.ImageryService.Location Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin::get_Location()
0x9aa1  ldarg.0
0x9aa2  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::set_Latitude(float64 value)
0x9aa7  ldloc.2
0x9aa8  callvirt instance class Microsoft.SharePoint.Spx.WebSite.ImageryService.Location Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin::get_Location()
0x9aad  ldarg.1
0x9aae  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::set_Longitude(float64 value)
0x9ab3  ldc.i4.1
0x9ab4  newarr   Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin
0x9ab9  stloc.s  9
0x9abb  ldloc.s  9
0x9abd  ldc.i4.0
0x9abe  ldloc.2
0x9abf  stelem.ref
0x9ac0  ldloc.s  9
0x9ac2  stloc.3
0x9ac3  ldloc.1
0x9ac4  ldloc.3
0x9ac5  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::set_Pushpins(class Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin[] value)
0x9aca  newobj   instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::.ctor()
0x9acf  stloc.s  4
0x9ad1  ldloc.s  4
0x9ad3  ldc.i4.0
0x9ad4  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::set_Style(valuetype Microsoft.SharePoint.Spx.WebSite.ImageryService.MapStyle value)
0x9ad9  ldloc.s  4
0x9adb  ldc.i4.s 0x10
0x9add  call     int16 [mscorlib]System.Convert::ToInt16(int32)
0x9ae2  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x9ae7  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::set_ZoomLevel(valuetype [mscorlib]System.Nullable`1<int32> value)
0x9aec  ldloc.s  4
0x9aee  newobj   instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint::.ctor()
0x9af3  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::set_ImageSize(class Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint value)
0x9af8  ldloc.s  4
0x9afa  callvirt instance class Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::get_ImageSize()
0x9aff  ldc.i4   0x136
0x9b04  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint::set_Height(int32 value)
0x9b09  ldloc.s  4
0x9b0b  callvirt instance class Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::get_ImageSize()
0x9b10  ldc.i4   0x136
0x9b15  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint::set_Width(int32 value)
0x9b1a  ldloc.1
0x9b1b  ldloc.s  4
0x9b1d  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::set_Options(class Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions value)
0x9b22  ldstr    aBasichttpbindi// "BasicHttpBinding_IImageryService"
0x9b27  newobj   instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryServiceClient::.ctor(string endpointConfigurationName)
0x9b2c  stloc.s  5
0x9b2e  ldloc.s  5
0x9b30  ldloc.1
0x9b31  callvirt instance class Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriResponse Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryServiceClient::GetMapUri(class Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest request)
0x9b36  stloc.s  6
0x9b38  ldloc.s  6
0x9b3a  callvirt instance string Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriResponse::get_Uri()
0x9b3f  stloc.s  7
0x9b41  ldloc.s  7
0x9b43  stloc.0
0x9b44  leave.s  loc_9B5C
0x9b46  stloc.s  8
0x9b48  ldstr    aAnExceptionOcc// "An exception occurred: "
0x9b4d  ldloc.s  8
0x9b4f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x9b54  call     string [mscorlib]System.String::Concat(string, string)
0x9b59  stloc.0
0x9b5a  leave.s  loc_9B5C
0x9b5c  ldc.i4.0
0x9b5d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0x9b62  ldc.i4.s 0x64
0x9b64  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::CLID
0x9b69  ldstr    aRequestimage// "RequestImage"
0x9b6e  ldstr    aResultUri// "Result Uri: "
0x9b73  ldloc.0
0x9b74  call     string [mscorlib]System.String::Concat(string, string)
0x9b79  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0x9b7e  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x9b83  ldloc.0
0x9b84  ret
```
