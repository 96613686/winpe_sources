# System.Xml.Xsl.Qil.QilXmlReader::StartElement

- ea: `0x3b7d0`
- end: `0x3bba3`
- name: `System.Xml.Xsl.Qil.QilXmlReader::StartElement`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x3b700`

## callees

- `0x362b0`
- `0x362d0`
- `0x36300`
- `0x36330`
- `0x36360`
- `0x363b0`
- `0x364b0`
- `0x376f0`
- `0x37710`
- `0x377c0`
- `0x3b7d0`
- `0x3c320`
- `0x3c370`
- `0x3c410`
- `0x3c4d0`
- `0x50af0`
- `0x57660`

## string_xrefs

- `0x3bb3e`: `xmlType`

## pseudocode

```c

```

## disassembly

```asm
0x3b7d0  newobj   instance void ReaderAnnotation::.ctor()
0x3b7d5  stloc.1
0x3b7d6  ldarg.0
0x3b7d7  ldfld    class [System.Xml]System.Xml.XmlReader System.Xml.Xsl.Qil.QilXmlReader::r
0x3b7dc  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x3b7e1  stloc.2
0x3b7e2  ldarg.0
0x3b7e3  ldfld    class [System.Xml]System.Xml.XmlReader System.Xml.Xsl.Qil.QilXmlReader::r
0x3b7e8  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x3b7ed  stloc.3
0x3b7ee  ldloc.3
0x3b7ef  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x3b7f4  stloc.s  4
0x3b7f6  ldloc.s  4
0x3b7f8  ldc.i4   0x683DC865
0x3b7fd  bgt.un.s loc_3B871
0x3b7ff  ldloc.s  4
0x3b801  ldc.i4   0x1782346C
0x3b806  bgt.un.s loc_3B831
0x3b808  ldloc.s  4
0x3b80a  ldc.i4   0x91EF7FF
0x3b80f  beq      loc_3B90D
0x3b814  ldloc.s  4
0x3b816  ldc.i4   0xF7E1B30
0x3b81b  beq      loc_3B976
0x3b820  ldloc.s  4
0x3b822  ldc.i4   0x1782346C
0x3b827  beq      loc_3B961
0x3b82c  br       loc_3BB2A
0x3b831  ldloc.s  4
0x3b833  ldc.i4   0x1B6192D7
0x3b838  bgt.un.s loc_3B857
0x3b83a  ldloc.s  4
0x3b83c  ldc.i4   0x1848BBB0
0x3b841  beq      loc_3B9A0
0x3b846  ldloc.s  4
0x3b848  ldc.i4   0x1B6192D7
0x3b84d  beq      loc_3B9CA
0x3b852  br       loc_3BB2A
0x3b857  ldloc.s  4
0x3b859  ldc.i4   0x3F500919
0x3b85e  beq      loc_3B922
0x3b863  ldloc.s  4
0x3b865  ldc.i4   0x683DC865
0x3b86a  beq.s    loc_3B8E3
0x3b86c  br       loc_3BB2A
0x3b871  ldloc.s  4
0x3b873  ldc.i4   0x98A79A69
0x3b878  bgt.un.s loc_3B8A0
0x3b87a  ldloc.s  4
0x3b87c  ldc.i4   0x7E82EE73
0x3b881  beq      loc_3B9F4
0x3b886  ldloc.s  4
0x3b888  ldc.i4   0x95269028
0x3b88d  beq.s    loc_3B8F8
0x3b88f  ldloc.s  4
0x3b891  ldc.i4   0x98A79A69
0x3b896  beq      loc_3B9B5
0x3b89b  br       loc_3BB2A
0x3b8a0  ldloc.s  4
0x3b8a2  ldc.i4   0xADB997AC
0x3b8a7  bgt.un.s loc_3B8C6
0x3b8a9  ldloc.s  4
0x3b8ab  ldc.i4   0xAAAE4B53
0x3b8b0  beq      loc_3B937
0x3b8b5  ldloc.s  4
0x3b8b7  ldc.i4   0xADB997AC
0x3b8bc  beq      loc_3B94C
0x3b8c1  br       loc_3BB2A
0x3b8c6  ldloc.s  4
0x3b8c8  ldc.i4   0xB2F59B9A
0x3b8cd  beq      loc_3B98B
0x3b8d2  ldloc.s  4
0x3b8d4  ldc.i4   0xEC1CC8F9
0x3b8d9  beq      loc_3B9DF
0x3b8de  br       loc_3BB2A
0x3b8e3  ldloc.3
0x3b8e4  ldstr    aLiteralstring// "LiteralString"
0x3b8e9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3b8ee  brtrue   loc_3BA09
0x3b8f3  br       loc_3BB2A
0x3b8f8  ldloc.3
0x3b8f9  ldstr    aLiteralint32// "LiteralInt32"
0x3b8fe  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3b903  brtrue   loc_3BA20
0x3b908  br       loc_3BB2A
0x3b90d  ldloc.3
0x3b90e  ldstr    aLiteralint64// "LiteralInt64"
0x3b913  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3b918  brtrue   loc_3BA41
0x3b91d  br       loc_3BB2A
0x3b922  ldloc.3
0x3b923  ldstr    aLiteraldouble// "LiteralDouble"
0x3b928  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3b92d  brtrue   loc_3BA62
0x3b932  br       loc_3BB2A
0x3b937  ldloc.3
0x3b938  ldstr    aLiteraldecimal// "LiteralDecimal"
0x3b93d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3b942  brtrue   loc_3BA83
0x3b947  br       loc_3BB2A
0x3b94c  ldloc.3
0x3b94d  ldstr    aLiteraltype// "LiteralType"
0x3b952  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3b957  brtrue   loc_3BAA4
0x3b95c  br       loc_3BB2A
0x3b961  ldloc.3
0x3b962  ldstr    aLiteralqname// "LiteralQName"
0x3b967  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3b96c  brtrue   loc_3BABE
0x3b971  br       loc_3BB2A
0x3b976  ldloc.3
0x3b977  ldstr    aFor_0// "For"
0x3b97c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3b981  brtrue   loc_3BAD7
0x3b986  br       loc_3BB2A
0x3b98b  ldloc.3
0x3b98c  ldstr    aLet// "Let"
0x3b991  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3b996  brtrue   loc_3BAD7
0x3b99b  br       loc_3BB2A
0x3b9a0  ldloc.3
0x3b9a1  ldstr    aParameter// "Parameter"
0x3b9a6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3b9ab  brtrue   loc_3BAD7
0x3b9b0  br       loc_3BB2A
0x3b9b5  ldloc.3
0x3b9b6  ldstr    aFunction_0// "Function"
0x3b9bb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3b9c0  brtrue   loc_3BAD7
0x3b9c5  br       loc_3BB2A
0x3b9ca  ldloc.3
0x3b9cb  ldstr    aRefto// "RefTo"
0x3b9d0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3b9d5  brtrue   loc_3BAD7
0x3b9da  br       loc_3BB2A
0x3b9df  ldloc.3
0x3b9e0  ldstr    aXsltinvokeearl// "XsltInvokeEarlyBound"
0x3b9e5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3b9ea  brtrue   loc_3BB0B
0x3b9ef  br       loc_3BB2A
0x3b9f4  ldloc.3
0x3b9f5  ldstr    aForwarddecls// "ForwardDecls"
0x3b9fa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3b9ff  brtrue   loc_3BB23
0x3ba04  br       loc_3BB2A
0x3ba09  ldarg.0
0x3ba0a  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilXmlReader::f
0x3ba0f  ldarg.0
0x3ba10  call     instance string System.Xml.Xsl.Qil.QilXmlReader::ReadText()
0x3ba15  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralString(string value)
0x3ba1a  stloc.0
0x3ba1b  br       loc_3BB36
0x3ba20  ldarg.0
0x3ba21  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilXmlReader::f
0x3ba26  ldarg.0
0x3ba27  call     instance string System.Xml.Xsl.Qil.QilXmlReader::ReadText()
0x3ba2c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3ba31  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x3ba36  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralInt32(int32 value)
0x3ba3b  stloc.0
0x3ba3c  br       loc_3BB36
0x3ba41  ldarg.0
0x3ba42  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilXmlReader::f
0x3ba47  ldarg.0
0x3ba48  call     instance string System.Xml.Xsl.Qil.QilXmlReader::ReadText()
0x3ba4d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3ba52  call     int64 [mscorlib]System.Int64::Parse(string, class [mscorlib]System.IFormatProvider)
0x3ba57  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralInt64(int64 value)
0x3ba5c  stloc.0
0x3ba5d  br       loc_3BB36
0x3ba62  ldarg.0
0x3ba63  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilXmlReader::f
0x3ba68  ldarg.0
0x3ba69  call     instance string System.Xml.Xsl.Qil.QilXmlReader::ReadText()
0x3ba6e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3ba73  call     float64 [mscorlib]System.Double::Parse(string, class [mscorlib]System.IFormatProvider)
0x3ba78  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralDouble(float64 value)
0x3ba7d  stloc.0
0x3ba7e  br       loc_3BB36
0x3ba83  ldarg.0
0x3ba84  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilXmlReader::f
0x3ba89  ldarg.0
0x3ba8a  call     instance string System.Xml.Xsl.Qil.QilXmlReader::ReadText()
0x3ba8f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3ba94  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::Parse(string, class [mscorlib]System.IFormatProvider)
0x3ba99  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralDecimal(valuetype [mscorlib]System.Decimal value)
0x3ba9e  stloc.0
0x3ba9f  br       loc_3BB36
0x3baa4  ldarg.0
0x3baa5  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilXmlReader::f
0x3baaa  ldarg.0
0x3baab  ldarg.0
0x3baac  call     instance string System.Xml.Xsl.Qil.QilXmlReader::ReadText()
0x3bab1  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilXmlReader::ParseType(string s)
0x3bab6  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralType(class System.Xml.Xsl.XmlQueryType value)
0x3babb  stloc.0
0x3babc  br.s     loc_3BB36
0x3babe  ldarg.0
0x3babf  ldarg.0
0x3bac0  ldfld    class [System.Xml]System.Xml.XmlReader System.Xml.Xsl.Qil.QilXmlReader::r
0x3bac5  ldstr    aName// "name"
0x3baca  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x3bacf  call     instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilXmlReader::ParseName(string name)
0x3bad4  stloc.0
0x3bad5  br.s     loc_3BB36
0x3bad7  ldloc.1
0x3bad8  ldarg.0
0x3bad9  ldfld    class [System.Xml]System.Xml.XmlReader System.Xml.Xsl.Qil.QilXmlReader::r
0x3bade  ldstr    aId// "id"
0x3bae3  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x3bae8  stfld    string ReaderAnnotation::Id
0x3baed  ldloc.1
0x3baee  ldarg.0
0x3baef  ldarg.0
0x3baf0  ldfld    class [System.Xml]System.Xml.XmlReader System.Xml.Xsl.Qil.QilXmlReader::r
0x3baf5  ldstr    aName// "name"
0x3bafa  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x3baff  call     instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilXmlReader::ParseName(string name)
0x3bb04  stfld    class System.Xml.Xsl.Qil.QilName ReaderAnnotation::Name
0x3bb09  br.s     loc_3BB2A
0x3bb0b  ldloc.1
0x3bb0c  ldarg.0
0x3bb0d  ldfld    class [System.Xml]System.Xml.XmlReader System.Xml.Xsl.Qil.QilXmlReader::r
0x3bb12  ldstr    aClrnamespace// "clrNamespace"
0x3bb17  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x3bb1c  stfld    string ReaderAnnotation::ClrNamespace
0x3bb21  br.s     loc_3BB2A
0x3bb23  ldarg.0
0x3bb24  ldc.i4.1
0x3bb25  stfld    bool System.Xml.Xsl.Qil.QilXmlReader::inFwdDecls
0x3bb2a  ldarg.0
0x3bb2b  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilXmlReader::f
0x3bb30  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilFactory::Sequence()
0x3bb35  stloc.0
0x3bb36  ldloc.1
0x3bb37  ldarg.0
0x3bb38  ldarg.0
0x3bb39  ldfld    class [System.Xml]System.Xml.XmlReader System.Xml.Xsl.Qil.QilXmlReader::r
0x3bb3e  ldstr    aXmltype// "xmlType"
0x3bb43  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x3bb48  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilXmlReader::ParseType(string s)
0x3bb4d  stfld    class System.Xml.Xsl.XmlQueryType ReaderAnnotation::XmlType
0x3bb52  ldloc.0
0x3bb53  ldarg.0
0x3bb54  ldarg.0
0x3bb55  ldfld    class [System.Xml]System.Xml.XmlReader System.Xml.Xsl.Qil.QilXmlReader::r
0x3bb5a  ldstr    aLineinfo// "lineInfo"
0x3bb5f  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x3bb64  call     instance class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Qil.QilXmlReader::ParseLineInfo(string s)
0x3bb69  callvirt instance void System.Xml.Xsl.Qil.QilNode::set_SourceLine(class System.Xml.Xsl.ISourceLineInfo value)
0x3bb6e  ldloc.0
0x3bb6f  ldloc.1
0x3bb70  callvirt instance void System.Xml.Xsl.Qil.QilNode::set_Annotation(object value)
0x3bb75  ldloc.0
0x3bb76  isinst   System.Xml.Xsl.Qil.QilList
0x3bb7b  brfalse.s loc_3BB90
0x3bb7d  ldarg.0
0x3bb7e  ldfld    class [System]System.Collections.Generic.Stack`1<class System.Xml.Xsl.Qil.QilList> System.Xml.Xsl.Qil.QilXmlReader::stk
0x3bb83  ldloc.0
0x3bb84  castclass System.Xml.Xsl.Qil.QilList
0x3bb89  callvirt instance void class [System]System.Collections.Generic.Stack`1<class System.Xml.Xsl.Qil.QilList>::Push(var<u1>)
0x3bb8e  ldc.i4.1
0x3bb8f  ret
0x3bb90  ldarg.0
0x3bb91  ldfld    class [System]System.Collections.Generic.Stack`1<class System.Xml.Xsl.Qil.QilList> System.Xml.Xsl.Qil.QilXmlReader::stk
0x3bb96  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class System.Xml.Xsl.Qil.QilList>::Peek()
0x3bb9b  ldloc.0
0x3bb9c  callvirt instance void System.Xml.Xsl.Qil.QilNode::Add(class System.Xml.Xsl.Qil.QilNode node)
0x3bba1  ldc.i4.0
0x3bba2  ret
```
