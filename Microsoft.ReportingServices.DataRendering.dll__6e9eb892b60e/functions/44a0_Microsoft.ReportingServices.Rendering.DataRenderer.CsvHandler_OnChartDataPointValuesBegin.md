# Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::OnChartDataPointValuesBegin

- ea: `0x44a0`
- end: `0x475a`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::OnChartDataPointValuesBegin`
- size: `698`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x44a0`
- `0x4f50`

## pseudocode

```c

```

## disassembly

```asm
0x44a0  ldarg.1
0x44a1  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Instance()
0x44a6  stloc.0
0x44a7  ldsfld   string [mscorlib]System.String::Empty
0x44ac  stloc.1
0x44ad  ldarg.1
0x44ae  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_X()
0x44b3  brfalse.s loc_44F9
0x44b5  ldarg.0
0x44b6  ldarg.0
0x44b7  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x44bc  ldc.i4.1
0x44bd  add
0x44be  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x44c3  ldarg.2
0x44c4  brfalse.s loc_44E7
0x44c6  ldloc.0
0x44c7  brfalse.s loc_44E7
0x44c9  ldloc.0
0x44ca  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_X()
0x44cf  brfalse.s loc_44E7
0x44d1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x44d6  ldstr    a0// "{0}"
0x44db  ldloc.0
0x44dc  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_X()
0x44e1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x44e6  stloc.1
0x44e7  ldarg.0
0x44e8  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_visitor
0x44ed  ldloc.1
0x44ee  ldarg.0
0x44ef  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_stackedMode
0x44f4  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::WriteValue(string unformattedValue, bool excelMode)
0x44f9  ldarg.1
0x44fa  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Y()
0x44ff  brfalse.s loc_4545
0x4501  ldarg.0
0x4502  ldarg.0
0x4503  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x4508  ldc.i4.1
0x4509  add
0x450a  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x450f  ldarg.2
0x4510  brfalse.s loc_4533
0x4512  ldloc.0
0x4513  brfalse.s loc_4533
0x4515  ldloc.0
0x4516  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Y()
0x451b  brfalse.s loc_4533
0x451d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4522  ldstr    a0// "{0}"
0x4527  ldloc.0
0x4528  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Y()
0x452d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x4532  stloc.1
0x4533  ldarg.0
0x4534  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_visitor
0x4539  ldloc.1
0x453a  ldarg.0
0x453b  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_stackedMode
0x4540  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::WriteValue(string unformattedValue, bool excelMode)
0x4545  ldarg.1
0x4546  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Size()
0x454b  brfalse.s loc_4591
0x454d  ldarg.0
0x454e  ldarg.0
0x454f  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x4554  ldc.i4.1
0x4555  add
0x4556  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x455b  ldarg.2
0x455c  brfalse.s loc_457F
0x455e  ldloc.0
0x455f  brfalse.s loc_457F
0x4561  ldloc.0
0x4562  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Size()
0x4567  brfalse.s loc_457F
0x4569  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x456e  ldstr    a0// "{0}"
0x4573  ldloc.0
0x4574  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Size()
0x4579  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x457e  stloc.1
0x457f  ldarg.0
0x4580  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_visitor
0x4585  ldloc.1
0x4586  ldarg.0
0x4587  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_stackedMode
0x458c  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::WriteValue(string unformattedValue, bool excelMode)
0x4591  ldarg.1
0x4592  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_High()
0x4597  brfalse.s loc_45DD
0x4599  ldarg.0
0x459a  ldarg.0
0x459b  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x45a0  ldc.i4.1
0x45a1  add
0x45a2  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x45a7  ldarg.2
0x45a8  brfalse.s loc_45CB
0x45aa  ldloc.0
0x45ab  brfalse.s loc_45CB
0x45ad  ldloc.0
0x45ae  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_High()
0x45b3  brfalse.s loc_45CB
0x45b5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x45ba  ldstr    a0// "{0}"
0x45bf  ldloc.0
0x45c0  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_High()
0x45c5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x45ca  stloc.1
0x45cb  ldarg.0
0x45cc  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_visitor
0x45d1  ldloc.1
0x45d2  ldarg.0
0x45d3  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_stackedMode
0x45d8  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::WriteValue(string unformattedValue, bool excelMode)
0x45dd  ldarg.1
0x45de  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Low()
0x45e3  brfalse.s loc_4629
0x45e5  ldarg.0
0x45e6  ldarg.0
0x45e7  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x45ec  ldc.i4.1
0x45ed  add
0x45ee  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x45f3  ldarg.2
0x45f4  brfalse.s loc_4617
0x45f6  ldloc.0
0x45f7  brfalse.s loc_4617
0x45f9  ldloc.0
0x45fa  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Low()
0x45ff  brfalse.s loc_4617
0x4601  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4606  ldstr    a0// "{0}"
0x460b  ldloc.0
0x460c  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Low()
0x4611  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x4616  stloc.1
0x4617  ldarg.0
0x4618  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_visitor
0x461d  ldloc.1
0x461e  ldarg.0
0x461f  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_stackedMode
0x4624  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::WriteValue(string unformattedValue, bool excelMode)
0x4629  ldarg.1
0x462a  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Start()
0x462f  brfalse.s loc_4675
0x4631  ldarg.0
0x4632  ldarg.0
0x4633  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x4638  ldc.i4.1
0x4639  add
0x463a  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x463f  ldarg.2
0x4640  brfalse.s loc_4663
0x4642  ldloc.0
0x4643  brfalse.s loc_4663
0x4645  ldloc.0
0x4646  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Start()
0x464b  brfalse.s loc_4663
0x464d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4652  ldstr    a0// "{0}"
0x4657  ldloc.0
0x4658  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Start()
0x465d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x4662  stloc.1
0x4663  ldarg.0
0x4664  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_visitor
0x4669  ldloc.1
0x466a  ldarg.0
0x466b  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_stackedMode
0x4670  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::WriteValue(string unformattedValue, bool excelMode)
0x4675  ldarg.1
0x4676  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_End()
0x467b  brfalse.s loc_46C1
0x467d  ldarg.0
0x467e  ldarg.0
0x467f  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x4684  ldc.i4.1
0x4685  add
0x4686  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x468b  ldarg.2
0x468c  brfalse.s loc_46AF
0x468e  ldloc.0
0x468f  brfalse.s loc_46AF
0x4691  ldloc.0
0x4692  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_End()
0x4697  brfalse.s loc_46AF
0x4699  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x469e  ldstr    a0// "{0}"
0x46a3  ldloc.0
0x46a4  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_End()
0x46a9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x46ae  stloc.1
0x46af  ldarg.0
0x46b0  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_visitor
0x46b5  ldloc.1
0x46b6  ldarg.0
0x46b7  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_stackedMode
0x46bc  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::WriteValue(string unformattedValue, bool excelMode)
0x46c1  ldarg.1
0x46c2  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Mean()
0x46c7  brfalse.s loc_470D
0x46c9  ldarg.0
0x46ca  ldarg.0
0x46cb  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x46d0  ldc.i4.1
0x46d1  add
0x46d2  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x46d7  ldarg.2
0x46d8  brfalse.s loc_46FB
0x46da  ldloc.0
0x46db  brfalse.s loc_46FB
0x46dd  ldloc.0
0x46de  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Mean()
0x46e3  brfalse.s loc_46FB
0x46e5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x46ea  ldstr    a0// "{0}"
0x46ef  ldloc.0
0x46f0  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Mean()
0x46f5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x46fa  stloc.1
0x46fb  ldarg.0
0x46fc  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_visitor
0x4701  ldloc.1
0x4702  ldarg.0
0x4703  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_stackedMode
0x4708  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::WriteValue(string unformattedValue, bool excelMode)
0x470d  ldarg.1
0x470e  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Median()
0x4713  brfalse.s loc_4759
0x4715  ldarg.0
0x4716  ldarg.0
0x4717  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x471c  ldc.i4.1
0x471d  add
0x471e  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x4723  ldarg.2
0x4724  brfalse.s loc_4747
0x4726  ldloc.0
0x4727  brfalse.s loc_4747
0x4729  ldloc.0
0x472a  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Median()
0x472f  brfalse.s loc_4747
0x4731  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4736  ldstr    a0// "{0}"
0x473b  ldloc.0
0x473c  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Median()
0x4741  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x4746  stloc.1
0x4747  ldarg.0
0x4748  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_visitor
0x474d  ldloc.1
0x474e  ldarg.0
0x474f  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_stackedMode
0x4754  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::WriteValue(string unformattedValue, bool excelMode)
0x4759  ret
```
