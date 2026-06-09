# Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::CreateRdlTextBox_0

- ea: `0x940`
- end: `0xa18`
- name: `Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::CreateRdlTextBox_0`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x820`

## callees

- `0x550`
- `0x940`

## pseudocode

```c

```

## disassembly

```asm
0x940  ldarg.2
0x941  brtrue.s loc_955
0x943  ldstr    aFields0Value// "=Fields!{0}.Value"
0x948  ldarg.0
0x949  callvirt instance string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field::get_Name()
0x94e  call     string [mscorlib]System.String::Format(string, object)
0x953  br.s     loc_965
0x955  ldstr    aIifIsnothingFi// "=iif(IsNothing(Fields!{0}(\"MEMBER_VALU"...
0x95a  ldarg.0
0x95b  callvirt instance string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field::get_Name()
0x960  call     string [mscorlib]System.String::Format(string, object)
0x965  stloc.0
0x966  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Textbox::.ctor()
0x96b  stloc.1
0x96c  ldloc.1
0x96d  ldstr    aTextbox0D41// "TextBox_{0:D4}_{1}"
0x972  ldarg.1
0x973  box      [mscorlib]System.Int32
0x978  ldarg.0
0x979  callvirt instance string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field::get_Name()
0x97e  call     string [mscorlib]System.String::Format(string, object, object)
0x983  call     string Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetRandomizedItemName(string itemName)
0x988  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem::set_Name(string)
0x98d  ldloc.1
0x98e  ldc.i4.2
0x98f  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Textbox::set_DataElementStyle(valuetype [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataElementStyles)
0x994  ldloc.1
0x995  ldc.i4.1
0x996  newarr   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.CustomProperty
0x99b  dup
0x99c  ldc.i4.0
0x99d  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.CustomProperty::.ctor()
0x9a2  dup
0x9a3  ldstr    aOriginalfieldn// "OriginalFieldName"
0x9a8  call     valuetype [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression::op_Implicit(string)
0x9ad  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.CustomProperty::set_Name(valuetype [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression)
0x9b2  dup
0x9b3  ldarg.0
0x9b4  callvirt instance string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field::get_Name()
0x9b9  call     valuetype [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression::op_Implicit(string)
0x9be  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.CustomProperty::set_Value(valuetype [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression)
0x9c3  stelem.ref
0x9c4  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem::set_CustomProperties(class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.CustomProperty>)
0x9c9  ldloc.1
0x9ca  ldc.i4.1
0x9cb  newarr   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Paragraph
0x9d0  dup
0x9d1  ldc.i4.0
0x9d2  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Paragraph::.ctor()
0x9d7  stloc.2
0x9d8  ldloc.2
0x9d9  ldc.i4.1
0x9da  newarr   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TextRun
0x9df  dup
0x9e0  ldc.i4.0
0x9e1  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TextRun::.ctor()
0x9e6  dup
0x9e7  ldloca.s 3
0x9e9  initobj  [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression
0x9ef  ldloca.s 3
0x9f1  ldloc.0
0x9f2  call     instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression::set_Value(string)
0x9f7  ldloc.3
0x9f8  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TextRun::set_Value(valuetype [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression)
0x9fd  stelem.ref
0x9fe  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Paragraph::set_TextRuns(class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TextRun>)
0xa03  ldloc.2
0xa04  stelem.ref
0xa05  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Textbox::set_Paragraphs(class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Paragraph>)
0xa0a  ldloc.1
0xa0b  ldarg.0
0xa0c  callvirt instance string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Field::get_Name()
0xa11  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Textbox::set_DefaultName(string)
0xa16  ldloc.1
0xa17  ret
```
