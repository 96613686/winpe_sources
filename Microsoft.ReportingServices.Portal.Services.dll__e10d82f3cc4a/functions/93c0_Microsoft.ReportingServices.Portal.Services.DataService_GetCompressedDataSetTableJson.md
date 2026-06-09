# Microsoft.ReportingServices.Portal.Services.DataService::GetCompressedDataSetTableJson

- ea: `0x93c0`
- end: `0x9447`
- name: `Microsoft.ReportingServices.Portal.Services.DataService::GetCompressedDataSetTableJson`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x8f60`
- `0x90b0`
- `0x9370`
- `0x93c0`
- `0x94e0`
- `0x95b0`
- `0x9800`
- `0x99a0`
- `0x9bf0`
- `0x9e80`

## pseudocode

```c

```

## disassembly

```asm
0x93c0  ldarg.1
0x93c1  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x93c6  stloc.0
0x93c7  ldarg.0
0x93c8  ldloc.0
0x93c9  ldarg.2
0x93ca  call     instance string Microsoft.ReportingServices.Portal.Services.DataService::ResolveCatalogPath(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, valuetype [mscorlib]System.Guid key)
0x93cf  stloc.1
0x93d0  ldarg.s  5
0x93d2  ldc.i4.0
0x93d3  stind.i1
0x93d4  ldarg.s  4
0x93d6  call     void Microsoft.ReportingServices.Portal.Services.DataService::CheckMaxRows(valuetype [mscorlib]System.Nullable`1<int32> maxRows)
0x93db  ldarg.0
0x93dc  ldloc.0
0x93dd  ldarg.1
0x93de  ldloc.1
0x93df  call     instance unsigned int8[] Microsoft.ReportingServices.Portal.Services.DataService::GetDataSetDefinitionBytes(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x93e4  stloc.2
0x93e5  ldloc.2
0x93e6  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetSchema Microsoft.ReportingServices.Portal.Services.DataService::CreateDataSetSchema(unsigned int8[] dataSetDefinitionBytes)
0x93eb  stloc.3
0x93ec  ldloc.3
0x93ed  ldarg.3
0x93ee  call     void Microsoft.ReportingServices.Portal.Services.DataService::CheckRequiredDataSetParameters(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetSchema dataSetSchema, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter> parameterOverrides)
0x93f3  ldarga.s 4
0x93f5  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x93fa  brtrue.s loc_9415
0x93fc  ldarg.0
0x93fd  ldloc.0
0x93fe  ldarg.2
0x93ff  ldarg.3
0x9400  ldloc.3
0x9401  ldarg.1
0x9402  ldloc.1
0x9403  call     instance unsigned int8[] Microsoft.ReportingServices.Portal.Services.DataService::GetCachedDataSetJson(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, valuetype [mscorlib]System.Guid key, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter> parameterOverrides, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetSchema dataSetSchema, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x9408  stloc.s  6
0x940a  ldloc.s  6
0x940c  brfalse.s loc_9415
0x940e  ldarg.s  5
0x9410  ldc.i4.1
0x9411  stind.i1
0x9412  ldloc.s  6
0x9414  ret
0x9415  ldloc.2
0x9416  call     class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet [ReportingServicesLibrary]Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetRdlSharedDataSet(unsigned int8[])
0x941b  stloc.s  4
0x941d  ldloc.0
0x941e  ldloc.1
0x941f  call     string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SharedDataSetRendering::GetDataSourceExtensionForDataSet(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService, string)
0x9424  ldstr    aOledbMd// "OLEDB-MD"
0x9429  ldc.i4.5
0x942a  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x942f  stloc.s  5
0x9431  ldarg.0
0x9432  ldarg.1
0x9433  ldloc.s  4
0x9435  ldloc.1
0x9436  ldloc.3
0x9437  ldarg.3
0x9438  ldarg.s  4
0x943a  ldloc.s  5
0x943c  call     instance string Microsoft.ReportingServices.Portal.Services.DataService::GetDataSetTableJsonInternal(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet sharedDataSet, string path, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetSchema datasetSchema, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter> parameterOverrides, valuetype [mscorlib]System.Nullable`1<int32> maxRows, bool usingAS)
0x9441  call     unsigned int8[] Microsoft.ReportingServices.Portal.Services.DataService::CompressUtf8String(string value)
0x9446  ret
```
