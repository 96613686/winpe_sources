# Microsoft.SharePoint.WebControls.XsdWriter::WriteDataXsd

- ea: `0x86e750`
- end: `0x86eb1c`
- name: `Microsoft.SharePoint.WebControls.XsdWriter::WriteDataXsd`
- size: `972`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x86e030`

## callees

- `0x86e660`
- `0x86e6b0`
- `0x86e750`

## string_xrefs

- `0x86e984`: `http://www.w3.org/2001/XMLSchema`
- `0x86ea34`: `http://www.w3.org/2001/XMLSchema`
- `0x86ea47`: `http://www.w3.org/2001/XMLSchema`
- `0x86e754`: `http://schemas.microsoft.com/sharepoint/dsp`
- `0x86e858`: `http://schemas.microsoft.com/sharepoint/dsp`
- `0x86e87a`: `http://schemas.microsoft.com/sharepoint/dsp`
- `0x86e89c`: `http://schemas.microsoft.com/sharepoint/dsp`
- `0x86e8be`: `http://schemas.microsoft.com/sharepoint/dsp`
- `0x86e8e0`: `http://schemas.microsoft.com/sharepoint/dsp`
- `0x86e90d`: `http://schemas.microsoft.com/sharepoint/dsp`
- `0x86e934`: `http://schemas.microsoft.com/sharepoint/dsp`
- `0x86e9dd`: `http://schemas.microsoft.com/sharepoint/dsp`
- `0x86ea74`: `http://schemas.microsoft.com/sharepoint/dsp`
- `0x86eab9`: `http://schemas.microsoft.com/sharepoint/dsp`
- `0x86e788`: `complexType`
- `0x86e7ed`: `complexType`
- `0x86e875`: `readOnly`

## pseudocode

```c

```

## disassembly

```asm
0x86e750  ldarg.1
0x86e751  brtrue.s loc_86E754
0x86e753  ret
0x86e754  ldstr    aHttpSchemasMic_148// "http://schemas.microsoft.com/sharepoint"...
0x86e759  stloc.0
0x86e75a  ldarg.0
0x86e75b  ldloca.s 1
0x86e75d  ldloc.0
0x86e75e  call     instance void Microsoft.SharePoint.WebControls.XsdWriter::WriteSchemaStart([out] class [System.Xml]System.Xml.XmlTextWriter& xtw, string szTargetNS)
0x86e763  ldloc.1
0x86e764  ldstr    aX_0// "x"
0x86e769  ldstr    aElement// "element"
0x86e76e  ldnull
0x86e76f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0x86e774  ldloc.1
0x86e775  ldnull
0x86e776  ldstr    aName// "name"
0x86e77b  ldnull
0x86e77c  ldarg.2
0x86e77d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x86e782  ldloc.1
0x86e783  ldstr    aX_0// "x"
0x86e788  ldstr    aComplextype// "complexType"
0x86e78d  ldnull
0x86e78e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0x86e793  ldloc.1
0x86e794  ldstr    aX_0// "x"
0x86e799  ldstr    aSequence_2// "sequence"
0x86e79e  ldnull
0x86e79f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0x86e7a4  ldloc.1
0x86e7a5  ldnull
0x86e7a6  ldstr    aMaxoccurs// "maxOccurs"
0x86e7ab  ldnull
0x86e7ac  ldstr    aUnbounded// "unbounded"
0x86e7b1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x86e7b6  ldloc.1
0x86e7b7  ldstr    aX_0// "x"
0x86e7bc  ldstr    aElement// "element"
0x86e7c1  ldnull
0x86e7c2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0x86e7c7  ldloc.1
0x86e7c8  ldnull
0x86e7c9  ldstr    aName// "name"
0x86e7ce  ldnull
0x86e7cf  ldarg.3
0x86e7d0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x86e7d5  ldloc.1
0x86e7d6  ldnull
0x86e7d7  ldstr    aMinoccurs// "minOccurs"
0x86e7dc  ldnull
0x86e7dd  ldstr    a0// "0"
0x86e7e2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x86e7e7  ldloc.1
0x86e7e8  ldstr    aX_0// "x"
0x86e7ed  ldstr    aComplextype// "complexType"
0x86e7f2  ldnull
0x86e7f3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0x86e7f8  ldc.i4.0
0x86e7f9  stloc.2
0x86e7fa  br       loc_86EAD2
0x86e7ff  ldarg.1
0x86e800  ldloc.2
0x86e801  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class ColumnInfo>::get_Item(!!T0)
0x86e806  stloc.3
0x86e807  ldloc.1
0x86e808  ldstr    aX_0// "x"
0x86e80d  ldstr    aAttribute// "attribute"
0x86e812  ldnull
0x86e813  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0x86e818  ldloc.1
0x86e819  ldnull
0x86e81a  ldstr    aName// "name"
0x86e81f  ldnull
0x86e820  ldloc.3
0x86e821  ldfld    string ColumnInfo::szName
0x86e826  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x86e82b  ldloc.3
0x86e82c  ldfld    bool ColumnInfo::fAllowNull
0x86e831  brtrue.s loc_86E845
0x86e833  ldloc.1
0x86e834  ldnull
0x86e835  ldstr    aUse_1// "use"
0x86e83a  ldnull
0x86e83b  ldstr    aRequired_2// "required"
0x86e840  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x86e845  ldloc.3
0x86e846  ldfld    bool ColumnInfo::fSortable
0x86e84b  brtrue.s loc_86E867
0x86e84d  ldloc.1
0x86e84e  ldstr    aD// "d"
0x86e853  ldstr    aSortable_0// "sortable"
0x86e858  ldstr    aHttpSchemasMic_148// "http://schemas.microsoft.com/sharepoint"...
0x86e85d  ldstr    aFalse// "false"
0x86e862  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x86e867  ldloc.3
0x86e868  ldfld    bool ColumnInfo::fReadOnly
0x86e86d  brfalse.s loc_86E889
0x86e86f  ldloc.1
0x86e870  ldstr    aD// "d"
0x86e875  ldstr    aReadonly_1// "readOnly"
0x86e87a  ldstr    aHttpSchemasMic_148// "http://schemas.microsoft.com/sharepoint"...
0x86e87f  ldstr    aTrue// "true"
0x86e884  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x86e889  ldloc.3
0x86e88a  ldfld    bool ColumnInfo::fUrlDescription
0x86e88f  brfalse.s loc_86E8AB
0x86e891  ldloc.1
0x86e892  ldstr    aD// "d"
0x86e897  ldstr    aUrldescription// "urlDescription"
0x86e89c  ldstr    aHttpSchemasMic_148// "http://schemas.microsoft.com/sharepoint"...
0x86e8a1  ldstr    aTrue// "true"
0x86e8a6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x86e8ab  ldloc.3
0x86e8ac  ldfld    bool ColumnInfo::fRichText
0x86e8b1  brfalse.s loc_86E8CD
0x86e8b3  ldloc.1
0x86e8b4  ldstr    aD// "d"
0x86e8b9  ldstr    aHtml_0// "html"
0x86e8be  ldstr    aHttpSchemasMic_148// "http://schemas.microsoft.com/sharepoint"...
0x86e8c3  ldstr    aTrue// "true"
0x86e8c8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x86e8cd  ldloc.3
0x86e8ce  ldfld    int32 ColumnInfo::iCurrency
0x86e8d3  brfalse.s loc_86E8FA
0x86e8d5  ldloc.1
0x86e8d6  ldstr    aD// "d"
0x86e8db  ldstr    aCurrency_0// "currency"
0x86e8e0  ldstr    aHttpSchemasMic_148// "http://schemas.microsoft.com/sharepoint"...
0x86e8e5  ldloc.3
0x86e8e6  ldflda   int32 ColumnInfo::iCurrency
0x86e8eb  call     class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.NumberFormatInfo::get_InvariantInfo()
0x86e8f0  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x86e8f5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x86e8fa  ldloc.3
0x86e8fb  ldfld    string ColumnInfo::szDisplayName
0x86e900  brfalse.s loc_86E91D
0x86e902  ldloc.1
0x86e903  ldstr    aD// "d"
0x86e908  ldstr    aDisplayname_0// "displayName"
0x86e90d  ldstr    aHttpSchemasMic_148// "http://schemas.microsoft.com/sharepoint"...
0x86e912  ldloc.3
0x86e913  ldfld    string ColumnInfo::szDisplayName
0x86e918  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x86e91d  ldloc.3
0x86e91e  ldfld    valuetype SchemaDataTypes ColumnInfo::xsdtCategory
0x86e923  ldc.i4.1
0x86e924  bne.un   loc_86EA19
0x86e929  ldloc.1
0x86e92a  ldstr    aD// "d"
0x86e92f  ldstr    aOutputformat// "outputFormat"
0x86e934  ldstr    aHttpSchemasMic_148// "http://schemas.microsoft.com/sharepoint"...
0x86e939  ldloc.3
0x86e93a  ldfld    valuetype Microsoft.SharePoint.SPChoiceFormatType ColumnInfo::_eDisplayType
0x86e93f  box      Microsoft.SharePoint.SPChoiceFormatType
0x86e944  callvirt instance string [mscorlib]System.Object::ToString()
0x86e949  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x86e94e  ldloc.1
0x86e94f  ldstr    aX_0// "x"
0x86e954  ldstr    aSimpletype// "simpleType"
0x86e959  ldnull
0x86e95a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0x86e95f  ldloc.1
0x86e960  ldstr    aX_0// "x"
0x86e965  ldstr    aRestriction_0// "restriction"
0x86e96a  ldnull
0x86e96b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0x86e970  ldloc.1
0x86e971  ldnull
0x86e972  ldstr    aBase// "base"
0x86e977  ldnull
0x86e978  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartAttribute(string, string, string)
0x86e97d  ldloc.1
0x86e97e  ldloc.3
0x86e97f  ldfld    string ColumnInfo::szBaseType
0x86e984  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0x86e989  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteQualifiedName(string, string)
0x86e98e  ldloc.1
0x86e98f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndAttribute()
0x86e994  ldc.i4.0
0x86e995  stloc.s  4
0x86e997  ldloc.3
0x86e998  ldfld    bool ColumnInfo::fLookup
0x86e99d  brfalse.s loc_86E9A2
0x86e99f  ldc.i4.1
0x86e9a0  stloc.s  4
0x86e9a2  ldc.i4.0
0x86e9a3  stloc.s  5
0x86e9a5  br.s     loc_86E9FC
0x86e9a7  ldloc.1
0x86e9a8  ldstr    aX_0// "x"
0x86e9ad  ldstr    aEnumeration// "enumeration"
0x86e9b2  ldnull
0x86e9b3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0x86e9b8  ldloc.1
0x86e9b9  ldnull
0x86e9ba  ldstr    aValue_2// "value"
0x86e9bf  ldnull
0x86e9c0  ldloc.3
0x86e9c1  ldfld    string[] ColumnInfo::rgszEnumValues
0x86e9c6  ldloc.s  5
0x86e9c8  ldelem.ref
0x86e9c9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x86e9ce  ldloc.s  4
0x86e9d0  brfalse.s loc_86E9F0
0x86e9d2  ldloc.1
0x86e9d3  ldstr    aD// "d"
0x86e9d8  ldstr    aLookupid_0// "lookupId"
0x86e9dd  ldstr    aHttpSchemasMic_148// "http://schemas.microsoft.com/sharepoint"...
0x86e9e2  ldloc.3
0x86e9e3  ldfld    string[] ColumnInfo::rgszLookupIds
0x86e9e8  ldloc.s  5
0x86e9ea  ldelem.ref
0x86e9eb  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x86e9f0  ldloc.1
0x86e9f1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x86e9f6  ldloc.s  5
0x86e9f8  ldc.i4.1
0x86e9f9  add
0x86e9fa  stloc.s  5
0x86e9fc  ldloc.s  5
0x86e9fe  ldloc.3
0x86e9ff  ldfld    string[] ColumnInfo::rgszEnumValues
0x86ea04  ldlen
0x86ea05  conv.i4
0x86ea06  blt.s    loc_86E9A7
0x86ea08  ldloc.1
0x86ea09  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x86ea0e  ldloc.1
0x86ea0f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x86ea14  br       loc_86EAC8
0x86ea19  ldloc.1
0x86ea1a  ldnull
0x86ea1b  ldstr    aType_0// "type"
0x86ea20  ldnull
0x86ea21  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartAttribute(string, string, string)
0x86ea26  ldloc.3
0x86ea27  ldfld    bool ColumnInfo::fUrlDescription
0x86ea2c  brfalse.s loc_86EA40
0x86ea2e  ldloc.1
0x86ea2f  ldstr    aString// "string"
0x86ea34  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0x86ea39  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteQualifiedName(string, string)
0x86ea3e  br.s     loc_86EA51
0x86ea40  ldloc.1
0x86ea41  ldloc.3
0x86ea42  ldfld    string ColumnInfo::szBaseType
0x86ea47  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0x86ea4c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteQualifiedName(string, string)
0x86ea51  ldloc.1
0x86ea52  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndAttribute()
0x86ea57  ldloc.3
0x86ea58  ldfld    string ColumnInfo::szBaseType
0x86ea5d  ldstr    aDatetime_3// "dateTime"
0x86ea62  call     bool [mscorlib]System.String::op_Equality(string, string)
0x86ea67  brfalse.s loc_86EA94
0x86ea69  ldloc.1
0x86ea6a  ldstr    aD// "d"
0x86ea6f  ldstr    aOutputformat// "outputFormat"
0x86ea74  ldstr    aHttpSchemasMic_148// "http://schemas.microsoft.com/sharepoint"...
0x86ea79  ldloc.3
0x86ea7a  ldfld    bool ColumnInfo::_fDateOnly
0x86ea7f  brtrue.s loc_86EA88
0x86ea81  ldstr    aDatetime// "DateTime"
0x86ea86  br.s     loc_86EA8D
0x86ea88  ldstr    aDateonly// "DateOnly"
0x86ea8d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x86ea92  br.s     loc_86EAC8
0x86ea94  ldloc.3
0x86ea95  ldfld    string ColumnInfo::szBaseType
0x86ea9a  ldstr    aString// "string"
0x86ea9f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x86eaa4  brfalse.s loc_86EAC8
0x86eaa6  ldloc.3
0x86eaa7  ldfld    bool ColumnInfo::_fMultiLine
0x86eaac  brfalse.s loc_86EAC8
0x86eaae  ldloc.1
0x86eaaf  ldstr    aD// "d"
0x86eab4  ldstr    aOutputformat// "outputFormat"
0x86eab9  ldstr    aHttpSchemasMic_148// "http://schemas.microsoft.com/sharepoint"...
0x86eabe  ldstr    aMultilinetext// "multiLineText"
0x86eac3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x86eac8  ldloc.1
0x86eac9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x86eace  ldloc.2
0x86eacf  ldc.i4.1
0x86ead0  add
0x86ead1  stloc.2
0x86ead2  ldloc.2
0x86ead3  ldarg.1
0x86ead4  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class ColumnInfo>::get_Count()
0x86ead9  blt      loc_86E7FF
0x86eade  ldloc.1
0x86eadf  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x86eae4  ldloc.1
0x86eae5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x86eaea  ldloc.1
0x86eaeb  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x86eaf0  ldloc.1
0x86eaf1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
  ... truncated ...
```
