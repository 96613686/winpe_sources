# Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadDrillthrough

- ea: `0x1c2cf0`
- end: `0x1c2e27`
- name: `Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadDrillthrough`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x1c2b20`

## callees

- `0x19a5e0`
- `0x19a5f0`
- `0x19a610`
- `0x19a630`
- `0x1a7470`
- `0x1a74a0`
- `0x1a74b0`
- `0x1b7c40`
- `0x1c2cf0`
- `0x1c32a0`
- `0x1cc910`
- `0x2643c0`
- `0x2643e0`

## string_xrefs

- `0x1c2d52`: `BookmarkLink`

## pseudocode

```c

```

## disassembly

```asm
0x1c2cf0  ldarg.3
0x1c2cf1  ldc.i4.0
0x1c2cf2  stind.i1
0x1c2cf3  ldc.i4.0
0x1c2cf4  stloc.0
0x1c2cf5  ldc.i4.0
0x1c2cf6  stloc.1
0x1c2cf7  ldc.i4.0
0x1c2cf8  stloc.2
0x1c2cf9  ldc.i4.0
0x1c2cfa  stloc.3
0x1c2cfb  ldarg.0
0x1c2cfc  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1c2d01  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1c2d06  pop
0x1c2d07  ldarg.0
0x1c2d08  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1c2d0d  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1c2d12  stloc.s  4
0x1c2d14  ldloc.s  4
0x1c2d16  ldc.i4.1
0x1c2d17  beq.s    loc_1C2D27
0x1c2d19  ldloc.s  4
0x1c2d1b  ldc.i4.s 0xF
0x1c2d1d  beq      loc_1C2E00
0x1c2d22  br       loc_1C2E19
0x1c2d27  ldarg.0
0x1c2d28  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1c2d2d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1c2d32  stloc.s  5
0x1c2d34  ldloc.s  5
0x1c2d36  ldstr    aReportname_0// "ReportName"
0x1c2d3b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c2d40  brtrue.s loc_1C2D66
0x1c2d42  ldloc.s  5
0x1c2d44  ldstr    aParameters// "Parameters"
0x1c2d49  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c2d4e  brtrue.s loc_1C2DCF
0x1c2d50  ldloc.s  5
0x1c2d52  ldstr    aBookmarklink// "BookmarkLink"
0x1c2d57  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c2d5c  brtrue   loc_1C2DE2
0x1c2d61  br       loc_1C2E19
0x1c2d66  ldarg.2
0x1c2d67  ldarg.0
0x1c2d68  ldarg.0
0x1c2d69  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1c2d6e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1c2d73  ldc.i4.0
0x1c2d74  ldc.i4.0
0x1c2d75  ldarg.1
0x1c2d76  ldloca.s 2
0x1c2d78  call     instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype ConstantType constantType, valuetype PublishingContextStruct context, [out] bool& computed)
0x1c2d7d  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ActionItem::set_DrillthroughReportName(class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo value)
0x1c2d82  ldc.i4.3
0x1c2d83  ldarg.2
0x1c2d84  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ActionItem::get_DrillthroughReportName()
0x1c2d89  callvirt instance valuetype Types Microsoft.ReportingServices.ReportProcessing.ExpressionInfo::get_Type()
0x1c2d8e  bne.un   loc_1C2E19
0x1c2d93  ldarg.2
0x1c2d94  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ActionItem::get_DrillthroughReportName()
0x1c2d99  ldarg.0
0x1c2d9a  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reportContext
0x1c2d9f  ldarg.2
0x1c2da0  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ActionItem::get_DrillthroughReportName()
0x1c2da5  callvirt instance string Microsoft.ReportingServices.ReportProcessing.ExpressionInfo::get_Value()
0x1c2daa  ldarga.s 1
0x1c2dac  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType PublishingContextStruct::get_ObjectType()
0x1c2db1  ldarga.s 1
0x1c2db3  call     instance string PublishingContextStruct::get_ObjectName()
0x1c2db8  ldstr    aDrillthroughre// "DrillthroughReportName"
0x1c2dbd  ldarg.0
0x1c2dbe  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_errorContext
0x1c2dc3  call     string Microsoft.ReportingServices.ReportProcessing.PublishingValidator::ValidateReportName(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext reportContext, string reportName, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0x1c2dc8  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ExpressionInfo::set_Value(string value)
0x1c2dcd  br.s     loc_1C2E19
0x1c2dcf  ldarg.2
0x1c2dd0  ldarg.0
0x1c2dd1  ldarg.1
0x1c2dd2  ldc.i4.1
0x1c2dd3  ldc.i4.0
0x1c2dd4  ldloca.s 0
0x1c2dd6  call     instance class Microsoft.ReportingServices.ReportProcessing.ParameterValueList Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadParameters(valuetype PublishingContextStruct context, bool omitAllowed, bool doClsValidation, [out] bool& computed)
0x1c2ddb  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ActionItem::set_DrillthroughParameters(class Microsoft.ReportingServices.ReportProcessing.ParameterValueList value)
0x1c2de0  br.s     loc_1C2E19
0x1c2de2  ldarg.2
0x1c2de3  ldarg.0
0x1c2de4  ldarg.0
0x1c2de5  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1c2dea  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1c2def  ldc.i4.0
0x1c2df0  ldc.i4.0
0x1c2df1  ldarg.1
0x1c2df2  ldloca.s 1
0x1c2df4  call     instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype ConstantType constantType, valuetype PublishingContextStruct context, [out] bool& computed)
0x1c2df9  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ActionItem::set_DrillthroughBookmarkLink(class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo value)
0x1c2dfe  br.s     loc_1C2E19
0x1c2e00  ldstr    aDrillthrough// "Drillthrough"
0x1c2e05  ldarg.0
0x1c2e06  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1c2e0b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1c2e10  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c2e15  brfalse.s loc_1C2E19
0x1c2e17  ldc.i4.1
0x1c2e18  stloc.3
0x1c2e19  ldloc.3
0x1c2e1a  brfalse  loc_1C2CFB
0x1c2e1f  ldarg.3
0x1c2e20  ldloc.0
0x1c2e21  ldloc.1
0x1c2e22  or
0x1c2e23  ldloc.2
0x1c2e24  or
0x1c2e25  stind.i1
0x1c2e26  ret
```
