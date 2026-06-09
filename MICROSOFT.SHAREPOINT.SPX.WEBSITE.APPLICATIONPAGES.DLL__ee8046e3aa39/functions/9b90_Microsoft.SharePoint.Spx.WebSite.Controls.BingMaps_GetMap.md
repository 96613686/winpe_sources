# Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::GetMap

- ea: `0x9b90`
- end: `0x9cdd`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::GetMap`
- size: `333`
- prototype: ``
- caller_count: `0`
- callee_count: `34`
- tags: `service_task, broker_com_uri`

## callees

- `0x9b90`
- `0xabd0`
- `0x17f90`
- `0x17fa0`
- `0x17fe0`
- `0x18160`
- `0x18250`
- `0x18600`
- `0x18610`
- `0x18690`
- `0x186d0`
- `0x18700`
- `0x18b30`
- `0x18b40`
- `0x18b70`
- `0x18b80`
- `0x18c30`
- `0x18da0`
- `0x18de0`
- `0x18e90`
- `0x191f0`
- `0x19200`
- `0x19240`
- `0x192c0`
- `0x19340`
- `0x193f0`
- `0x19440`
- `0x19480`
- `0x194b0`
- `0x194c0`
- `0x19570`
- `0x19930`
- `0x1a240`
- `0x1a290`

## string_xrefs

- `0x9c8a`: `BasicHttpBinding_IImageryService`

## pseudocode

```c

```

## disassembly

```asm
0x9b90  newobj   instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriResponse::.ctor()
0x9b95  stloc.0
0x9b96  newobj   instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::.ctor()
0x9b9b  stloc.1
0x9b9c  ldloc.1
0x9b9d  newobj   instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Credentials::.ctor()
0x9ba2  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.RequestBase::set_Credentials(class Microsoft.SharePoint.Spx.WebSite.ImageryService.Credentials value)
0x9ba7  ldloc.1
0x9ba8  callvirt instance class Microsoft.SharePoint.Spx.WebSite.ImageryService.Credentials Microsoft.SharePoint.Spx.WebSite.ImageryService.RequestBase::get_Credentials()
0x9bad  call     string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_BingMapKey()
0x9bb2  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Credentials::set_ApplicationId(string value)
0x9bb7  ldloc.1
0x9bb8  newobj   instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::.ctor()
0x9bbd  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::set_Center(class Microsoft.SharePoint.Spx.WebSite.ImageryService.Location value)
0x9bc2  ldloc.1
0x9bc3  ldarg.0
0x9bc4  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.RequestBase::set_Culture(string value)
0x9bc9  newobj   instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::.ctor()
0x9bce  stloc.2
0x9bcf  ldloc.2
0x9bd0  ldc.i4.s 9
0x9bd2  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::set_Style(valuetype Microsoft.SharePoint.Spx.WebSite.ImageryService.MapStyle value)
0x9bd7  ldloc.2
0x9bd8  ldc.i4.s 0xA
0x9bda  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x9bdf  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::set_ZoomLevel(valuetype [mscorlib]System.Nullable`1<int32> value)
0x9be4  ldloc.2
0x9be5  newobj   instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint::.ctor()
0x9bea  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::set_ImageSize(class Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint value)
0x9bef  ldloc.2
0x9bf0  callvirt instance class Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::get_ImageSize()
0x9bf5  ldc.i4   0x190
0x9bfa  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint::set_Height(int32 value)
0x9bff  ldloc.2
0x9c00  callvirt instance class Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::get_ImageSize()
0x9c05  ldc.i4   0x258
0x9c0a  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint::set_Width(int32 value)
0x9c0f  ldloc.2
0x9c10  ldc.i4.1
0x9c11  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions::set_ImageType(valuetype Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageType value)
0x9c16  ldloc.1
0x9c17  ldloc.2
0x9c18  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::set_Options(class Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions value)
0x9c1d  ldc.i4.1
0x9c1e  newarr   Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin
0x9c23  stloc.3
0x9c24  ldloc.3
0x9c25  ldc.i4.0
0x9c26  newobj   instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin::.ctor()
0x9c2b  stelem.ref
0x9c2c  ldloc.3
0x9c2d  ldc.i4.0
0x9c2e  ldelem.ref
0x9c2f  ldstr    a11// "11"
0x9c34  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin::set_IconStyle(string value)
0x9c39  ldloc.3
0x9c3a  ldc.i4.0
0x9c3b  ldelem.ref
0x9c3c  ldstr    aCp// "CP"
0x9c41  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin::set_Label(string value)
0x9c46  ldloc.3
0x9c47  ldc.i4.0
0x9c48  ldelem.ref
0x9c49  newobj   instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::.ctor()
0x9c4e  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin::set_Location(class Microsoft.SharePoint.Spx.WebSite.ImageryService.Location value)
0x9c53  ldloc.3
0x9c54  ldc.i4.0
0x9c55  ldelem.ref
0x9c56  callvirt instance class Microsoft.SharePoint.Spx.WebSite.ImageryService.Location Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin::get_Location()
0x9c5b  ldloc.1
0x9c5c  callvirt instance class Microsoft.SharePoint.Spx.WebSite.ImageryService.Location Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::get_Center()
0x9c61  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::get_Latitude()
0x9c66  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::set_Latitude(float64 value)
0x9c6b  ldloc.3
0x9c6c  ldc.i4.0
0x9c6d  ldelem.ref
0x9c6e  callvirt instance class Microsoft.SharePoint.Spx.WebSite.ImageryService.Location Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin::get_Location()
0x9c73  ldloc.1
0x9c74  callvirt instance class Microsoft.SharePoint.Spx.WebSite.ImageryService.Location Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::get_Center()
0x9c79  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::get_Longitude()
0x9c7e  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.Location::set_Longitude(float64 value)
0x9c83  ldloc.1
0x9c84  ldloc.3
0x9c85  callvirt instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::set_Pushpins(class Microsoft.SharePoint.Spx.WebSite.ImageryService.Pushpin[] value)
0x9c8a  ldstr    aBasichttpbindi// "BasicHttpBinding_IImageryService"
0x9c8f  newobj   instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryServiceClient::.ctor(string endpointConfigurationName)
0x9c94  stloc.s  4
0x9c96  ldloc.s  4
0x9c98  ldloc.1
0x9c99  callvirt instance class Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriResponse Microsoft.SharePoint.Spx.WebSite.ImageryService.ImageryServiceClient::GetMapUri(class Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest request)
0x9c9e  stloc.0
0x9c9f  leave.s  loc_9CDB
0x9ca1  stloc.s  5
0x9ca3  ldc.i4.0
0x9ca4  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0x9ca9  ldc.i4.s 0x32
0x9cab  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::CLID
0x9cb0  ldstr    aGetmap// "GetMap"
0x9cb5  ldstr    aFailedToGetMap// "Failed to get Map: {0}"
0x9cba  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0x9cbf  ldc.i4.1
0x9cc0  newarr   [mscorlib]System.Object
0x9cc5  stloc.s  6
0x9cc7  ldloc.s  6
0x9cc9  ldc.i4.0
0x9cca  ldloc.s  5
0x9ccc  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetExceptionString(class [mscorlib]System.Exception)
0x9cd1  stelem.ref
0x9cd2  ldloc.s  6
0x9cd4  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x9cd9  leave.s  loc_9CDB
0x9cdb  ldloc.0
0x9cdc  ret
```
