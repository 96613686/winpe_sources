# Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::CreateRdlDataSet

- ea: `0x5b0`
- end: `0x6c7`
- name: `Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::CreateRdlDataSet`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x5b0`
- `0xb590`

## pseudocode

```c

```

## disassembly

```asm
0x5b0  newobj   instance void <>c__DisplayClass18_0::.ctor()
0x5b5  stloc.0
0x5b6  ldloc.0
0x5b7  ldarg.2
0x5b8  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <>c__DisplayClass18_0::createQueryParameterNames
0x5bd  ldarg.0
0x5be  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet::get_DataSet()
0x5c3  callvirt instance string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSetBase::get_Name()
0x5c8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5cd  brfalse.s loc_5DF
0x5cf  ldarg.0
0x5d0  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet::get_DataSet()
0x5d5  ldstr    aDataset1// "DataSet1"
0x5da  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSetBase::set_Name(string)
0x5df  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet::.ctor()
0x5e4  dup
0x5e5  ldarg.0
0x5e6  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet::get_DataSet()
0x5eb  callvirt instance string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSetBase::get_Name()
0x5f0  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSetBase::set_Name(string)
0x5f5  dup
0x5f6  ldarg.0
0x5f7  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet::get_DataSet()
0x5fc  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet::get_Fields()
0x601  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet::set_Fields(class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field>)
0x606  stloc.1
0x607  ldloc.1
0x608  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet::get_Fields()
0x60d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field>::GetEnumerator()
0x612  stloc.2
0x613  br.s     loc_649
0x615  ldloc.2
0x616  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field>::get_Current()
0x61b  stloc.3
0x61c  ldloc.3
0x61d  ldloc.3
0x61e  callvirt instance string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field::get_Name()
0x623  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field::set_DataField(string)
0x628  ldloc.3
0x629  callvirt instance valuetype [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field::get_Value()
0x62e  stloc.s  4
0x630  ldloca.s 4
0x632  call     instance bool [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression::get_IsExpression()
0x637  brfalse.s loc_649
0x639  ldloc.3
0x63a  ldloca.s 4
0x63c  initobj  [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression
0x642  ldloc.s  4
0x644  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field::set_Value(valuetype [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression)
0x649  ldloc.2
0x64a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x64f  brtrue.s loc_615
0x651  leave.s  loc_65D
0x653  ldloc.2
0x654  brfalse.s loc_65C
0x656  ldloc.2
0x657  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x65c  endfinally
0x65d  ldloc.1
0x65e  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSet::.ctor()
0x663  dup
0x664  ldarg.1
0x665  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSet::set_SharedDataSetReference(string)
0x66a  dup
0x66b  ldarg.0
0x66c  callvirt instance string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet::get_ReportServerUrl()
0x671  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSet::set_ReportServerUrl(string)
0x676  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet::set_SharedDataSet(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSet)
0x67b  ldloc.0
0x67c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <>c__DisplayClass18_0::createQueryParameterNames
0x681  brfalse.s loc_6C5
0x683  ldloc.1
0x684  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSet [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet::get_SharedDataSet()
0x689  ldarg.0
0x68a  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.SharedDataSet::get_DataSet()
0x68f  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.Query [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSet::get_Query()
0x694  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSetParameter> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.Query::get_DataSetParameters()
0x699  ldnull
0x69a  ldftn    class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.QueryParameter Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::CreateRdlQueryParameter(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSetParameter parameter)
0x6a0  newobj   instance void class [mscorlib]System.Func`2<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSets.DataSetParameter, class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.QueryParameter>::.ctor(object, native int)
0x6a5  call     T0x2B000001
0x6aa  ldloc.0
0x6ab  ldftn    instance bool <>c__DisplayClass18_0::<CreateRdlDataSet>b__0(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.QueryParameter p)
0x6b1  newobj   instance void class [mscorlib]System.Func`2<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.QueryParameter, bool>::.ctor(object, native int)
0x6b6  call     T0x2B000002
0x6bb  call     T0x2B000003
0x6c0  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSet::set_QueryParameters(class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.QueryParameter>)
0x6c5  ldloc.1
0x6c6  ret
```
