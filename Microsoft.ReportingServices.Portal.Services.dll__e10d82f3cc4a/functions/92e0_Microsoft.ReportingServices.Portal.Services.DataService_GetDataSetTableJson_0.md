# Microsoft.ReportingServices.Portal.Services.DataService::GetDataSetTableJson_0

- ea: `0x92e0`
- end: `0x936c`
- name: `Microsoft.ReportingServices.Portal.Services.DataService::GetDataSetTableJson_0`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x91a0`

## callees

- `0x8f60`
- `0x90b0`
- `0x9250`
- `0x92e0`
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
0x92e0  ldarg.1
0x92e1  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x92e6  stloc.0
0x92e7  ldarg.0
0x92e8  ldloc.0
0x92e9  ldarg.2
0x92ea  call     instance string Microsoft.ReportingServices.Portal.Services.DataService::ResolveCatalogPath(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, valuetype [mscorlib]System.Guid key)
0x92ef  stloc.1
0x92f0  ldarg.s  5
0x92f2  ldc.i4.0
0x92f3  stind.i1
0x92f4  ldarg.s  4
0x92f6  call     void Microsoft.ReportingServices.Portal.Services.DataService::CheckMaxRows(valuetype [mscorlib]System.Nullable`1<int32> maxRows)
0x92fb  ldarg.0
0x92fc  ldloc.0
0x92fd  ldarg.1
0x92fe  ldloc.1
0x92ff  call     instance unsigned int8[] Microsoft.ReportingServices.Portal.Services.DataService::GetDataSetDefinitionBytes(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x9304  stloc.2
0x9305  ldloc.2
0x9306  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetSchema Microsoft.ReportingServices.Portal.Services.DataService::CreateDataSetSchema(unsigned int8[] dataSetDefinitionBytes)
0x930b  stloc.3
0x930c  ldloc.3
0x930d  ldarg.3
0x930e  call     void Microsoft.ReportingServices.Portal.Services.DataService::CheckRequiredDataSetParameters(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetSchema dataSetSchema, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter> parameterOverrides)
0x9313  ldarga.s 4
0x9315  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x931a  brtrue.s loc_933F
0x931c  ldarg.0
0x931d  ldloc.0
0x931e  ldarg.2
0x931f  ldarg.3
0x9320  ldloc.3
0x9321  ldarg.1
0x9322  ldloc.1
0x9323  call     instance unsigned int8[] Microsoft.ReportingServices.Portal.Services.DataService::GetCachedDataSetJson(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, valuetype [mscorlib]System.Guid key, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter> parameterOverrides, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetSchema dataSetSchema, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x9328  stloc.s  6
0x932a  ldloc.s  6
0x932c  brfalse.s loc_933F
0x932e  ldarg.s  5
0x9330  ldc.i4.1
0x9331  stind.i1
0x9332  ldloc.s  6
0x9334  call     unsigned int8[] Microsoft.ReportingServices.Portal.Services.DataService::DecompressGZipBytes(unsigned int8[] compressedBytes)
0x9339  call     string [ReportingServicesLibrary]Microsoft.ReportingServices.Common.ConversionUtils::Utf8BytesToString(unsigned int8[])
0x933e  ret
0x933f  ldloc.2
0x9340  call     class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet [ReportingServicesLibrary]Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetRdlSharedDataSet(unsigned int8[])
0x9345  stloc.s  4
0x9347  ldloc.0
0x9348  ldloc.1
0x9349  call     string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SharedDataSetRendering::GetDataSourceExtensionForDataSet(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService, string)
0x934e  ldstr    aOledbMd// "OLEDB-MD"
0x9353  ldc.i4.5
0x9354  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x9359  stloc.s  5
0x935b  ldarg.0
0x935c  ldarg.1
0x935d  ldloc.s  4
0x935f  ldloc.1
0x9360  ldloc.3
0x9361  ldarg.3
0x9362  ldarg.s  4
0x9364  ldloc.s  5
0x9366  call     instance string Microsoft.ReportingServices.Portal.Services.DataService::GetDataSetTableJsonInternal(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet sharedDataSet, string path, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetSchema datasetSchema, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter> parameterOverrides, valuetype [mscorlib]System.Nullable`1<int32> maxRows, bool usingAS)
0x936b  ret
```
