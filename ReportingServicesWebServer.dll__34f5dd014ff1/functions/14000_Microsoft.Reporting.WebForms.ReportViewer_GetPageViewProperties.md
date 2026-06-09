# Microsoft.Reporting.WebForms.ReportViewer::GetPageViewProperties

- ea: `0x14000`
- end: `0x14107`
- name: `Microsoft.Reporting.WebForms.ReportViewer::GetPageViewProperties`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14110`

## callees

- `0x5430`
- `0x12870`
- `0x128c0`
- `0x128e0`
- `0x14000`
- `0x141c0`
- `0x23790`
- `0x23810`
- `0x24350`

## string_xrefs

- `0x140bc`: `HashedReportPath`
- `0x140eb`: `HashedReportPath`

## pseudocode

```c

```

## disassembly

```asm
0x14000  ldarg.1
0x14001  ldstr    aHashedrvcid// "HashedRvcId"
0x14006  ldarg.0
0x14007  ldarg.0
0x14008  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1400d  call     instance string Microsoft.Reporting.WebForms.ReportViewer::GetSHA256Hash(string input)
0x14012  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x14017  ldarg.1
0x14018  ldstr    aProcessingmode_0// "ProcessingMode"
0x1401d  ldarg.0
0x1401e  call     instance valuetype Microsoft.Reporting.WebForms.ProcessingMode Microsoft.Reporting.WebForms.ReportViewer::get_ProcessingMode()
0x14023  stloc.0
0x14024  ldloca.s 0
0x14026  constrained. Microsoft.Reporting.WebForms.ProcessingMode
0x1402c  callvirt instance string [mscorlib]System.Object::ToString()
0x14031  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x14036  ldarg.0
0x14037  call     instance valuetype Microsoft.Reporting.WebForms.ProcessingMode Microsoft.Reporting.WebForms.ReportViewer::get_ProcessingMode()
0x1403c  ldc.i4.1
0x1403d  bne.un   loc_140D8
0x14042  ldsfld   string [mscorlib]System.String::Empty
0x14047  stloc.1
0x14048  ldsfld   string [mscorlib]System.String::Empty
0x1404d  stloc.2
0x1404e  ldarg.0
0x1404f  call     instance class Microsoft.Reporting.WebForms.ServerReport Microsoft.Reporting.WebForms.ReportViewer::get_ServerReport()
0x14054  brfalse.s loc_1408B
0x14056  ldarg.0
0x14057  call     instance class Microsoft.Reporting.WebForms.ServerReport Microsoft.Reporting.WebForms.ReportViewer::get_ServerReport()
0x1405c  callvirt instance class [System]System.Uri Microsoft.Reporting.WebForms.ServerReport::get_ReportServerUrl()
0x14061  ldnull
0x14062  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x14067  brfalse.s loc_1408B
0x14069  ldarg.0
0x1406a  call     instance class Microsoft.Reporting.WebForms.ServerReport Microsoft.Reporting.WebForms.ReportViewer::get_ServerReport()
0x1406f  callvirt instance class [System]System.Uri Microsoft.Reporting.WebForms.ServerReport::get_ReportServerUrl()
0x14074  callvirt instance string [mscorlib]System.Object::ToString()
0x14079  stloc.1
0x1407a  ldarg.0
0x1407b  call     instance class Microsoft.Reporting.WebForms.ServerReport Microsoft.Reporting.WebForms.ReportViewer::get_ServerReport()
0x14080  callvirt instance string Microsoft.Reporting.WebForms.ServerReport::GetServerVersion()
0x14085  stloc.2
0x14086  leave.s  loc_1408B
0x14088  pop
0x14089  leave.s  loc_1408B
0x1408b  ldarg.1
0x1408c  ldstr    aRsbuild// "RSBuild"
0x14091  ldloc.2
0x14092  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x14097  ldarg.1
0x14098  ldstr    aHashedinstance// "HashedInstanceId"
0x1409d  ldarg.0
0x1409e  ldloc.1
0x1409f  call     instance string Microsoft.Reporting.WebForms.ReportViewer::GetSHA256Hash(string input)
0x140a4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x140a9  ldarg.0
0x140aa  call     instance class Microsoft.Reporting.WebForms.ServerReport Microsoft.Reporting.WebForms.ReportViewer::get_ServerReport()
0x140af  callvirt instance string Microsoft.Reporting.WebForms.ServerReport::get_ReportPath()
0x140b4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x140b9  brtrue.s loc_14106
0x140bb  ldarg.1
0x140bc  ldstr    aHashedreportpa// "HashedReportPath"
0x140c1  ldarg.0
0x140c2  ldarg.0
0x140c3  call     instance class Microsoft.Reporting.WebForms.ServerReport Microsoft.Reporting.WebForms.ReportViewer::get_ServerReport()
0x140c8  callvirt instance string Microsoft.Reporting.WebForms.ServerReport::get_ReportPath()
0x140cd  call     instance string Microsoft.Reporting.WebForms.ReportViewer::GetSHA256Hash(string input)
0x140d2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x140d7  ret
0x140d8  ldarg.0
0x140d9  call     instance class Microsoft.Reporting.WebForms.LocalReport Microsoft.Reporting.WebForms.ReportViewer::get_LocalReport()
0x140de  callvirt instance string Microsoft.Reporting.WebForms.LocalReport::get_ReportPath()
0x140e3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x140e8  brtrue.s loc_14106
0x140ea  ldarg.1
0x140eb  ldstr    aHashedreportpa// "HashedReportPath"
0x140f0  ldarg.0
0x140f1  ldarg.0
0x140f2  call     instance class Microsoft.Reporting.WebForms.LocalReport Microsoft.Reporting.WebForms.ReportViewer::get_LocalReport()
0x140f7  callvirt instance string Microsoft.Reporting.WebForms.LocalReport::get_ReportPath()
0x140fc  call     instance string Microsoft.Reporting.WebForms.ReportViewer::GetSHA256Hash(string input)
0x14101  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x14106  ret
```
