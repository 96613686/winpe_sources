# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadRSDDataSetParameter

- ea: `0xb5f10`
- end: `0xb60f1`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadRSDDataSetParameter`
- size: `481`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callers

- `0xa9f50`

## callees

- `0x9f780`
- `0xadae0`
- `0xb5f10`
- `0xbb940`
- `0xbcdc0`
- `0xbcdd0`
- `0xbcde0`
- `0xbcdf0`
- `0x116d10`
- `0x116d20`
- `0x116d30`
- `0x116d40`
- `0x116d60`
- `0x117010`
- `0x1179c0`
- `0x13cb30`
- `0x13cb40`
- `0x13cb50`
- `0x13cb60`
- `0x13cb70`
- `0x13cb80`
- `0x13cbd0`
- `0x1767c0`

## string_xrefs

- `0xb5fc2`: `ReadOnly`
- `0xb6028`: `ReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0xb5f10  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0xb5f15  ldc.i4.s 0x26
0xb5f17  ldarga.s 1
0xb5f19  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xb5f1e  ceq
0xb5f20  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool)
0xb5f25  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.DataSetParameterValue::.ctor()
0xb5f2a  stloc.0
0xb5f2b  ldloc.0
0xb5f2c  ldarg.0
0xb5f2d  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb5f32  ldstr    aUniquename// "UniqueName"
0xb5f37  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0xb5f3c  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue::set_UniqueName(string value)
0xb5f41  ldloc.0
0xb5f42  ldarg.0
0xb5f43  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb5f48  ldstr    aName_1// "Name"
0xb5f4d  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0xb5f52  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue::set_Name(string value)
0xb5f57  ldarga.s 1
0xb5f59  ldc.i4.s 0x17
0xb5f5b  call     instance void Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::set_ObjectType(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType value)
0xb5f60  ldarga.s 1
0xb5f62  ldloc.0
0xb5f63  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue::get_Name()
0xb5f68  call     instance void Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::set_ObjectName(string value)
0xb5f6d  ldarg.0
0xb5f6e  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb5f73  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xb5f78  brtrue   loc_B60A4
0xb5f7d  ldc.i4.0
0xb5f7e  stloc.1
0xb5f7f  ldarg.0
0xb5f80  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb5f85  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xb5f8a  pop
0xb5f8b  ldarg.0
0xb5f8c  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb5f91  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xb5f96  stloc.2
0xb5f97  ldloc.2
0xb5f98  ldc.i4.1
0xb5f99  beq.s    loc_B5FA8
0xb5f9b  ldloc.2
0xb5f9c  ldc.i4.s 0xF
0xb5f9e  beq      loc_B6085
0xb5fa3  br       loc_B609E
0xb5fa8  ldarg.0
0xb5fa9  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb5fae  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xb5fb3  stloc.3
0xb5fb4  ldloc.3
0xb5fb5  ldstr    aDefaultvalue// "DefaultValue"
0xb5fba  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb5fbf  brtrue.s loc_B5FED
0xb5fc1  ldloc.3
0xb5fc2  ldstr    aReadonly// "ReadOnly"
0xb5fc7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb5fcc  brtrue.s loc_B6013
0xb5fce  ldloc.3
0xb5fcf  ldstr    aNullable// "Nullable"
0xb5fd4  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb5fd9  brtrue.s loc_B6039
0xb5fdb  ldloc.3
0xb5fdc  ldstr    aOmitfromquery// "OmitFromQuery"
0xb5fe1  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb5fe6  brtrue.s loc_B605F
0xb5fe8  br       loc_B609E
0xb5fed  ldloc.0
0xb5fee  ldarg.0
0xb5fef  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.DataType Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadDataTypeAttribute()
0xb5ff4  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue::set_ConstantDataType(valuetype Microsoft.ReportingServices.ReportProcessing.DataType value)
0xb5ff9  ldloc.0
0xb5ffa  ldarg.0
0xb5ffb  ldarg.1
0xb5ffc  ldloc.0
0xb5ffd  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.DataType Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue::get_ConstantDataType()
0xb6002  ldarg.2
0xb6003  ldarg.3
0xb6004  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadQueryOrParameterExpression(valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, valuetype Microsoft.ReportingServices.ReportProcessing.DataType dataType, bool& isComplex, class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> parametersInQuery)
0xb6009  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue::set_Value(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xb600e  br       loc_B609E
0xb6013  ldloc.0
0xb6014  ldarg.0
0xb6015  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb601a  ldarga.s 1
0xb601c  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xb6021  ldarga.s 1
0xb6023  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xb6028  ldstr    aReadonly// "ReadOnly"
0xb602d  callvirt instance bool Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::ReadBoolean(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName)
0xb6032  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.DataSetParameterValue::set_ReadOnly(bool value)
0xb6037  br.s     loc_B609E
0xb6039  ldloc.0
0xb603a  ldarg.0
0xb603b  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb6040  ldarga.s 1
0xb6042  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xb6047  ldarga.s 1
0xb6049  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xb604e  ldstr    aNullable// "Nullable"
0xb6053  callvirt instance bool Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::ReadBoolean(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName)
0xb6058  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.DataSetParameterValue::set_Nullable(bool value)
0xb605d  br.s     loc_B609E
0xb605f  ldloc.0
0xb6060  ldarg.0
0xb6061  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb6066  ldarga.s 1
0xb6068  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xb606d  ldarga.s 1
0xb606f  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xb6074  ldstr    aOmitfromquery// "OmitFromQuery"
0xb6079  callvirt instance bool Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::ReadBoolean(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName)
0xb607e  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.DataSetParameterValue::set_OmitFromQuery(bool value)
0xb6083  br.s     loc_B609E
0xb6085  ldstr    aDatasetparamet// "DataSetParameter"
0xb608a  ldarg.0
0xb608b  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb6090  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xb6095  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb609a  brfalse.s loc_B609E
0xb609c  ldc.i4.1
0xb609d  stloc.1
0xb609e  ldloc.1
0xb609f  brfalse  loc_B5F7F
0xb60a4  ldloc.0
0xb60a5  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.DataSetParameterValue::get_ReadOnly()
0xb60aa  brfalse.s loc_B60EF
0xb60ac  ldloc.0
0xb60ad  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.DataSetParameterValue::get_Nullable()
0xb60b2  brtrue.s loc_B60EF
0xb60b4  ldloc.0
0xb60b5  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue::get_Value()
0xb60ba  brfalse.s loc_B60C9
0xb60bc  ldloc.0
0xb60bd  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue::get_Value()
0xb60c2  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_OriginalText()
0xb60c7  brtrue.s loc_B60EF
0xb60c9  ldarg.0
0xb60ca  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_errorContext
0xb60cf  ldc.i4   0x1FD
0xb60d4  ldc.i4.0
0xb60d5  ldarga.s 1
0xb60d7  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xb60dc  ldarga.s 1
0xb60de  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xb60e3  ldnull
0xb60e4  call     T0x2B000001
0xb60e9  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0xb60ee  pop
0xb60ef  ldloc.0
0xb60f0  ret
```
