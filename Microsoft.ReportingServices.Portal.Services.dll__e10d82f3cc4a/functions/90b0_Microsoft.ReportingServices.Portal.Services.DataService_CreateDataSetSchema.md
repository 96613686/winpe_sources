# Microsoft.ReportingServices.Portal.Services.DataService::CreateDataSetSchema

- ea: `0x90b0`
- end: `0x917c`
- name: `Microsoft.ReportingServices.Portal.Services.DataService::CreateDataSetSchema`
- size: `204`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x8f30`
- `0x91c0`
- `0x92e0`
- `0x93c0`
- `0x9450`

## callees

- `0x90b0`
- `0x9180`
- `0x202f0`

## pseudocode

```c

```

## disassembly

```asm
0x90b0  newobj   instance void <>c__DisplayClass11_0::.ctor()
0x90b5  stloc.0
0x90b6  ldarg.0
0x90b7  call     class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet [ReportingServicesLibrary]Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetRdlSharedDataSet(unsigned int8[])
0x90bc  stloc.1
0x90bd  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetSchema::.ctor()
0x90c2  dup
0x90c3  ldloc.1
0x90c4  callvirt instance string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet::get_Name()
0x90c9  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetSchema::set_Name(string)
0x90ce  stloc.2
0x90cf  ldloc.1
0x90d0  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet::get_DataSet()
0x90d5  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet::get_Fields()
0x90da  brfalse.s loc_9111
0x90dc  ldloc.2
0x90dd  ldloc.1
0x90de  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet::get_DataSet()
0x90e3  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet::get_Fields()
0x90e8  ldsfld   class [mscorlib]System.Func`2<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetField> <>c::<>9__11_0
0x90ed  dup
0x90ee  brtrue.s loc_9107
0x90f0  pop
0x90f1  ldsfld   class <>c <>c::<>9
0x90f6  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetField <>c::<CreateDataSetSchema>b__11_0(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field x)
0x90fc  newobj   instance void class [mscorlib]System.Func`2<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetField>::.ctor(object, native int)
0x9101  dup
0x9102  stsfld   class [mscorlib]System.Func`2<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetField> <>c::<>9__11_0
0x9107  call     T0x2B000083
0x910c  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetSchema::set_Fields(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetField>)
0x9111  ldloc.0
0x9112  ldarg.0
0x9113  call     class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.ReportingServices.Portal.Services.DataService::DeserializeDataSetDefinitionXml(unsigned int8[] dataSetDefinition)
0x9118  stfld    class [System.Xml.Linq]System.Xml.Linq.XElement <>c__DisplayClass11_0::dataSetSchemaXml
0x911d  ldloc.1
0x911e  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet::get_DataSet()
0x9123  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.Query [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet::get_Query()
0x9128  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSetParameter> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.Query::get_DataSetParameters()
0x912d  brfalse.s loc_917A
0x912f  ldloc.2
0x9130  ldloc.1
0x9131  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet::get_DataSet()
0x9136  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.Query [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet::get_Query()
0x913b  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSetParameter> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.Query::get_DataSetParameters()
0x9140  ldsfld   class [mscorlib]System.Func`2<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSetParameter, bool> <>c::<>9__11_1
0x9145  dup
0x9146  brtrue.s loc_915F
0x9148  pop
0x9149  ldsfld   class <>c <>c::<>9
0x914e  ldftn    instance bool <>c::<CreateDataSetSchema>b__11_1(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSetParameter x)
0x9154  newobj   instance void class [mscorlib]System.Func`2<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSetParameter, bool>::.ctor(object, native int)
0x9159  dup
0x915a  stsfld   class [mscorlib]System.Func`2<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSetParameter, bool> <>c::<>9__11_1
0x915f  call     T0x2B000084
0x9164  ldloc.0
0x9165  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameterInfo <>c__DisplayClass11_0::<CreateDataSetSchema>b__2(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSetParameter x)
0x916b  newobj   instance void class [mscorlib]System.Func`2<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSetParameter, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameterInfo>::.ctor(object, native int)
0x9170  call     T0x2B000085
0x9175  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetSchema::set_Parameters(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameterInfo>)
0x917a  ldloc.2
0x917b  ret
```
