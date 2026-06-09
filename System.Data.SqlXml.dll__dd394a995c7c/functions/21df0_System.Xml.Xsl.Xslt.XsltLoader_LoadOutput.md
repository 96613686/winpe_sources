# System.Xml.Xsl.Xslt.XsltLoader::LoadOutput

- ea: `0x21df0`
- end: `0x223ca`
- name: `System.Xml.Xsl.Xslt.XsltLoader::LoadOutput`
- size: `1498`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x21890`

## callees

- `0x13b60`
- `0x13b70`
- `0x1f920`
- `0x20590`
- `0x206d0`
- `0x20800`
- `0x21df0`
- `0x24e00`
- `0x24f00`
- `0x24fd0`
- `0x250f0`
- `0x25200`
- `0x25410`
- `0x255a0`
- `0x255c0`
- `0x375d0`

## string_xrefs

- `0x22256`: `omit-xml-declaration`
- `0x22298`: `omit-xml-declaration`
- `0x22128`: `escape-uri-attributes`
- `0x2213c`: `xsl:output/@escape-uri-attributes == flase()`

## pseudocode

```c

```

## disassembly

```asm
0x21df0  ldarg.0
0x21df1  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21df6  ldarg.0
0x21df7  ldfld    valuetype XsltAttribute[] System.Xml.Xsl.Xslt.XsltLoader::outputAttributes
0x21dfc  callvirt instance class ContextInfo System.Xml.Xsl.Xslt.XsltInput::GetAttributes(valuetype XsltAttribute[] attributes)
0x21e01  stloc.0
0x21e02  ldarg.0
0x21e03  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltLoader::compiler
0x21e08  ldfld    class System.Xml.Xsl.Xslt.Output System.Xml.Xsl.Xslt.Compiler::Output
0x21e0d  stloc.1
0x21e0e  ldloc.1
0x21e0f  ldfld    class [System.Xml]System.Xml.XmlWriterSettings System.Xml.Xsl.Xslt.Output::Settings
0x21e14  stloc.2
0x21e15  ldarg.0
0x21e16  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltLoader::compiler
0x21e1b  ldfld    int32 System.Xml.Xsl.Xslt.Compiler::CurrentPrecedence
0x21e20  stloc.3
0x21e21  ldarg.0
0x21e22  ldc.i4.0
0x21e23  call     instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XsltLoader::ParseQNameAttribute(int32 attNum)
0x21e28  stloc.s  5
0x21e2a  ldloc.s  5
0x21e2c  ldnull
0x21e2d  call     bool System.Xml.Xsl.Qil.QilName::op_Inequality(class System.Xml.Xsl.Qil.QilName a, class System.Xml.Xsl.Qil.QilName b)
0x21e32  brfalse.s loc_21E3F
0x21e34  ldarg.0
0x21e35  ldstr    aXslOutputName// "xsl:output/@name"
0x21e3a  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportNYI(string arg)
0x21e3f  ldarg.0
0x21e40  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21e45  ldc.i4.1
0x21e46  ldstr    aMethod// "method"
0x21e4b  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToXsltAttribute(int32 attNum, string attName)
0x21e50  brfalse  loc_21EEB
0x21e55  ldloc.1
0x21e56  ldfld    int32 System.Xml.Xsl.Xslt.Output::MethodPrec
0x21e5b  ldloc.3
0x21e5c  bgt      loc_21EEB
0x21e61  ldarg.0
0x21e62  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltLoader::compiler
0x21e67  callvirt instance void System.Xml.Xsl.Xslt.Compiler::EnterForwardsCompatible()
0x21e6c  ldarg.0
0x21e6d  ldarg.0
0x21e6e  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21e73  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_Value()
0x21e78  ldloca.s 0xB
0x21e7a  call     instance class [System.Xml]System.Xml.XmlQualifiedName System.Xml.Xsl.Xslt.XsltLoader::ParseOutputMethod(string attValue, [out] valuetype [System.Xml]System.Xml.XmlOutputMethod& method)
0x21e7f  stloc.s  0xC
0x21e81  ldarg.0
0x21e82  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltLoader::compiler
0x21e87  ldarg.0
0x21e88  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21e8d  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::get_ForwardCompatibility()
0x21e92  callvirt instance bool System.Xml.Xsl.Xslt.Compiler::ExitForwardsCompatible(bool fwdCompat)
0x21e97  brfalse.s loc_21EEB
0x21e99  ldloc.s  0xC
0x21e9b  ldnull
0x21e9c  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Inequality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x21ea1  brfalse.s loc_21EEB
0x21ea3  ldloc.3
0x21ea4  ldloc.1
0x21ea5  ldfld    int32 System.Xml.Xsl.Xslt.Output::MethodPrec
0x21eaa  bne.un.s loc_21ED4
0x21eac  ldloc.1
0x21ead  ldfld    class [System.Xml]System.Xml.XmlQualifiedName System.Xml.Xsl.Xslt.Output::Method
0x21eb2  ldloc.s  0xC
0x21eb4  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x21eb9  brtrue.s loc_21ED4
0x21ebb  ldarg.0
0x21ebc  ldstr    aXsltAttributer// "Xslt_AttributeRedefinition"
0x21ec1  ldc.i4.1
0x21ec2  newarr   [mscorlib]System.String
0x21ec7  dup
0x21ec8  ldc.i4.0
0x21ec9  ldstr    aMethod// "method"
0x21ece  stelem.ref
0x21ecf  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportWarning(string res, string[] args)
0x21ed4  ldloc.2
0x21ed5  ldloc.s  0xB
0x21ed7  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OutputMethod(valuetype [System.Xml]System.Xml.XmlOutputMethod)
0x21edc  ldloc.1
0x21edd  ldloc.s  0xC
0x21edf  stfld    class [System.Xml]System.Xml.XmlQualifiedName System.Xml.Xsl.Xslt.Output::Method
0x21ee4  ldloc.1
0x21ee5  ldloc.3
0x21ee6  stfld    int32 System.Xml.Xsl.Xslt.Output::MethodPrec
0x21eeb  ldarg.0
0x21eec  ldc.i4.2
0x21eed  ldstr    aByteOrderMark// "byte-order-mark"
0x21ef2  call     instance valuetype [System.Xml]System.Xml.TriState System.Xml.Xsl.Xslt.XsltLoader::ParseYesNoAttribute(int32 attNum, string attName)
0x21ef7  stloc.s  6
0x21ef9  ldloc.s  6
0x21efb  ldc.i4.m1
0x21efc  beq.s    loc_21F09
0x21efe  ldarg.0
0x21eff  ldstr    aXslOutputByteO// "xsl:output/@byte-order-mark"
0x21f04  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportNYI(string arg)
0x21f09  ldarg.0
0x21f0a  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21f0f  ldc.i4.3
0x21f10  ldstr    aCdataSectionEl// "cdata-section-elements"
0x21f15  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToXsltAttribute(int32 attNum, string attName)
0x21f1a  brfalse.s loc_21F8B
0x21f1c  ldarg.0
0x21f1d  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltLoader::compiler
0x21f22  callvirt instance void System.Xml.Xsl.Xslt.Compiler::EnterForwardsCompatible()
0x21f27  ldarg.0
0x21f28  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21f2d  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_Value()
0x21f32  call     string[] [System.Xml]System.Xml.XmlConvert::SplitString(string)
0x21f37  stloc.s  0xD
0x21f39  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Xml]System.Xml.XmlQualifiedName>::.ctor()
0x21f3e  stloc.s  0xE
0x21f40  ldc.i4.0
0x21f41  stloc.s  0xF
0x21f43  br.s     loc_21F5E
0x21f45  ldloc.s  0xE
0x21f47  ldarg.0
0x21f48  ldc.i4.0
0x21f49  ldloc.s  0xD
0x21f4b  ldloc.s  0xF
0x21f4d  ldelem.ref
0x21f4e  call     instance class [System.Xml]System.Xml.XmlQualifiedName System.Xml.Xsl.Xslt.XsltLoader::ResolveQName(bool ignoreDefaultNs, string qname)
0x21f53  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Xml]System.Xml.XmlQualifiedName>::Add(var<u1>)
0x21f58  ldloc.s  0xF
0x21f5a  ldc.i4.1
0x21f5b  add
0x21f5c  stloc.s  0xF
0x21f5e  ldloc.s  0xF
0x21f60  ldloc.s  0xD
0x21f62  ldlen
0x21f63  conv.i4
0x21f64  blt.s    loc_21F45
0x21f66  ldarg.0
0x21f67  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltLoader::compiler
0x21f6c  ldarg.0
0x21f6d  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21f72  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::get_ForwardCompatibility()
0x21f77  callvirt instance bool System.Xml.Xsl.Xslt.Compiler::ExitForwardsCompatible(bool fwdCompat)
0x21f7c  brfalse.s loc_21F8B
0x21f7e  ldloc.2
0x21f7f  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [System.Xml]System.Xml.XmlQualifiedName> [System.Xml]System.Xml.XmlWriterSettings::get_CDataSectionElements()
0x21f84  ldloc.s  0xE
0x21f86  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Xml]System.Xml.XmlQualifiedName>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x21f8b  ldarg.0
0x21f8c  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21f91  ldc.i4.4
0x21f92  ldstr    aDoctypePublic// "doctype-public"
0x21f97  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToXsltAttribute(int32 attNum, string attName)
0x21f9c  brfalse.s loc_21FF9
0x21f9e  ldloc.1
0x21f9f  ldfld    int32 System.Xml.Xsl.Xslt.Output::DocTypePublicPrec
0x21fa4  ldloc.3
0x21fa5  bgt.s    loc_21FF9
0x21fa7  ldloc.3
0x21fa8  ldloc.1
0x21fa9  ldfld    int32 System.Xml.Xsl.Xslt.Output::DocTypePublicPrec
0x21fae  bne.un.s loc_21FE1
0x21fb0  ldloc.2
0x21fb1  callvirt instance string [System.Xml]System.Xml.XmlWriterSettings::get_DocTypePublic()
0x21fb6  ldarg.0
0x21fb7  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21fbc  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_Value()
0x21fc1  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x21fc6  brfalse.s loc_21FE1
0x21fc8  ldarg.0
0x21fc9  ldstr    aXsltAttributer// "Xslt_AttributeRedefinition"
0x21fce  ldc.i4.1
0x21fcf  newarr   [mscorlib]System.String
0x21fd4  dup
0x21fd5  ldc.i4.0
0x21fd6  ldstr    aDoctypePublic// "doctype-public"
0x21fdb  stelem.ref
0x21fdc  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportWarning(string res, string[] args)
0x21fe1  ldloc.2
0x21fe2  ldarg.0
0x21fe3  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21fe8  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_Value()
0x21fed  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_DocTypePublic(string)
0x21ff2  ldloc.1
0x21ff3  ldloc.3
0x21ff4  stfld    int32 System.Xml.Xsl.Xslt.Output::DocTypePublicPrec
0x21ff9  ldarg.0
0x21ffa  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x21fff  ldc.i4.5
0x22000  ldstr    aDoctypeSystem// "doctype-system"
0x22005  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToXsltAttribute(int32 attNum, string attName)
0x2200a  brfalse.s loc_22067
0x2200c  ldloc.1
0x2200d  ldfld    int32 System.Xml.Xsl.Xslt.Output::DocTypeSystemPrec
0x22012  ldloc.3
0x22013  bgt.s    loc_22067
0x22015  ldloc.3
0x22016  ldloc.1
0x22017  ldfld    int32 System.Xml.Xsl.Xslt.Output::DocTypeSystemPrec
0x2201c  bne.un.s loc_2204F
0x2201e  ldloc.2
0x2201f  callvirt instance string [System.Xml]System.Xml.XmlWriterSettings::get_DocTypeSystem()
0x22024  ldarg.0
0x22025  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2202a  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_Value()
0x2202f  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x22034  brfalse.s loc_2204F
0x22036  ldarg.0
0x22037  ldstr    aXsltAttributer// "Xslt_AttributeRedefinition"
0x2203c  ldc.i4.1
0x2203d  newarr   [mscorlib]System.String
0x22042  dup
0x22043  ldc.i4.0
0x22044  ldstr    aDoctypeSystem// "doctype-system"
0x22049  stelem.ref
0x2204a  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportWarning(string res, string[] args)
0x2204f  ldloc.2
0x22050  ldarg.0
0x22051  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x22056  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_Value()
0x2205b  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_DocTypeSystem(string)
0x22060  ldloc.1
0x22061  ldloc.3
0x22062  stfld    int32 System.Xml.Xsl.Xslt.Output::DocTypeSystemPrec
0x22067  ldarg.0
0x22068  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2206d  ldc.i4.6
0x2206e  ldstr    aEncoding_0// "encoding"
0x22073  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToXsltAttribute(int32 attNum, string attName)
0x22078  brfalse  loc_22126
0x2207d  ldloc.1
0x2207e  ldfld    int32 System.Xml.Xsl.Xslt.Output::EncodingPrec
0x22083  ldloc.3
0x22084  bgt      loc_22126
0x22089  ldarg.0
0x2208a  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2208f  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_Value()
0x22094  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::GetEncoding(string)
0x22099  stloc.s  0x10
0x2209b  ldloc.3
0x2209c  ldloc.1
0x2209d  ldfld    int32 System.Xml.Xsl.Xslt.Output::EncodingPrec
0x220a2  bne.un.s loc_220D5
0x220a4  ldloc.1
0x220a5  ldfld    string System.Xml.Xsl.Xslt.Output::Encoding
0x220aa  ldarg.0
0x220ab  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x220b0  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_Value()
0x220b5  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x220ba  brfalse.s loc_220D5
0x220bc  ldarg.0
0x220bd  ldstr    aXsltAttributer// "Xslt_AttributeRedefinition"
0x220c2  ldc.i4.1
0x220c3  newarr   [mscorlib]System.String
0x220c8  dup
0x220c9  ldc.i4.0
0x220ca  ldstr    aEncoding_0// "encoding"
0x220cf  stelem.ref
0x220d0  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportWarning(string res, string[] args)
0x220d5  ldloc.2
0x220d6  ldloc.s  0x10
0x220d8  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_Encoding(class [mscorlib]System.Text.Encoding)
0x220dd  ldloc.1
0x220de  ldarg.0
0x220df  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x220e4  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_Value()
0x220e9  stfld    string System.Xml.Xsl.Xslt.Output::Encoding
0x220ee  ldloc.1
0x220ef  ldloc.3
0x220f0  stfld    int32 System.Xml.Xsl.Xslt.Output::EncodingPrec
0x220f5  leave.s  loc_22126
0x220f7  pop
0x220f8  ldarg.0
0x220f9  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x220fe  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::get_ForwardCompatibility()
0x22103  brtrue.s loc_22124
0x22105  ldarg.0
0x22106  ldstr    aXsltInvalidenc// "Xslt_InvalidEncoding"
0x2210b  ldc.i4.1
0x2210c  newarr   [mscorlib]System.String
0x22111  dup
0x22112  ldc.i4.0
0x22113  ldarg.0
0x22114  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x22119  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_Value()
0x2211e  stelem.ref
0x2211f  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportWarning(string res, string[] args)
0x22124  leave.s  loc_22126
0x22126  ldarg.0
0x22127  ldc.i4.7
0x22128  ldstr    aEscapeUriAttri// "escape-uri-attributes"
0x2212d  call     instance valuetype [System.Xml]System.Xml.TriState System.Xml.Xsl.Xslt.XsltLoader::ParseYesNoAttribute(int32 attNum, string attName)
0x22132  ldc.i4.0
0x22133  cgt.un
0x22135  stloc.s  7
0x22137  ldloc.s  7
0x22139  brtrue.s loc_22146
0x2213b  ldarg.0
0x2213c  ldstr    aXslOutputEscap// "xsl:output/@escape-uri-attributes == fl"...
0x22141  call     instance void System.Xml.Xsl.Xslt.XsltLoader::ReportNYI(string arg)
0x22146  ldarg.0
0x22147  ldc.i4.8
0x22148  ldstr    aIncludeContent// "include-content-type"
0x2214d  call     instance valuetype [System.Xml]System.Xml.TriState System.Xml.Xsl.Xslt.XsltLoader::ParseYesNoAttribute(int32 attNum, string attName)
  ... truncated ...
```
