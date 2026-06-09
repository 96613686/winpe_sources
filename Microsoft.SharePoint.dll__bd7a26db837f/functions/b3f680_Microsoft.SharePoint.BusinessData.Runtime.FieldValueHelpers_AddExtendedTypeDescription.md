# Microsoft.SharePoint.BusinessData.Runtime.FieldValueHelpers::AddExtendedTypeDescription

- ea: `0xb3f680`
- end: `0xb3f937`
- name: `Microsoft.SharePoint.BusinessData.Runtime.FieldValueHelpers::AddExtendedTypeDescription`
- size: `695`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xb3f4a0`

## callees

- `0xb3f680`

## string_xrefs

- `0xb3f698`: `http://www.w3.org/2001/XMLSchema`
- `0xb3f6a8`: `http://www.w3.org/2001/XMLSchema`
- `0xb3f6c8`: `http://www.w3.org/2001/XMLSchema`
- `0xb3f710`: `http://www.w3.org/2001/XMLSchema`
- `0xb3f720`: `http://www.w3.org/2001/XMLSchema`
- `0xb3f764`: `http://www.w3.org/2001/XMLSchema`
- `0xb3f7c3`: `http://www.w3.org/2001/XMLSchema`
- `0xb3f7d3`: `http://www.w3.org/2001/XMLSchema`
- `0xb3f806`: `http://www.w3.org/2001/XMLSchema`
- `0xb3f843`: `http://www.w3.org/2001/XMLSchema`
- `0xb3f853`: `http://www.w3.org/2001/XMLSchema`
- `0xb3f877`: `http://www.w3.org/2001/XMLSchema`
- `0xb3f8ca`: `http://www.w3.org/2001/XMLSchema`
- `0xb3f8da`: `http://www.w3.org/2001/XMLSchema`
- `0xb3f8ea`: `http://www.w3.org/2001/XMLSchema`
- `0xb3f83e`: `complexType`
- `0xb3f8c5`: `complexType`

## pseudocode

```c

```

## disassembly

```asm
0xb3f680  ldarg.0
0xb3f681  ldtoken  [mscorlib]System.Guid
0xb3f686  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb3f68b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xb3f690  brfalse.s loc_B3F6F5
0xb3f692  ldarg.1
0xb3f693  ldstr    aSimpletype// "simpleType"
0xb3f698  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0xb3f69d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb3f6a2  ldarg.1
0xb3f6a3  ldstr    aRestriction_0// "restriction"
0xb3f6a8  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0xb3f6ad  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb3f6b2  ldarg.1
0xb3f6b3  ldstr    aBase// "base"
0xb3f6b8  ldstr    aXsString// "xs:string"
0xb3f6bd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xb3f6c2  ldarg.1
0xb3f6c3  ldstr    aPattern_0// "pattern"
0xb3f6c8  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0xb3f6cd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb3f6d2  ldarg.1
0xb3f6d3  ldstr    aValue_2// "value"
0xb3f6d8  ldstr    aAFaF098AFaF094// "[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-"...
0xb3f6dd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xb3f6e2  ldarg.1
0xb3f6e3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb3f6e8  ldarg.1
0xb3f6e9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb3f6ee  ldarg.1
0xb3f6ef  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb3f6f4  ret
0xb3f6f5  ldarg.0
0xb3f6f6  ldtoken  [mscorlib]System.Decimal
0xb3f6fb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb3f700  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xb3f705  brfalse  loc_B3F798
0xb3f70a  ldarg.1
0xb3f70b  ldstr    aSimpletype// "simpleType"
0xb3f710  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0xb3f715  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb3f71a  ldarg.1
0xb3f71b  ldstr    aRestriction_0// "restriction"
0xb3f720  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0xb3f725  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb3f72a  ldarg.1
0xb3f72b  ldstr    aBase// "base"
0xb3f730  ldstr    aXsDecimal// "xs:decimal"
0xb3f735  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xb3f73a  ldarg.2
0xb3f73b  ldstr    aDecimalDigits// "Decimal Digits"
0xb3f740  ldloca.s 0
0xb3f742  callvirt instance bool class [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.Collections.IReadOnlyDictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0xb3f747  brfalse.s loc_B3F78B
0xb3f749  ldloc.0
0xb3f74a  isinst   valuetype [mscorlib]System.Nullable`1<int32>
0xb3f74f  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0xb3f754  stloc.1
0xb3f755  ldloca.s 1
0xb3f757  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xb3f75c  brfalse.s loc_B3F78B
0xb3f75e  ldarg.1
0xb3f75f  ldstr    aFractiondigits// "fractionDigits"
0xb3f764  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0xb3f769  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb3f76e  ldarg.1
0xb3f76f  ldstr    aValue_2// "value"
0xb3f774  ldloca.s 1
0xb3f776  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xb3f77b  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0xb3f780  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xb3f785  ldarg.1
0xb3f786  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb3f78b  ldarg.1
0xb3f78c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb3f791  ldarg.1
0xb3f792  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb3f797  ret
0xb3f798  ldarg.0
0xb3f799  callvirt instance bool [mscorlib]System.Type::get_IsEnum()
0xb3f79e  brfalse  loc_B3F8C4
0xb3f7a3  ldarg.0
0xb3f7a4  ldtoken  [mscorlib]System.FlagsAttribute
0xb3f7a9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb3f7ae  ldc.i4.0
0xb3f7af  callvirt instance object[] [mscorlib]System.Reflection.MemberInfo::GetCustomAttributes(class [mscorlib]System.Type, bool)
0xb3f7b4  stloc.2
0xb3f7b5  ldloc.2
0xb3f7b6  ldlen
0xb3f7b7  conv.i4
0xb3f7b8  brtrue   loc_B3F83D
0xb3f7bd  ldarg.1
0xb3f7be  ldstr    aSimpletype// "simpleType"
0xb3f7c3  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0xb3f7c8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb3f7cd  ldarg.1
0xb3f7ce  ldstr    aRestriction_0// "restriction"
0xb3f7d3  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0xb3f7d8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb3f7dd  ldarg.1
0xb3f7de  ldstr    aBase// "base"
0xb3f7e3  ldstr    aXsString// "xs:string"
0xb3f7e8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xb3f7ed  ldarg.0
0xb3f7ee  call     string[] [mscorlib]System.Enum::GetNames(class [mscorlib]System.Type)
0xb3f7f3  stloc.s  5
0xb3f7f5  ldc.i4.0
0xb3f7f6  stloc.s  6
0xb3f7f8  br.s     loc_B3F828
0xb3f7fa  ldloc.s  5
0xb3f7fc  ldloc.s  6
0xb3f7fe  ldelem.ref
0xb3f7ff  stloc.3
0xb3f800  ldarg.1
0xb3f801  ldstr    aEnumeration// "enumeration"
0xb3f806  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0xb3f80b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb3f810  ldarg.1
0xb3f811  ldstr    aValue_2// "value"
0xb3f816  ldloc.3
0xb3f817  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xb3f81c  ldarg.1
0xb3f81d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb3f822  ldloc.s  6
0xb3f824  ldc.i4.1
0xb3f825  add
0xb3f826  stloc.s  6
0xb3f828  ldloc.s  6
0xb3f82a  ldloc.s  5
0xb3f82c  ldlen
0xb3f82d  conv.i4
0xb3f82e  blt.s    loc_B3F7FA
0xb3f830  ldarg.1
0xb3f831  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb3f836  ldarg.1
0xb3f837  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb3f83c  ret
0xb3f83d  ldarg.1
0xb3f83e  ldstr    aComplextype// "complexType"
0xb3f843  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0xb3f848  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb3f84d  ldarg.1
0xb3f84e  ldstr    aSequence_2// "sequence"
0xb3f853  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0xb3f858  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb3f85d  ldarg.0
0xb3f85e  call     string[] [mscorlib]System.Enum::GetNames(class [mscorlib]System.Type)
0xb3f863  stloc.s  7
0xb3f865  ldc.i4.0
0xb3f866  stloc.s  8
0xb3f868  br.s     loc_B3F8AF
0xb3f86a  ldloc.s  7
0xb3f86c  ldloc.s  8
0xb3f86e  ldelem.ref
0xb3f86f  stloc.s  4
0xb3f871  ldarg.1
0xb3f872  ldstr    aElement// "element"
0xb3f877  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0xb3f87c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb3f881  ldarg.1
0xb3f882  ldstr    aName// "name"
0xb3f887  ldloc.s  4
0xb3f889  call     string [System.Xml]System.Xml.XmlConvert::EncodeLocalName(string)
0xb3f88e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xb3f893  ldarg.1
0xb3f894  ldstr    aType_0// "type"
0xb3f899  ldstr    aXsBoolean// "xs:boolean"
0xb3f89e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xb3f8a3  ldarg.1
0xb3f8a4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb3f8a9  ldloc.s  8
0xb3f8ab  ldc.i4.1
0xb3f8ac  add
0xb3f8ad  stloc.s  8
0xb3f8af  ldloc.s  8
0xb3f8b1  ldloc.s  7
0xb3f8b3  ldlen
0xb3f8b4  conv.i4
0xb3f8b5  blt.s    loc_B3F86A
0xb3f8b7  ldarg.1
0xb3f8b8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb3f8bd  ldarg.1
0xb3f8be  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb3f8c3  ret
0xb3f8c4  ldarg.1
0xb3f8c5  ldstr    aComplextype// "complexType"
0xb3f8ca  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0xb3f8cf  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb3f8d4  ldarg.1
0xb3f8d5  ldstr    aSequence_2// "sequence"
0xb3f8da  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0xb3f8df  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb3f8e4  ldarg.1
0xb3f8e5  ldstr    aAny// "any"
0xb3f8ea  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0xb3f8ef  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb3f8f4  ldarg.1
0xb3f8f5  ldstr    aMinoccurs// "minOccurs"
0xb3f8fa  ldstr    a0// "0"
0xb3f8ff  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xb3f904  ldarg.1
0xb3f905  ldstr    aMaxoccurs// "maxOccurs"
0xb3f90a  ldstr    a1// "1"
0xb3f90f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xb3f914  ldarg.1
0xb3f915  ldstr    aProcesscontent_0// "processContents"
0xb3f91a  ldstr    aLax// "lax"
0xb3f91f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xb3f924  ldarg.1
0xb3f925  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb3f92a  ldarg.1
0xb3f92b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb3f930  ldarg.1
0xb3f931  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb3f936  ret
```
