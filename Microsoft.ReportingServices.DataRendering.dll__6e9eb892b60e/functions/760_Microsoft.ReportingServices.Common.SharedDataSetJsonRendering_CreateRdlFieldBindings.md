# Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::CreateRdlFieldBindings

- ea: `0x760`
- end: `0x7cb`
- name: `Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::CreateRdlFieldBindings`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x760`
- `0x7d0`
- `0x7f0`
- `0x820`

## pseudocode

```c

```

## disassembly

```asm
0x760  ldc.i4.0
0x761  stloc.0
0x762  ldarg.0
0x763  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report::get_DataSets()
0x768  ldarg.1
0x769  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet>::Contains(var<u1>)
0x76e  brtrue.s loc_77C
0x770  ldarg.0
0x771  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report::get_DataSets()
0x776  ldarg.1
0x777  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet>::Add(var<u1>)
0x77c  ldarg.0
0x77d  call     class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Tablix Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetReportDataTablix(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report report)
0x782  dup
0x783  ldarg.1
0x784  callvirt instance string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSetBase::get_Name()
0x789  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataRegion::set_DataSetName(string)
0x78e  call     class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Rectangle Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetTablixDataRectangle(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Tablix tablix)
0x793  stloc.1
0x794  ldarg.1
0x795  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet::get_Fields()
0x79a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field>::GetEnumerator()
0x79f  stloc.2
0x7a0  br.s     loc_7B6
0x7a2  ldloc.2
0x7a3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field>::get_Current()
0x7a8  stloc.3
0x7a9  ldloc.1
0x7aa  ldloc.3
0x7ab  ldloc.0
0x7ac  ldc.i4.1
0x7ad  add
0x7ae  dup
0x7af  stloc.0
0x7b0  ldarg.2
0x7b1  call     void Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::AddDataField(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Rectangle rectangle, class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field field, int32 index, bool useAsSpecificExpression)
0x7b6  ldloc.2
0x7b7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7bc  brtrue.s loc_7A2
0x7be  leave.s  loc_7CA
0x7c0  ldloc.2
0x7c1  brfalse.s loc_7C9
0x7c3  ldloc.2
0x7c4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7c9  endfinally
0x7ca  ret
```
