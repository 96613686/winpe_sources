# Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::CreateRdlTextBox

- ea: `0x860`
- end: `0x939`
- name: `Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::CreateRdlTextBox`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x840`

## callees

- `0x550`
- `0x860`

## pseudocode

```c

```

## disassembly

```asm
0x860  ldsfld   string[] Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::AllowedAggregateFunctions
0x865  ldarg.1
0x866  call     T0x2B000004
0x86b  brtrue.s loc_87D
0x86d  ldstr    aInvalidAggrega// "Invalid aggregation specified"
0x872  ldstr    aAggregation// "aggregation"
0x877  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x87c  throw
0x87d  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Textbox::.ctor()
0x882  stloc.0
0x883  ldloc.0
0x884  ldstr    aTextbox// "TextBox_"
0x889  ldarg.0
0x88a  callvirt instance string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field::get_Name()
0x88f  call     string [mscorlib]System.String::Concat(string, string)
0x894  call     string Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetRandomizedItemName(string itemName)
0x899  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem::set_Name(string)
0x89e  ldloc.0
0x89f  ldc.i4.2
0x8a0  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Textbox::set_DataElementStyle(valuetype [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataElementStyles)
0x8a5  ldloc.0
0x8a6  ldc.i4.1
0x8a7  newarr   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.CustomProperty
0x8ac  dup
0x8ad  ldc.i4.0
0x8ae  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.CustomProperty::.ctor()
0x8b3  dup
0x8b4  ldstr    aOriginalfieldn// "OriginalFieldName"
0x8b9  call     valuetype [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression::op_Implicit(string)
0x8be  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.CustomProperty::set_Name(valuetype [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression)
0x8c3  dup
0x8c4  ldarg.0
0x8c5  callvirt instance string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field::get_Name()
0x8ca  call     valuetype [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression::op_Implicit(string)
0x8cf  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.CustomProperty::set_Value(valuetype [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression)
0x8d4  stelem.ref
0x8d5  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem::set_CustomProperties(class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.CustomProperty>)
0x8da  ldloc.0
0x8db  ldc.i4.1
0x8dc  newarr   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Paragraph
0x8e1  dup
0x8e2  ldc.i4.0
0x8e3  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Paragraph::.ctor()
0x8e8  stloc.1
0x8e9  ldloc.1
0x8ea  ldc.i4.1
0x8eb  newarr   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TextRun
0x8f0  dup
0x8f1  ldc.i4.0
0x8f2  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TextRun::.ctor()
0x8f7  dup
0x8f8  ldloca.s 2
0x8fa  initobj  [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression
0x900  ldloca.s 2
0x902  ldstr    a0Fields1Value// "={0}(Fields!{1}.Value)"
0x907  ldarg.1
0x908  ldarg.0
0x909  callvirt instance string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field::get_Name()
0x90e  call     string [mscorlib]System.String::Format(string, object, object)
0x913  call     instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression::set_Value(string)
0x918  ldloc.2
0x919  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TextRun::set_Value(valuetype [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression)
0x91e  stelem.ref
0x91f  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Paragraph::set_TextRuns(class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TextRun>)
0x924  ldloc.1
0x925  stelem.ref
0x926  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Textbox::set_Paragraphs(class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Paragraph>)
0x92b  ldloc.0
0x92c  ldarg.0
0x92d  callvirt instance string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field::get_Name()
0x932  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Textbox::set_DefaultName(string)
0x937  ldloc.0
0x938  ret
```
