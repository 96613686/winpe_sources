# Microsoft.ReportingServices.Portal.Services.DataService::GetDataSetColumnJson

- ea: `0x91c0`
- end: `0x924e`
- name: `Microsoft.ReportingServices.Portal.Services.DataService::GetDataSetColumnJson`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x8f60`
- `0x90b0`
- `0x94e0`
- `0x9800`
- `0x9bf0`
- `0x9e80`
- `0x20350`

## pseudocode

```c

```

## disassembly

```asm
0x91c0  newobj   instance void <>c__DisplayClass14_0::.ctor()
0x91c5  stloc.0
0x91c6  ldloc.0
0x91c7  ldarg.s  4
0x91c9  stfld    string <>c__DisplayClass14_0::columnName
0x91ce  ldarg.1
0x91cf  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x91d4  stloc.1
0x91d5  ldarg.0
0x91d6  ldloc.1
0x91d7  ldarg.2
0x91d8  call     instance string Microsoft.ReportingServices.Portal.Services.DataService::ResolveCatalogPath(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, valuetype [mscorlib]System.Guid key)
0x91dd  stloc.2
0x91de  ldarg.0
0x91df  ldloc.1
0x91e0  ldarg.1
0x91e1  ldloc.2
0x91e2  call     instance unsigned int8[] Microsoft.ReportingServices.Portal.Services.DataService::GetDataSetDefinitionBytes(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x91e7  dup
0x91e8  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetSchema Microsoft.ReportingServices.Portal.Services.DataService::CreateDataSetSchema(unsigned int8[] dataSetDefinitionBytes)
0x91ed  stloc.3
0x91ee  ldloc.3
0x91ef  ldarg.3
0x91f0  call     void Microsoft.ReportingServices.Portal.Services.DataService::CheckRequiredDataSetParameters(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetSchema dataSetSchema, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter> parameterOverrides)
0x91f5  call     class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet [ReportingServicesLibrary]Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetRdlSharedDataSet(unsigned int8[])
0x91fa  stloc.s  4
0x91fc  ldloc.s  4
0x91fe  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet::get_DataSet()
0x9203  ldloc.s  4
0x9205  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet::get_DataSet()
0x920a  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet::get_Fields()
0x920f  ldloc.0
0x9210  ldftn    instance bool <>c__DisplayClass14_0::<GetDataSetColumnJson>b__0(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field x)
0x9216  newobj   instance void class [mscorlib]System.Func`2<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field, bool>::.ctor(object, native int)
0x921b  call     T0x2B000086
0x9220  call     T0x2B000087
0x9225  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet::set_Fields(class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field>)
0x922a  ldarg.0
0x922b  ldarg.1
0x922c  ldloc.s  4
0x922e  ldloc.2
0x922f  ldloc.3
0x9230  ldarg.3
0x9231  ldloca.s 5
0x9233  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x9239  ldloc.s  5
0x923b  ldc.i4.0
0x923c  call     instance string Microsoft.ReportingServices.Portal.Services.DataService::GetDataSetTableJsonInternal(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet sharedDataSet, string path, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetSchema datasetSchema, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter> parameterOverrides, valuetype [mscorlib]System.Nullable`1<int32> maxRows, bool usingAS)
0x9241  ldarg.s  5
0x9243  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x9248  call     T0x2B000088
0x924d  ret
```
