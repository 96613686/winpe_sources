# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::AddReportParametersToRowContent

- ea: `0x3430`
- end: `0x3517`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::AddReportParametersToRowContent`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xb7f0`

## callees

- `0x11e0`
- `0x3430`
- `0x3da0`

## pseudocode

```c

```

## disassembly

```asm
0x3430  ldarg.0
0x3431  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameterCollection Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_reportParamters
0x3436  brtrue.s loc_3439
0x3438  ret
0x3439  ldarg.0
0x343a  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameterCollection Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_reportParamters
0x343f  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameter>::get_Count()
0x3444  ldc.i4.1
0x3445  sub
0x3446  stloc.0
0x3447  br       loc_350F
0x344c  ldarg.0
0x344d  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameterCollection Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_reportParamters
0x3452  ldloc.0
0x3453  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameter>::get_Item(!!T0)
0x3458  stloc.1
0x3459  ldnull
0x345a  stloc.2
0x345b  ldnull
0x345c  stloc.3
0x345d  ldloc.1
0x345e  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameter::get_MultiValue()
0x3463  brfalse.s loc_34C6
0x3465  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x346a  stloc.s  4
0x346c  ldc.i4.0
0x346d  stloc.s  5
0x346f  br.s     loc_34A8
0x3471  ldloc.s  5
0x3473  brfalse.s loc_347F
0x3475  ldloc.s  4
0x3477  ldc.i4.s 0x2C
0x3479  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x347e  pop
0x347f  ldloc.1
0x3480  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameterInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameter::get_Instance()
0x3485  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<object> [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameterInstance::get_Values()
0x348a  ldloc.s  5
0x348c  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<object>::get_Item(!!T0)
0x3491  call     string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::XmlConvertOrginalValue(object value)
0x3496  stloc.s  6
0x3498  ldloc.s  4
0x349a  ldloc.s  6
0x349c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x34a1  pop
0x34a2  ldloc.s  5
0x34a4  ldc.i4.1
0x34a5  add
0x34a6  stloc.s  5
0x34a8  ldloc.s  5
0x34aa  ldloc.1
0x34ab  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameterInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameter::get_Instance()
0x34b0  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<object> [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameterInstance::get_Values()
0x34b5  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<object>::get_Count()
0x34ba  blt.s    loc_3471
0x34bc  ldloc.s  4
0x34be  callvirt instance string [mscorlib]System.Object::ToString()
0x34c3  stloc.3
0x34c4  br.s     loc_34F8
0x34c6  ldarg.0
0x34c7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_typeCodeToEdmMapping
0x34cc  ldloc.1
0x34cd  callvirt instance valuetype [mscorlib]System.TypeCode [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameter::get_DataType()
0x34d2  ldloca.s 2
0x34d4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string>::TryGetValue(var<u1>, !!T0)
0x34d9  pop
0x34da  ldloc.1
0x34db  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameterInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameter::get_Instance()
0x34e0  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameterInstance::get_Value()
0x34e5  brfalse.s loc_34F8
0x34e7  ldloc.1
0x34e8  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameterInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameter::get_Instance()
0x34ed  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameterInstance::get_Value()
0x34f2  call     string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::XmlConvertOrginalValue(object value)
0x34f7  stloc.3
0x34f8  ldarg.0
0x34f9  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_rowContent
0x34fe  ldloc.1
0x34ff  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameter::get_Name()
0x3504  ldloc.2
0x3505  ldloc.3
0x3506  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::AddBeginning(string columnName, string edmType, string value)
0x350b  ldloc.0
0x350c  ldc.i4.1
0x350d  sub
0x350e  stloc.0
0x350f  ldloc.0
0x3510  ldc.i4.0
0x3511  bge      loc_344C
0x3516  ret
```
