# Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::BindDataSetParameters

- ea: `0xef0`
- end: `0xf8f`
- name: `Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::BindDataSetParameters`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xe80`
- `0xef0`

## pseudocode

```c

```

## disassembly

```asm
0xef0  ldc.i4.0
0xef1  stloc.0
0xef2  ldarg.2
0xef3  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0xef8  stloc.1
0xef9  br.s     loc_F70
0xefb  ldloc.1
0xefc  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xf01  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfo
0xf06  stloc.2
0xf07  ldnull
0xf08  stloc.3
0xf09  ldloc.2
0xf0a  callvirt instance object[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfo::get_Values()
0xf0f  brfalse.s loc_F55
0xf11  ldloc.2
0xf12  callvirt instance object[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfo::get_Values()
0xf17  ldlen
0xf18  brfalse.s loc_F55
0xf1a  ldloc.2
0xf1b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf20  callvirt instance string[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfo::ValuesToStringArray(class [mscorlib]System.Globalization.CultureInfo)
0xf25  stloc.s  4
0xf27  ldloc.2
0xf28  callvirt instance object[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfo::get_Values()
0xf2d  ldlen
0xf2e  conv.i4
0xf2f  ldc.i4.1
0xf30  bne.un.s loc_F39
0xf32  ldloc.s  4
0xf34  ldc.i4.0
0xf35  ldelem.ref
0xf36  stloc.3
0xf37  br.s     loc_F55
0xf39  ldstr    aNewObject// "=new Object() {\""
0xf3e  ldstr    asc_EA48// "\",\""
0xf43  ldloc.s  4
0xf45  call     string [mscorlib]System.String::Join(string, string[])
0xf4a  ldstr    asc_EA50// "\"}"
0xf4f  call     string [mscorlib]System.String::Concat(string, string, string)
0xf54  stloc.3
0xf55  ldarg.0
0xf56  ldarg.1
0xf57  ldloc.2
0xf58  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterBase::get_Name()
0xf5d  ldloc.3
0xf5e  ldloc.2
0xf5f  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterBase::get_MultiValue()
0xf64  ldloc.0
0xf65  call     bool Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::TryAddDataSetParameterToReport(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report report, class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet dataSet, string parameterName, string parameterValue, bool multiValue, int32 reportParameterIndex)
0xf6a  brfalse.s loc_F70
0xf6c  ldloc.0
0xf6d  ldc.i4.1
0xf6e  add
0xf6f  stloc.0
0xf70  ldloc.1
0xf71  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xf76  brtrue.s loc_EFB
0xf78  leave.s  loc_F8E
0xf7a  ldloc.1
0xf7b  isinst   [mscorlib]System.IDisposable
0xf80  stloc.s  5
0xf82  ldloc.s  5
0xf84  brfalse.s loc_F8D
0xf86  ldloc.s  5
0xf88  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf8d  endfinally
0xf8e  ret
```
