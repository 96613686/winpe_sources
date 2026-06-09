# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.ComponentUtils::AddRdlObjectToReport

- ea: `0xda0`
- end: `0xea8`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.ComponentUtils::AddRdlObjectToReport`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x410`

## callees

- `0xda0`

## pseudocode

```c

```

## disassembly

```asm
0xda0  ldarg.0
0xda1  brtrue.s loc_DAE
0xda3  ldstr    aReport// "report"
0xda8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xdad  throw
0xdae  ldarg.1
0xdaf  isinst   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSource
0xdb4  brfalse.s loc_DDF
0xdb6  ldarg.0
0xdb7  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSource> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report::get_DataSources()
0xdbc  ldarg.1
0xdbd  castclass [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSource
0xdc2  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSource>::Contains(var<u1>)
0xdc7  brtrue.s loc_DDF
0xdc9  ldarg.0
0xdca  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSource> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report::get_DataSources()
0xdcf  ldarg.1
0xdd0  castclass [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSource
0xdd5  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSource>::Add(var<u1>)
0xdda  br       loc_EA6
0xddf  ldarg.1
0xde0  isinst   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet
0xde5  brfalse.s loc_E10
0xde7  ldarg.0
0xde8  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report::get_DataSets()
0xded  ldarg.1
0xdee  castclass [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet
0xdf3  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet>::Contains(var<u1>)
0xdf8  brtrue.s loc_E10
0xdfa  ldarg.0
0xdfb  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report::get_DataSets()
0xe00  ldarg.1
0xe01  castclass [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet
0xe06  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet>::Add(var<u1>)
0xe0b  br       loc_EA6
0xe10  ldarg.1
0xe11  isinst   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportParameter
0xe16  brfalse.s loc_E3E
0xe18  ldarg.0
0xe19  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportParameter> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report::get_ReportParameters()
0xe1e  ldarg.1
0xe1f  castclass [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportParameter
0xe24  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportParameter>::Contains(var<u1>)
0xe29  brtrue.s loc_E3E
0xe2b  ldarg.0
0xe2c  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportParameter> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report::get_ReportParameters()
0xe31  ldarg.1
0xe32  castclass [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportParameter
0xe37  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportParameter>::Add(var<u1>)
0xe3c  br.s     loc_EA6
0xe3e  ldarg.1
0xe3f  isinst   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem
0xe44  brfalse.s loc_E76
0xe46  ldarg.0
0xe47  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Body [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report::get_Body()
0xe4c  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Body::get_ReportItems()
0xe51  ldarg.1
0xe52  castclass [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem
0xe57  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem>::Contains(var<u1>)
0xe5c  brtrue.s loc_E76
0xe5e  ldarg.0
0xe5f  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Body [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report::get_Body()
0xe64  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Body::get_ReportItems()
0xe69  ldarg.1
0xe6a  castclass [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem
0xe6f  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem>::Add(var<u1>)
0xe74  br.s     loc_EA6
0xe76  ldarg.1
0xe77  isinst   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.EmbeddedImage
0xe7c  brfalse.s loc_EA4
0xe7e  ldarg.0
0xe7f  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.EmbeddedImage> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report::get_EmbeddedImages()
0xe84  ldarg.1
0xe85  castclass [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.EmbeddedImage
0xe8a  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.EmbeddedImage>::Contains(var<u1>)
0xe8f  brtrue.s loc_EA4
0xe91  ldarg.0
0xe92  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.EmbeddedImage> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report::get_EmbeddedImages()
0xe97  ldarg.1
0xe98  castclass [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.EmbeddedImage
0xe9d  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.EmbeddedImage>::Add(var<u1>)
0xea2  br.s     loc_EA6
0xea4  ldc.i4.0
0xea5  ret
0xea6  ldc.i4.1
0xea7  ret
```
