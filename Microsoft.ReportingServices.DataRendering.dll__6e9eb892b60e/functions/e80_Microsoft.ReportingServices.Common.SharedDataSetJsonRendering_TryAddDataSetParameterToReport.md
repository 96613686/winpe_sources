# Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::TryAddDataSetParameterToReport

- ea: `0xe80`
- end: `0xee7`
- name: `Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::TryAddDataSetParameterToReport`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xef0`

## callees

- `0xdb0`
- `0xe20`
- `0xe80`
- `0xb670`

## pseudocode

```c

```

## disassembly

```asm
0xe80  newobj   instance void <>c__DisplayClass36_0::.ctor()
0xe85  stloc.0
0xe86  ldloc.0
0xe87  ldarg.2
0xe88  stfld    string <>c__DisplayClass36_0::parameterName
0xe8d  ldarg.1
0xe8e  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSet [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet::get_SharedDataSet()
0xe93  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.QueryParameter> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.SharedDataSet::get_QueryParameters()
0xe98  ldloc.0
0xe99  ldftn    instance bool <>c__DisplayClass36_0::<TryAddDataSetParameterToReport>b__0(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.QueryParameter x)
0xe9f  newobj   instance void class [mscorlib]System.Func`2<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.QueryParameter, bool>::.ctor(object, native int)
0xea4  call     T0x2B000009
0xea9  stloc.1
0xeaa  ldloc.1
0xeab  brfalse.s loc_EE5
0xead  ldarg.3
0xeae  ldloc.1
0xeaf  ldloca.s 2
0xeb1  call     class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportParameter Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::CreateReportParameter(string value, class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.QueryParameter queryParameter, [out] string& name)
0xeb6  stloc.3
0xeb7  ldloc.3
0xeb8  ldarg.s  4
0xeba  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportParameter::set_MultiValue(bool)
0xebf  ldarg.0
0xec0  ldloc.3
0xec1  ldarg.s  5
0xec3  call     void Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::AddReportParameter(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report report, class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportParameter reportParameter, int32 reportParameterIndex)
0xec8  ldloc.1
0xec9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xece  ldstr    aParameters0Val// "=Parameters!{0}.Value"
0xed3  ldloc.2
0xed4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xed9  call     valuetype [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression::op_Implicit(string)
0xede  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.QueryParameter::set_Value(valuetype [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression)
0xee3  ldc.i4.1
0xee4  ret
0xee5  ldc.i4.0
0xee6  ret
```
