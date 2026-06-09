# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadDrillthrough

- ea: `0x9fcb0`
- end: `0x9fdff`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadDrillthrough`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x9fad0`

## callees

- `0x9fcb0`
- `0xac760`
- `0xae650`
- `0xb9e50`
- `0xbcdc0`
- `0xbcde0`
- `0xbce10`
- `0xbce20`
- `0xc01a0`
- `0xeedc0`
- `0xeedd0`
- `0xeedf0`
- `0xeee10`
- `0x117860`
- `0x117880`
- `0x117890`

## string_xrefs

- `0x9fd21`: `BookmarkLink`

## pseudocode

```c

```

## disassembly

```asm
0x9fcb0  ldarg.3
0x9fcb1  ldc.i4.0
0x9fcb2  stind.i1
0x9fcb3  ldc.i4.0
0x9fcb4  stloc.0
0x9fcb5  ldc.i4.0
0x9fcb6  stloc.1
0x9fcb7  ldc.i4.0
0x9fcb8  stloc.2
0x9fcb9  ldc.i4.0
0x9fcba  stloc.3
0x9fcbb  ldarga.s 1
0x9fcbd  ldstr    aActioninfoActi_0// "ActionInfo.Action.Drillthrough."
0x9fcc2  call     instance void Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::set_PrefixPropertyName(string value)
0x9fcc7  ldarg.0
0x9fcc8  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9fccd  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x9fcd2  pop
0x9fcd3  ldarg.0
0x9fcd4  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9fcd9  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x9fcde  stloc.s  4
0x9fce0  ldloc.s  4
0x9fce2  ldc.i4.1
0x9fce3  beq.s    loc_9FCF3
0x9fce5  ldloc.s  4
0x9fce7  ldc.i4.s 0xF
0x9fce9  beq      loc_9FDD8
0x9fcee  br       loc_9FDF1
0x9fcf3  ldarg.0
0x9fcf4  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9fcf9  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9fcfe  stloc.s  5
0x9fd00  ldloc.s  5
0x9fd02  ldstr    aReportname_0// "ReportName"
0x9fd07  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9fd0c  brtrue.s loc_9FD35
0x9fd0e  ldloc.s  5
0x9fd10  ldstr    aParameters// "Parameters"
0x9fd15  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9fd1a  brtrue   loc_9FDA5
0x9fd1f  ldloc.s  5
0x9fd21  ldstr    aBookmarklink// "BookmarkLink"
0x9fd26  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9fd2b  brtrue   loc_9FDB9
0x9fd30  br       loc_9FDF1
0x9fd35  ldarg.2
0x9fd36  ldarg.0
0x9fd37  ldarg.0
0x9fd38  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9fd3d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9fd42  ldc.i4.0
0x9fd43  ldc.i4.s 0x12
0x9fd45  ldarg.1
0x9fd46  ldloca.s 2
0x9fd48  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, [out] bool& computed)
0x9fd4d  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::set_DrillthroughReportName(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x9fd52  ldc.i4.3
0x9fd53  ldarg.2
0x9fd54  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::get_DrillthroughReportName()
0x9fd59  callvirt instance valuetype Types Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_Type()
0x9fd5e  bne.un   loc_9FDF1
0x9fd63  ldarg.2
0x9fd64  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::get_DrillthroughReportName()
0x9fd69  ldarg.0
0x9fd6a  ldfld    class Microsoft.ReportingServices.ReportPublishing.PublishingContextBase Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_publishingContext
0x9fd6f  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext Microsoft.ReportingServices.ReportPublishing.PublishingContextBase::get_CatalogContext()
0x9fd74  ldarg.2
0x9fd75  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::get_DrillthroughReportName()
0x9fd7a  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_StringValue()
0x9fd7f  ldarga.s 1
0x9fd81  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0x9fd86  ldarga.s 1
0x9fd88  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0x9fd8d  ldstr    aDrillthroughre// "DrillthroughReportName"
0x9fd92  ldarga.s 1
0x9fd94  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0x9fd99  call     string Microsoft.ReportingServices.ReportPublishing.PublishingValidator::ValidateReportName(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext reportContext, string reportName, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0x9fd9e  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::set_StringValue(string value)
0x9fda3  br.s     loc_9FDF1
0x9fda5  ldarg.2
0x9fda6  ldarg.0
0x9fda7  ldarg.1
0x9fda8  ldc.i4.1
0x9fda9  ldc.i4.0
0x9fdaa  ldc.i4.0
0x9fdab  ldloca.s 0
0x9fdad  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadParameters(valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, bool omitAllowed, bool doClsValidation, bool isSubreportParameter, [out] bool& computed)
0x9fdb2  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::set_DrillthroughParameters(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue> value)
0x9fdb7  br.s     loc_9FDF1
0x9fdb9  ldarg.2
0x9fdba  ldarg.0
0x9fdbb  ldarg.0
0x9fdbc  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9fdc1  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9fdc6  ldc.i4.0
0x9fdc7  ldc.i4.s 0x12
0x9fdc9  ldarg.1
0x9fdca  ldloca.s 1
0x9fdcc  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, [out] bool& computed)
0x9fdd1  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::set_DrillthroughBookmarkLink(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x9fdd6  br.s     loc_9FDF1
0x9fdd8  ldstr    aDrillthrough// "Drillthrough"
0x9fddd  ldarg.0
0x9fdde  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9fde3  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9fde8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9fded  brfalse.s loc_9FDF1
0x9fdef  ldc.i4.1
0x9fdf0  stloc.3
0x9fdf1  ldloc.3
0x9fdf2  brfalse  loc_9FCC7
0x9fdf7  ldarg.3
0x9fdf8  ldloc.0
0x9fdf9  ldloc.1
0x9fdfa  or
0x9fdfb  ldloc.2
0x9fdfc  or
0x9fdfd  stind.i1
0x9fdfe  ret
```
