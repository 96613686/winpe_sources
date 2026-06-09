# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::OnGaugeInputValueBegin

- ea: `0x1530`
- end: `0x15bf`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::OnGaugeInputValueBegin`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x11e0`
- `0x1530`
- `0x3370`
- `0x55f0`

## pseudocode

```c

```

## disassembly

```asm
0x1530  ldarg.0
0x1531  ldarg.1
0x1532  ldarg.2
0x1533  ldarg.3
0x1534  ldarg.s  4
0x1536  ldarg.s  5
0x1538  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnGaugeInputValueBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue gaugeInputValue, string defaultGaugeInputValueColName, bool output, object value, bool& walkThisGaugeInputValue)
0x153d  ldarg.s  5
0x153f  ldind.u1
0x1540  brfalse.s loc_15BE
0x1542  ldsfld   string [mscorlib]System.String::Empty
0x1547  stloc.0
0x1548  ldc.i4.s 0x12
0x154a  stloc.1
0x154b  ldarg.3
0x154c  brfalse.s loc_15B1
0x154e  ldarg.s  4
0x1550  brtrue.s loc_1598
0x1552  ldarg.1
0x1553  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CompiledGaugeInputValueInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue::get_CompiledInstance()
0x1558  brfalse.s loc_1576
0x155a  ldarg.1
0x155b  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CompiledGaugeInputValueInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue::get_CompiledInstance()
0x1560  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CompiledGaugeInputValueInstance::get_Value()
0x1565  brfalse.s loc_1576
0x1567  ldarg.1
0x1568  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CompiledGaugeInputValueInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue::get_CompiledInstance()
0x156d  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CompiledGaugeInputValueInstance::get_Value()
0x1572  starg.s  4
0x1574  br.s     loc_1598
0x1576  ldarg.1
0x1577  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValueInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue::get_Instance()
0x157c  brfalse.s loc_1598
0x157e  ldarg.1
0x157f  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValueInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue::get_Instance()
0x1584  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValueInstance::get_Value()
0x1589  brfalse.s loc_1598
0x158b  ldarg.1
0x158c  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValueInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue::get_Instance()
0x1591  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValueInstance::get_Value()
0x1596  starg.s  4
0x1598  ldarg.s  4
0x159a  brfalse.s loc_15B1
0x159c  ldarg.s  4
0x159e  call     string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::XmlConvertOrginalValue(object value)
0x15a3  stloc.0
0x15a4  ldarg.s  4
0x15a6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x15ab  call     valuetype [mscorlib]System.TypeCode [mscorlib]System.Type::GetTypeCode(class [mscorlib]System.Type)
0x15b0  stloc.1
0x15b1  ldarg.0
0x15b2  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0x15b7  ldloc.0
0x15b8  ldloc.1
0x15b9  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteValue(string value, valuetype [mscorlib]System.TypeCode typeCode)
0x15be  ret
```
