# Microsoft.ReportingServices.Portal.Services.DataService::GetDataSetTableJsonInternal

- ea: `0x94e0`
- end: `0x953d`
- name: `Microsoft.ReportingServices.Portal.Services.DataService::GetDataSetTableJsonInternal`
- size: `93`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x91c0`
- `0x92e0`
- `0x93c0`

## callees

- `0x94e0`
- `0x98a0`
- `0x9b50`

## pseudocode

```c

```

## disassembly

```asm
0x94e0  ldarg.s  6
0x94e2  call     class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report [ReportingServicesLibrary]Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetTablixBasedRdlReport(valuetype [mscorlib]System.Nullable`1<int32>)
0x94e7  stloc.0
0x94e8  ldarg.s  5
0x94ea  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter, string> <>c::<>9__20_0
0x94ef  dup
0x94f0  brtrue.s loc_9509
0x94f2  pop
0x94f3  ldsfld   class <>c <>c::<>9
0x94f8  ldftn    instance string <>c::<GetDataSetTableJsonInternal>b__20_0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter x)
0x94fe  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter, string>::.ctor(object, native int)
0x9503  dup
0x9504  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter, string> <>c::<>9__20_0
0x9509  call     T0x2B00008A
0x950e  call     T0x2B000033
0x9513  stloc.1
0x9514  ldarg.2
0x9515  ldarg.3
0x9516  ldloc.1
0x9517  call     class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet [ReportingServicesLibrary]Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::CreateRdlDataSet(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x951c  stloc.2
0x951d  ldloc.0
0x951e  ldloc.2
0x951f  ldarg.s  7
0x9521  call     void [ReportingServicesLibrary]Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::CreateRdlFieldBindings(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report, class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet, bool)
0x9526  ldloc.0
0x9527  ldloc.2
0x9528  ldarg.s  4
0x952a  ldarg.s  5
0x952c  call     void Microsoft.ReportingServices.Portal.Services.DataService::BindDataSetParameters(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report report, class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet dataSet, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetSchema datasetSchema, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter> parameters)
0x9531  ldarg.0
0x9532  ldarg.1
0x9533  ldloc.0
0x9534  ldarg.3
0x9535  ldarg.s  6
0x9537  call     instance string Microsoft.ReportingServices.Portal.Services.DataService::RenderReport(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report rdlReport, string path, valuetype [mscorlib]System.Nullable`1<int32> maxRows)
0x953c  ret
```
