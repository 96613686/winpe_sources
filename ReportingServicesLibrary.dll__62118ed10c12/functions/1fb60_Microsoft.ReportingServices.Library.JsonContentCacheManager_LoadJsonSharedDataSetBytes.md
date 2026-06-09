# Microsoft.ReportingServices.Library.JsonContentCacheManager::LoadJsonSharedDataSetBytes

- ea: `0x1fb60`
- end: `0x1fbc6`
- name: `Microsoft.ReportingServices.Library.JsonContentCacheManager::LoadJsonSharedDataSetBytes`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1fdf0`

## callees

- `0xe840`
- `0xe940`
- `0xe9e0`
- `0x197a0`
- `0x77910`
- `0x77ac0`
- `0x77ae0`
- `0x77c90`
- `0x78460`

## string_xrefs

- `0x1fbb6`: `SHAREDDATASETJSON`
- `0x1fbbb`: `<DeviceInfo><SharedDataSetTable>true</SharedDataSetTable><JsonCacheCreation>true</JsonCacheCreation></DeviceInfo>`

## pseudocode

```c

```

## disassembly

```asm
0x1fb60  ldc.i4.0
0x1fb61  newobj   instance void Microsoft.ReportingServices.Library.RSService::.ctor(bool checkSecurity)
0x1fb66  dup
0x1fb67  ldarg.0
0x1fb68  call     unsigned int8[] Microsoft.ReportingServices.Library.SharedDataSetRendering::LoadDataSetDefinition(class Microsoft.ReportingServices.Library.RSService rsService, string dataSetPath)
0x1fb6d  call     class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetRdlSharedDataSet(unsigned int8[] dataSetDefinition)
0x1fb72  ldarg.1
0x1fb73  callvirt instance string[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection::GetParameterNames()
0x1fb78  stloc.0
0x1fb79  ldarg.0
0x1fb7a  ldloc.0
0x1fb7b  call     class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::CreateRdlDataSet(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet sharedDataSet, string path, [opt] class [mscorlib]System.Collections.Generic.IEnumerable`1<string> createQueryParameterNames)
0x1fb80  stloc.1
0x1fb81  ldloca.s 4
0x1fb83  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1fb89  ldloc.s  4
0x1fb8b  call     class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetTablixBasedRdlReport([opt] valuetype [mscorlib]System.Nullable`1<int32> maxRows)
0x1fb90  stloc.2
0x1fb91  dup
0x1fb92  ldarg.0
0x1fb93  call     string Microsoft.ReportingServices.Library.SharedDataSetRendering::GetDataSourceExtensionForDataSet(class Microsoft.ReportingServices.Library.RSService rsService, string path)
0x1fb98  ldstr    aOledbMd// "OLEDB-MD"
0x1fb9d  ldc.i4.5
0x1fb9e  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1fba3  stloc.3
0x1fba4  ldloc.2
0x1fba5  ldloc.1
0x1fba6  ldloc.3
0x1fba7  call     void Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::CreateRdlFieldBindings(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report report, class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet dataSet, bool useAsSpecificExpression)
0x1fbac  ldloc.2
0x1fbad  ldloc.1
0x1fbae  ldarg.1
0x1fbaf  call     void Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::BindDataSetParameters(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report report, class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet dataSet, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection parameterInfoCollection)
0x1fbb4  ldloc.2
0x1fbb5  ldloc.1
0x1fbb6  ldstr    aShareddatasetj// "SHAREDDATASETJSON"
0x1fbbb  ldstr    aDeviceinfoShar// "<DeviceInfo><SharedDataSetTable>true</S"...
0x1fbc0  call     unsigned int8[] Microsoft.ReportingServices.Library.SharedDataSetRendering::GetSharedDataSetBytes(class Microsoft.ReportingServices.Library.RSService rsService, class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report baseReport, class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet dataSet, string renderFormat, [opt] string deviceInfo)
0x1fbc5  ret
```
