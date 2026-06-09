# Microsoft.ReportingServices.Portal.Services.DataService::GetDataSetAggregatedValuesJson

- ea: `0x9450`
- end: `0x94d8`
- name: `Microsoft.ReportingServices.Portal.Services.DataService::GetDataSetAggregatedValuesJson`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x8f60`
- `0x90b0`
- `0x9540`
- `0x9800`
- `0x9bf0`
- `0x9e80`
- `0x20390`

## pseudocode

```c

```

## disassembly

```asm
0x9450  newobj   instance void <>c__DisplayClass19_0::.ctor()
0x9455  stloc.0
0x9456  ldloc.0
0x9457  ldarg.s  4
0x9459  stfld    string <>c__DisplayClass19_0::columnName
0x945e  ldarg.1
0x945f  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x9464  stloc.1
0x9465  ldarg.0
0x9466  ldloc.1
0x9467  ldarg.2
0x9468  call     instance string Microsoft.ReportingServices.Portal.Services.DataService::ResolveCatalogPath(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, valuetype [mscorlib]System.Guid key)
0x946d  stloc.2
0x946e  ldarg.0
0x946f  ldloc.1
0x9470  ldarg.1
0x9471  ldloc.2
0x9472  call     instance unsigned int8[] Microsoft.ReportingServices.Portal.Services.DataService::GetDataSetDefinitionBytes(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x9477  dup
0x9478  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetSchema Microsoft.ReportingServices.Portal.Services.DataService::CreateDataSetSchema(unsigned int8[] dataSetDefinitionBytes)
0x947d  stloc.3
0x947e  ldloc.3
0x947f  ldarg.3
0x9480  call     void Microsoft.ReportingServices.Portal.Services.DataService::CheckRequiredDataSetParameters(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetSchema dataSetSchema, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter> parameterOverrides)
0x9485  call     class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet [ReportingServicesLibrary]Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetRdlSharedDataSet(unsigned int8[])
0x948a  stloc.s  4
0x948c  ldloc.s  4
0x948e  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet::get_DataSet()
0x9493  ldloc.s  4
0x9495  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet::get_DataSet()
0x949a  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet::get_Fields()
0x949f  ldloc.0
0x94a0  ldftn    instance bool <>c__DisplayClass19_0::<GetDataSetAggregatedValuesJson>b__0(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field x)
0x94a6  newobj   instance void class [mscorlib]System.Func`2<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field, bool>::.ctor(object, native int)
0x94ab  call     T0x2B000086
0x94b0  call     T0x2B000087
0x94b5  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet::set_Fields(class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field>)
0x94ba  ldarg.0
0x94bb  ldarg.1
0x94bc  ldloc.s  4
0x94be  ldloc.2
0x94bf  ldloc.3
0x94c0  ldarg.3
0x94c1  ldarg.s  5
0x94c3  call     instance string Microsoft.ReportingServices.Portal.Services.DataService::GetDataSetAggregatedValuesInternal(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet sharedDataSet, string path, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetSchema datasetSchema, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter> parameterOverrides, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItemAggregation aggregation)
0x94c8  ldloca.s 5
0x94ca  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x94d0  ldloc.s  5
0x94d2  call     T0x2B000089
0x94d7  ret
```
