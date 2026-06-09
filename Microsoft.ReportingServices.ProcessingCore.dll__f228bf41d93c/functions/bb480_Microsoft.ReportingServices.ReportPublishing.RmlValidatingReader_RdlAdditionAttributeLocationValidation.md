# Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::RdlAdditionAttributeLocationValidation

- ea: `0xbb480`
- end: `0xbb7e6`
- name: `Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::RdlAdditionAttributeLocationValidation`
- size: `870`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xba8b0`

## callees

- `0xbb1b0`
- `0xbb480`
- `0xbb860`
- `0xbbbd0`
- `0xbbbf0`
- `0xbc230`
- `0x175d50`
- `0x176790`
- `0x1767c0`

## string_xrefs

- `0xbb4bb`: `http://schemas.microsoft.com/sqlserver/reporting/2016/01/reportdefinition`
- `0xbb5fe`: `xmlns`

## pseudocode

```c

```

## disassembly

```asm
0xbb480  ldarg.1
0xbb481  ldnull
0xbb482  stind.ref
0xbb483  ldnull
0xbb484  stloc.0
0xbb485  ldarg.0
0xbb486  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xbb48b  ldc.i4.1
0xbb48c  bne.un   loc_BB7E0
0xbb491  ldarg.0
0xbb492  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_HasAttributes()
0xbb497  brfalse  loc_BB7E0
0xbb49c  ldarg.0
0xbb49d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xbb4a2  ldarg.0
0xbb4a3  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xbb4a8  call     string Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::GetExpandedName(string localName, string namespaceURI)
0xbb4ad  stloc.1
0xbb4ae  ldarg.0
0xbb4af  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xbb4b4  stloc.2
0xbb4b5  ldloc.1
0xbb4b6  ldstr    aReport// "Report"
0xbb4bb  ldstr    aHttpSchemasMic_7// "http://schemas.microsoft.com/sqlserver/"...
0xbb4c0  call     string Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::GetExpandedName(string localName, string namespaceURI)
0xbb4c5  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0xbb4ca  brtrue   loc_BB6B8
0xbb4cf  ldarg.0
0xbb4d0  ldstr    aMustunderstand// "MustUnderstand"
0xbb4d5  call     instance string Microsoft.ReportingServices.ReportPublishing.RDLValidatingReader::GetAttributeLocalName(string name)
0xbb4da  brfalse  loc_BB6B8
0xbb4df  ldarg.0
0xbb4e0  ldstr    aMustunderstand// "MustUnderstand"
0xbb4e5  call     instance string Microsoft.ReportingServices.ReportPublishing.RDLValidatingReader::GetAttributeLocalName(string name)
0xbb4ea  call     T0x2B000017
0xbb4ef  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xbb4f4  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0xbb4f9  stloc.0
0xbb4fa  br       loc_BB6B8
0xbb4ff  ldarg.0
0xbb500  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xbb505  stloc.3
0xbb506  ldloc.3
0xbb507  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbb50c  brfalse.s loc_BB510
0xbb50e  ldloc.2
0xbb50f  stloc.3
0xbb510  ldarg.0
0xbb511  ldloc.3
0xbb512  call     instance bool Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::IsMicroVersionedAttributeNamespace(string namespaceUri)
0xbb517  brfalse  loc_BB5F2
0xbb51c  ldarg.0
0xbb51d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xbb522  ldloc.3
0xbb523  call     string Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::GetExpandedName(string localName, string namespaceURI)
0xbb528  stloc.s  4
0xbb52a  ldarg.0
0xbb52b  ldfld    valuetype ItemType Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::m_itemType
0xbb530  brfalse.s loc_BB53B
0xbb532  ldarg.0
0xbb533  ldfld    valuetype ItemType Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::m_itemType
0xbb538  ldc.i4.2
0xbb539  bne.un.s loc_BB579
0xbb53b  ldarg.1
0xbb53c  ldloc.s  4
0xbb53e  ldloc.3
0xbb53f  ldarg.0
0xbb540  call     instance int32 Microsoft.ReportingServices.ReportPublishing.RDLValidatingReader::get_LineNumber()
0xbb545  stloc.s  5
0xbb547  ldloca.s 5
0xbb549  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb54e  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0xbb553  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb558  ldarg.0
0xbb559  call     instance int32 Microsoft.ReportingServices.ReportPublishing.RDLValidatingReader::get_LinePosition()
0xbb55e  stloc.s  5
0xbb560  ldloca.s 5
0xbb562  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb567  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0xbb56c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb571  call     string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.RDLValidatingReaderStringsWrapper::rdlValidationInvalidNamespaceAttribute(string, string, string, string)
0xbb576  stind.ref
0xbb577  br.s     loc_BB5F2
0xbb579  ldarg.0
0xbb57a  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::m_microversioningValidationStructureAttributes
0xbb57f  ldloc.s  4
0xbb581  callvirt instance string[] [System]System.Collections.Specialized.NameValueCollection::GetValues(string)
0xbb586  stloc.s  6
0xbb588  ldloc.s  6
0xbb58a  brfalse.s loc_BB5B6
0xbb58c  ldc.i4.0
0xbb58d  stloc.s  7
0xbb58f  br.s     loc_BB5AE
0xbb591  ldloc.s  6
0xbb593  ldloc.s  7
0xbb595  ldelem.ref
0xbb596  ldloc.1
0xbb597  ldc.i4.4
0xbb598  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xbb59d  brfalse.s loc_BB5A8
0xbb59f  ldarg.0
0xbb5a0  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0xbb5a5  pop
0xbb5a6  ldc.i4.1
0xbb5a7  ret
0xbb5a8  ldloc.s  7
0xbb5aa  ldc.i4.1
0xbb5ab  add
0xbb5ac  stloc.s  7
0xbb5ae  ldloc.s  7
0xbb5b0  ldloc.s  6
0xbb5b2  ldlen
0xbb5b3  conv.i4
0xbb5b4  blt.s    loc_BB591
0xbb5b6  ldarg.1
0xbb5b7  ldloc.s  4
0xbb5b9  ldloc.1
0xbb5ba  ldarg.0
0xbb5bb  call     instance int32 Microsoft.ReportingServices.ReportPublishing.RDLValidatingReader::get_LineNumber()
0xbb5c0  stloc.s  5
0xbb5c2  ldloca.s 5
0xbb5c4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb5c9  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0xbb5ce  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb5d3  ldarg.0
0xbb5d4  call     instance int32 Microsoft.ReportingServices.ReportPublishing.RDLValidatingReader::get_LinePosition()
0xbb5d9  stloc.s  5
0xbb5db  ldloca.s 5
0xbb5dd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb5e2  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0xbb5e7  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb5ec  call     string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.RDLValidatingReaderStringsWrapper::rdlValidationInvalidMicroVersionedAttribute(string, string, string, string)
0xbb5f1  stind.ref
0xbb5f2  ldloc.0
0xbb5f3  brfalse  loc_BB6B8
0xbb5f8  ldarg.0
0xbb5f9  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Prefix()
0xbb5fe  ldstr    aXmlns// "xmlns"
0xbb603  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbb608  brfalse  loc_BB6B8
0xbb60d  ldloc.0
0xbb60e  ldarg.0
0xbb60f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xbb614  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0xbb619  brfalse  loc_BB6B8
0xbb61e  ldloc.0
0xbb61f  ldarg.0
0xbb620  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xbb625  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Remove(var<u1>)
0xbb62a  pop
0xbb62b  ldarg.0
0xbb62c  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::m_serverSupportedSchemas
0xbb631  ldarg.0
0xbb632  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0xbb637  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0xbb63c  brtrue.s loc_BB6B8
0xbb63e  ldarg.1
0xbb63f  ldarg.0
0xbb640  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0xbb645  ldarg.0
0xbb646  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xbb64b  ldarg.0
0xbb64c  call     instance int32 Microsoft.ReportingServices.ReportPublishing.RDLValidatingReader::get_LineNumber()
0xbb651  stloc.s  5
0xbb653  ldloca.s 5
0xbb655  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb65a  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0xbb65f  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb664  ldarg.0
0xbb665  call     instance int32 Microsoft.ReportingServices.ReportPublishing.RDLValidatingReader::get_LinePosition()
0xbb66a  stloc.s  5
0xbb66c  ldloca.s 5
0xbb66e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb673  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0xbb678  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb67d  call     string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.RDLValidatingReaderStringsWrapper::rdlValidationUnsupportedSchema(string, string, string, string)
0xbb682  stind.ref
0xbb683  ldarg.0
0xbb684  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::m_errorContext
0xbb689  ldc.i4   0x25F
0xbb68e  ldc.i4.0
0xbb68f  ldc.i4.0
0xbb690  ldnull
0xbb691  ldstr    aMustunderstand// "MustUnderstand"
0xbb696  ldc.i4.1
0xbb697  newarr   [mscorlib]System.String
0xbb69c  dup
0xbb69d  ldc.i4.0
0xbb69e  ldarg.1
0xbb69f  ldind.ref
0xbb6a0  stelem.ref
0xbb6a1  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0xbb6a6  pop
0xbb6a7  ldarg.0
0xbb6a8  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::m_errorContext
0xbb6ad  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessageList Microsoft.ReportingServices.ReportProcessing.ErrorContext::get_Messages()
0xbb6b2  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(class Microsoft.ReportingServices.ReportProcessing.ProcessingMessageList processingMessages)
0xbb6b7  throw
0xbb6b8  ldarg.0
0xbb6b9  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0xbb6be  brtrue   loc_BB4FF
0xbb6c3  ldloc.0
0xbb6c4  brfalse  loc_BB7D9
0xbb6c9  ldloc.0
0xbb6ca  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<string>::get_Count()
0xbb6cf  brfalse  loc_BB7D9
0xbb6d4  ldloc.0
0xbb6d5  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<string>::get_Count()
0xbb6da  ldc.i4.1
0xbb6db  bne.un.s loc_BB756
0xbb6dd  ldarg.1
0xbb6de  ldloc.0
0xbb6df  call     T0x2B000018
0xbb6e4  ldstr    aMustunderstand// "MustUnderstand"
0xbb6e9  ldarg.0
0xbb6ea  call     instance int32 Microsoft.ReportingServices.ReportPublishing.RDLValidatingReader::get_LineNumber()
0xbb6ef  stloc.s  5
0xbb6f1  ldloca.s 5
0xbb6f3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb6f8  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0xbb6fd  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb702  ldarg.0
0xbb703  call     instance int32 Microsoft.ReportingServices.ReportPublishing.RDLValidatingReader::get_LinePosition()
0xbb708  stloc.s  5
0xbb70a  ldloca.s 5
0xbb70c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb711  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0xbb716  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb71b  call     string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.RDLValidatingReaderStringsWrapper::rdlValidationUndefinedSchemaNamespace(string, string, string, string)
0xbb720  stind.ref
0xbb721  ldarg.0
0xbb722  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::m_errorContext
0xbb727  ldc.i4   0x25F
0xbb72c  ldc.i4.0
0xbb72d  ldc.i4.0
0xbb72e  ldnull
0xbb72f  ldstr    aMustunderstand// "MustUnderstand"
0xbb734  ldc.i4.1
0xbb735  newarr   [mscorlib]System.String
0xbb73a  dup
0xbb73b  ldc.i4.0
0xbb73c  ldarg.1
0xbb73d  ldind.ref
0xbb73e  stelem.ref
0xbb73f  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0xbb744  pop
0xbb745  ldarg.0
0xbb746  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::m_errorContext
0xbb74b  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessageList Microsoft.ReportingServices.ReportProcessing.ErrorContext::get_Messages()
0xbb750  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(class Microsoft.ReportingServices.ReportProcessing.ProcessingMessageList processingMessages)
0xbb755  throw
0xbb756  ldarg.1
0xbb757  ldstr    asc_27A9DE// ", "
0xbb75c  ldloc.0
0xbb75d  call     T0x2B000019
0xbb762  call     string [mscorlib]System.String::Join(string, string[])
0xbb767  ldstr    aMustunderstand// "MustUnderstand"
0xbb76c  ldarg.0
0xbb76d  call     instance int32 Microsoft.ReportingServices.ReportPublishing.RDLValidatingReader::get_LineNumber()
0xbb772  stloc.s  5
0xbb774  ldloca.s 5
0xbb776  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb77b  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0xbb780  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb785  ldarg.0
0xbb786  call     instance int32 Microsoft.ReportingServices.ReportPublishing.RDLValidatingReader::get_LinePosition()
0xbb78b  stloc.s  5
0xbb78d  ldloca.s 5
0xbb78f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb794  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0xbb799  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb79e  call     string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.RDLValidatingReaderStringsWrapper::rdlValidationMultipleUndefinedSchemaNamespaces(string, string, string, string)
0xbb7a3  stind.ref
0xbb7a4  ldarg.0
0xbb7a5  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::m_errorContext
0xbb7aa  ldc.i4   0x25F
0xbb7af  ldc.i4.0
0xbb7b0  ldc.i4.0
0xbb7b1  ldnull
0xbb7b2  ldstr    aMustunderstand// "MustUnderstand"
0xbb7b7  ldc.i4.1
0xbb7b8  newarr   [mscorlib]System.String
0xbb7bd  dup
0xbb7be  ldc.i4.0
0xbb7bf  ldarg.1
0xbb7c0  ldind.ref
0xbb7c1  stelem.ref
0xbb7c2  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0xbb7c7  pop
0xbb7c8  ldarg.0
0xbb7c9  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::m_errorContext
0xbb7ce  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessageList Microsoft.ReportingServices.ReportProcessing.ErrorContext::get_Messages()
0xbb7d3  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(class Microsoft.ReportingServices.ReportProcessing.ProcessingMessageList processingMessages)
0xbb7d8  throw
0xbb7d9  ldarg.0
0xbb7da  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0xbb7df  pop
0xbb7e0  ldarg.1
0xbb7e1  ldind.ref
0xbb7e2  ldnull
  ... truncated ...
```
