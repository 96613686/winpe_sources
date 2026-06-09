# Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::OnGaugeInputValueBegin

- ea: `0x47f0`
- end: `0x488f`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::OnGaugeInputValueBegin`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x47f0`
- `0x4f50`
- `0x55f0`

## pseudocode

```c

```

## disassembly

```asm
0x47f0  ldarg.0
0x47f1  ldarg.1
0x47f2  ldarg.2
0x47f3  ldarg.3
0x47f4  ldarg.s  4
0x47f6  ldarg.s  5
0x47f8  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnGaugeInputValueBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue gaugeInputValue, string defaultGaugeInputValueColName, bool output, object value, bool& walkThisGaugeInputValue)
0x47fd  ldarg.s  5
0x47ff  ldind.u1
0x4800  brfalse  loc_488E
0x4805  ldarg.0
0x4806  ldarg.0
0x4807  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x480c  ldc.i4.1
0x480d  add
0x480e  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_currentColumn
0x4813  ldsfld   string [mscorlib]System.String::Empty
0x4818  stloc.0
0x4819  ldarg.3
0x481a  brfalse.s loc_487C
0x481c  ldarg.s  4
0x481e  brtrue.s loc_4866
0x4820  ldarg.1
0x4821  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CompiledGaugeInputValueInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue::get_CompiledInstance()
0x4826  brfalse.s loc_4844
0x4828  ldarg.1
0x4829  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CompiledGaugeInputValueInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue::get_CompiledInstance()
0x482e  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CompiledGaugeInputValueInstance::get_Value()
0x4833  brfalse.s loc_4844
0x4835  ldarg.1
0x4836  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CompiledGaugeInputValueInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue::get_CompiledInstance()
0x483b  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CompiledGaugeInputValueInstance::get_Value()
0x4840  starg.s  4
0x4842  br.s     loc_4866
0x4844  ldarg.1
0x4845  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValueInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue::get_Instance()
0x484a  brfalse.s loc_4866
0x484c  ldarg.1
0x484d  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValueInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue::get_Instance()
0x4852  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValueInstance::get_Value()
0x4857  brfalse.s loc_4866
0x4859  ldarg.1
0x485a  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValueInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue::get_Instance()
0x485f  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValueInstance::get_Value()
0x4864  starg.s  4
0x4866  ldarg.s  4
0x4868  brfalse.s loc_487C
0x486a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x486f  ldstr    a0// "{0}"
0x4874  ldarg.s  4
0x4876  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x487b  stloc.0
0x487c  ldarg.0
0x487d  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_visitor
0x4882  ldloc.0
0x4883  ldarg.0
0x4884  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::m_stackedMode
0x4889  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::WriteValue(string unformattedValue, bool excelMode)
0x488e  ret
```
