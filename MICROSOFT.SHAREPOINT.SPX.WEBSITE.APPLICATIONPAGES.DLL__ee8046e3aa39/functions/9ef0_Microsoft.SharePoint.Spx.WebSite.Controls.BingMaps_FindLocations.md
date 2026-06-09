# Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::FindLocations

- ea: `0x9ef0`
- end: `0xa1dd`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::FindLocations`
- size: `749`
- prototype: ``
- caller_count: `0`
- callee_count: `37`
- tags: `service_task, broker_com_uri`

## callees

- `0x9ef0`
- `0xa1e0`
- `0xabd0`
- `0xd780`
- `0x16c10`
- `0x16c50`
- `0x16c90`
- `0x16cd0`
- `0x16d10`
- `0x16d50`
- `0x16d90`
- `0x17150`
- `0x17190`
- `0x17560`
- `0x175a0`
- `0x17ba0`
- `0x17c30`
- `0x17c70`
- `0x17cb0`
- `0x17d70`
- `0x1c640`
- `0x1c650`
- `0x1c810`
- `0x1c900`
- `0x1c950`
- `0x1ca00`
- `0x1ccc0`
- `0x1cd70`
- `0x1d300`
- `0x1d340`
- `0x1df90`
- `0x1dfd0`
- `0x1e360`
- `0x1eea0`
- `0x1f020`
- `0x1fd10`
- `0x1fd50`

## string_xrefs

- `0x9efc`: `BasicHttpBinding_ISearchService`

## pseudocode

```c

```

## disassembly

```asm
0x9ef0  ldstr    aBingmapsFindlo// "BingMaps:FindLocations"
0x9ef5  stloc.0
0x9ef6  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x9efb  stloc.1
0x9efc  ldstr    aBasichttpbindi_1// "BasicHttpBinding_ISearchService"
0x9f01  newobj   instance void Microsoft.SharePoint.Spx.WebSite.SearchService.SearchServiceClient::.ctor(string endpointConfigurationName)
0x9f06  stloc.2
0x9f07  newobj   instance void Microsoft.SharePoint.Spx.WebSite.SearchService.SearchRequest::.ctor()
0x9f0c  stloc.3
0x9f0d  newobj   instance void Microsoft.SharePoint.Spx.WebSite.SearchService.SearchResponse::.ctor()
0x9f12  stloc.s  4
0x9f14  ldloc.3
0x9f15  newobj   instance void Microsoft.SharePoint.Spx.WebSite.SearchService.Credentials::.ctor()
0x9f1a  callvirt instance void Microsoft.SharePoint.Spx.WebSite.SearchService.RequestBase::set_Credentials(class Microsoft.SharePoint.Spx.WebSite.SearchService.Credentials value)
0x9f1f  ldloc.3
0x9f20  callvirt instance class Microsoft.SharePoint.Spx.WebSite.SearchService.Credentials Microsoft.SharePoint.Spx.WebSite.SearchService.RequestBase::get_Credentials()
0x9f25  call     string Microsoft.SharePoint.Spx.WebSite.Controls.LocationMapConfig::get_BingMapKey()
0x9f2a  callvirt instance void Microsoft.SharePoint.Spx.WebSite.SearchService.Credentials::set_ApplicationId(string value)
0x9f2f  newobj   instance void Microsoft.SharePoint.Spx.WebSite.SearchService.ExecutionOptions::.ctor()
0x9f34  stloc.s  5
0x9f36  ldloc.s  5
0x9f38  ldc.i4.1
0x9f39  callvirt instance void Microsoft.SharePoint.Spx.WebSite.SearchService.ExecutionOptions::set_SuppressFaults(bool value)
0x9f3e  ldloc.3
0x9f3f  ldarg.0
0x9f40  callvirt instance void Microsoft.SharePoint.Spx.WebSite.SearchService.SearchRequest::set_Query(string value)
0x9f45  ldloc.2
0x9f46  ldloc.3
0x9f47  callvirt instance class Microsoft.SharePoint.Spx.WebSite.SearchService.SearchResponse Microsoft.SharePoint.Spx.WebSite.SearchService.SearchServiceClient::Search(class Microsoft.SharePoint.Spx.WebSite.SearchService.SearchRequest request)
0x9f4c  stloc.s  4
0x9f4e  leave.s  loc_9F86
0x9f50  stloc.s  6
0x9f52  ldc.i4.0
0x9f53  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0x9f58  ldc.i4.s 0x32
0x9f5a  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::CLID
0x9f5f  ldloc.0
0x9f60  ldstr    aFailedToFindLo// "Failed to find locations: {0}"
0x9f65  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0x9f6a  ldc.i4.1
0x9f6b  newarr   [mscorlib]System.Object
0x9f70  stloc.s  0x1B
0x9f72  ldloc.s  0x1B
0x9f74  ldc.i4.0
0x9f75  ldloc.s  6
0x9f77  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetExceptionString(class [mscorlib]System.Exception)
0x9f7c  stelem.ref
0x9f7d  ldloc.s  0x1B
0x9f7f  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x9f84  leave.s  loc_9F86
0x9f86  ldloc.s  4
0x9f88  brfalse  loc_A1DB
0x9f8d  ldloc.s  4
0x9f8f  callvirt instance class Microsoft.SharePoint.Spx.WebSite.SearchService.SearchResultSet[] Microsoft.SharePoint.Spx.WebSite.SearchService.SearchResponse::get_ResultSets()
0x9f94  brfalse  loc_A1DB
0x9f99  ldloc.s  4
0x9f9b  callvirt instance class Microsoft.SharePoint.Spx.WebSite.SearchService.SearchResultSet[] Microsoft.SharePoint.Spx.WebSite.SearchService.SearchResponse::get_ResultSets()
0x9fa0  stloc.s  0x1C
0x9fa2  ldc.i4.0
0x9fa3  stloc.s  0x1D
0x9fa5  br       loc_A1D0
0x9faa  ldloc.s  0x1C
0x9fac  ldloc.s  0x1D
0x9fae  ldelem.ref
0x9faf  stloc.s  7
0x9fb1  ldloc.s  7
0x9fb3  callvirt instance class Microsoft.SharePoint.Spx.WebSite.SearchService.SearchResultBase[] Microsoft.SharePoint.Spx.WebSite.SearchService.SearchResultSet::get_Results()
0x9fb8  stloc.s  0x1E
0x9fba  ldc.i4.0
0x9fbb  stloc.s  0x1F
0x9fbd  br       loc_A1BF
0x9fc2  ldloc.s  0x1E
0x9fc4  ldloc.s  0x1F
0x9fc6  ldelem.ref
0x9fc7  stloc.s  8
0x9fc9  ldloc.s  8
0x9fcb  callvirt instance class Microsoft.SharePoint.Spx.WebSite.SearchService.LocationData Microsoft.SharePoint.Spx.WebSite.SearchService.SearchResultBase::get_LocationData()
0x9fd0  callvirt instance class Microsoft.SharePoint.Spx.WebSite.SearchService.GeocodeLocation[] Microsoft.SharePoint.Spx.WebSite.SearchService.LocationData::get_Locations()
0x9fd5  stloc.s  0x20
0x9fd7  ldc.i4.0
0x9fd8  stloc.s  0x21
0x9fda  br       loc_A1AE
0x9fdf  ldloc.s  0x20
0x9fe1  ldloc.s  0x21
0x9fe3  ldelem.ref
0x9fe4  stloc.s  9
0x9fe6  ldloc.s  9
0x9fe8  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.SearchService.Location::get_Latitude()
0x9fed  ldloc.s  9
0x9fef  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.SearchService.Location::get_Longitude()
0x9ff4  call     class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResponse Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::MakeReverseGeocodeRequest(float64 latitude, float64 longitude)
0x9ff9  stloc.s  0xA
0x9ffb  ldloc.s  0xA
0x9ffd  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult[] Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResponse::get_Results()
0xa002  ldc.i4.0
0xa003  ldelem.ref
0xa004  callvirt instance valuetype Microsoft.SharePoint.Spx.WebSite.GeocodeService.Confidence Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult::get_Confidence()
0xa009  box      Microsoft.SharePoint.Spx.WebSite.GeocodeService.Confidence
0xa00e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa013  call     int16 [mscorlib]System.Convert::ToInt16(object, class [mscorlib]System.IFormatProvider)
0xa018  stloc.s  0xB
0xa01a  ldloc.s  0xA
0xa01c  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult[] Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResponse::get_Results()
0xa021  ldc.i4.0
0xa022  ldelem.ref
0xa023  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.Address Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult::get_Address()
0xa028  callvirt instance string Microsoft.SharePoint.Spx.WebSite.GeocodeService.Address::get_FormattedAddress()
0xa02d  stloc.s  0xC
0xa02f  ldloc.s  0xA
0xa031  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult[] Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResponse::get_Results()
0xa036  ldc.i4.0
0xa037  ldelem.ref
0xa038  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.Address Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult::get_Address()
0xa03d  callvirt instance string Microsoft.SharePoint.Spx.WebSite.GeocodeService.Address::get_AddressLine()
0xa042  stloc.s  0xD
0xa044  ldloc.s  0xA
0xa046  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult[] Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResponse::get_Results()
0xa04b  ldc.i4.0
0xa04c  ldelem.ref
0xa04d  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.Address Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult::get_Address()
0xa052  callvirt instance string Microsoft.SharePoint.Spx.WebSite.GeocodeService.Address::get_District()
0xa057  stloc.s  0xE
0xa059  ldloc.s  0xA
0xa05b  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult[] Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResponse::get_Results()
0xa060  ldc.i4.0
0xa061  ldelem.ref
0xa062  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.Address Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult::get_Address()
0xa067  callvirt instance string Microsoft.SharePoint.Spx.WebSite.GeocodeService.Address::get_AdminDistrict()
0xa06c  stloc.s  0xF
0xa06e  ldloc.s  0xA
0xa070  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult[] Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResponse::get_Results()
0xa075  ldc.i4.0
0xa076  ldelem.ref
0xa077  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.Address Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult::get_Address()
0xa07c  callvirt instance string Microsoft.SharePoint.Spx.WebSite.GeocodeService.Address::get_Locality()
0xa081  stloc.s  0x10
0xa083  ldloc.s  0xA
0xa085  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult[] Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResponse::get_Results()
0xa08a  ldc.i4.0
0xa08b  ldelem.ref
0xa08c  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.Address Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult::get_Address()
0xa091  callvirt instance string Microsoft.SharePoint.Spx.WebSite.GeocodeService.Address::get_PostalCode()
0xa096  stloc.s  0x11
0xa098  ldloc.s  0xA
0xa09a  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult[] Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResponse::get_Results()
0xa09f  ldc.i4.0
0xa0a0  ldelem.ref
0xa0a1  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.Address Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult::get_Address()
0xa0a6  callvirt instance string Microsoft.SharePoint.Spx.WebSite.GeocodeService.Address::get_CountryRegion()
0xa0ab  stloc.s  0x12
0xa0ad  ldloc.s  0xA
0xa0af  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult[] Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResponse::get_Results()
0xa0b4  ldc.i4.0
0xa0b5  ldelem.ref
0xa0b6  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeLocation[] Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult::get_Locations()
0xa0bb  ldc.i4.0
0xa0bc  ldelem.ref
0xa0bd  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.GeocodeService.Location::get_Latitude()
0xa0c2  stloc.s  0x13
0xa0c4  ldloc.s  0xA
0xa0c6  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult[] Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResponse::get_Results()
0xa0cb  ldc.i4.0
0xa0cc  ldelem.ref
0xa0cd  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeLocation[] Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult::get_Locations()
0xa0d2  ldc.i4.0
0xa0d3  ldelem.ref
0xa0d4  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.GeocodeService.Location::get_Longitude()
0xa0d9  stloc.s  0x14
0xa0db  ldloc.s  0xA
0xa0dd  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult[] Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResponse::get_Results()
0xa0e2  ldc.i4.0
0xa0e3  ldelem.ref
0xa0e4  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.Rectangle Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult::get_BestView()
0xa0e9  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.Location Microsoft.SharePoint.Spx.WebSite.GeocodeService.Rectangle::get_Northeast()
0xa0ee  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.GeocodeService.Location::get_Latitude()
0xa0f3  stloc.s  0x15
0xa0f5  ldloc.s  0xA
0xa0f7  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult[] Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResponse::get_Results()
0xa0fc  ldc.i4.0
0xa0fd  ldelem.ref
0xa0fe  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.Rectangle Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult::get_BestView()
0xa103  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.Location Microsoft.SharePoint.Spx.WebSite.GeocodeService.Rectangle::get_Northeast()
0xa108  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.GeocodeService.Location::get_Longitude()
0xa10d  stloc.s  0x16
0xa10f  ldloc.s  0xA
0xa111  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult[] Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResponse::get_Results()
0xa116  ldc.i4.0
0xa117  ldelem.ref
0xa118  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.Rectangle Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult::get_BestView()
0xa11d  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.Location Microsoft.SharePoint.Spx.WebSite.GeocodeService.Rectangle::get_Southwest()
0xa122  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.GeocodeService.Location::get_Latitude()
0xa127  stloc.s  0x17
0xa129  ldloc.s  0xA
0xa12b  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult[] Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResponse::get_Results()
0xa130  ldc.i4.0
0xa131  ldelem.ref
0xa132  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.Rectangle Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeResult::get_BestView()
0xa137  callvirt instance class Microsoft.SharePoint.Spx.WebSite.GeocodeService.Location Microsoft.SharePoint.Spx.WebSite.GeocodeService.Rectangle::get_Southwest()
0xa13c  callvirt instance float64 Microsoft.SharePoint.Spx.WebSite.GeocodeService.Location::get_Longitude()
0xa141  stloc.s  0x18
0xa143  ldloc.s  0xB
0xa145  conv.r8
0xa146  ldloc.s  0xC
0xa148  ldloc.s  0xD
0xa14a  ldloc.s  0xE
0xa14c  ldloc.s  0xF
0xa14e  ldloc.s  0x10
0xa150  ldloc.s  0x11
0xa152  ldloc.s  0x12
0xa154  ldloc.s  0x13
0xa156  ldloc.s  0x14
0xa158  ldloc.s  0x15
0xa15a  ldloc.s  0x16
0xa15c  ldloc.s  0x17
0xa15e  ldloc.s  0x18
0xa160  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointLocation::.ctor(float64 score, string formattedAddress, string addressLine, string primaryCity, string secondaryCity, string subdivision, string postalCode, string countryRegion, float64 latitude, float64 longitude, float64 northLatitude, float64 eastLongitude, float64 southLatitude, float64 westLongitude)
0xa165  stloc.s  0x19
0xa167  ldloc.1
0xa168  ldloc.s  0x19
0xa16a  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xa16f  pop
0xa170  leave.s  loc_A1A8
0xa172  stloc.s  0x1A
0xa174  ldc.i4.0
0xa175  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0xa17a  ldc.i4.s 0x32
0xa17c  ldsfld   string Microsoft.SharePoint.Spx.WebSite.Controls.BingMaps::CLID
0xa181  ldloc.0
0xa182  ldstr    aFailedToRevers// "Failed to Reverse Geo Code: {0}"
0xa187  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0xa18c  ldc.i4.1
0xa18d  newarr   [mscorlib]System.Object
0xa192  stloc.s  0x22
0xa194  ldloc.s  0x22
0xa196  ldc.i4.0
0xa197  ldloc.s  0x1A
0xa199  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetExceptionString(class [mscorlib]System.Exception)
0xa19e  stelem.ref
0xa19f  ldloc.s  0x22
0xa1a1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xa1a6  leave.s  loc_A1A8
0xa1a8  ldloc.s  0x21
0xa1aa  ldc.i4.1
0xa1ab  add
0xa1ac  stloc.s  0x21
0xa1ae  ldloc.s  0x21
0xa1b0  ldloc.s  0x20
0xa1b2  ldlen
0xa1b3  conv.i4
0xa1b4  blt      loc_9FDF
0xa1b9  ldloc.s  0x1F
0xa1bb  ldc.i4.1
0xa1bc  add
0xa1bd  stloc.s  0x1F
0xa1bf  ldloc.s  0x1F
0xa1c1  ldloc.s  0x1E
0xa1c3  ldlen
0xa1c4  conv.i4
0xa1c5  blt      loc_9FC2
0xa1ca  ldloc.s  0x1D
0xa1cc  ldc.i4.1
0xa1cd  add
0xa1ce  stloc.s  0x1D
0xa1d0  ldloc.s  0x1D
0xa1d2  ldloc.s  0x1C
0xa1d4  ldlen
0xa1d5  conv.i4
0xa1d6  blt      loc_9FAA
0xa1db  ldloc.1
0xa1dc  ret
```
