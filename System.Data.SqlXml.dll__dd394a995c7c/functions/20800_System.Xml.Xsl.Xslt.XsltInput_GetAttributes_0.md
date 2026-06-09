# System.Xml.Xsl.Xslt.XsltInput::GetAttributes_0

- ea: `0x20800`
- end: `0x20bbd`
- name: `System.Xml.Xsl.Xslt.XsltInput::GetAttributes_0`
- size: `957`
- prototype: ``
- caller_count: `31`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x207f0`
- `0x21890`
- `0x21c10`
- `0x21ca0`
- `0x21d30`
- `0x21d90`
- `0x21df0`
- `0x22530`
- `0x22670`
- `0x229b0`
- `0x22b10`
- `0x22ce0`
- `0x22ee0`
- `0x23220`
- `0x23300`
- `0x239e0`
- `0x23a40`
- `0x23a80`
- `0x23b20`
- `0x23bb0`
- `0x23db0`
- `0x23e10`
- `0x23e80`
- `0x24010`
- `0x24140`
- `0x24330`
- `0x243d0`
- `0x24430`
- `0x24500`
- `0x245c0`
- `0x24690`

## callees

- `0x13b60`
- `0x13b70`
- `0x1f8c0`
- `0x1f960`
- `0x20540`
- `0x20550`
- `0x20620`
- `0x20630`
- `0x20650`
- `0x206d0`
- `0x20710`
- `0x20770`
- `0x20800`
- `0x20dd0`
- `0x20ef0`
- `0x20f20`
- `0x21100`
- `0x21160`
- `0x56d90`

## pseudocode

```c

```

## disassembly

```asm
0x20800  ldarg.0
0x20801  ldarg.1
0x20802  stfld    valuetype XsltAttribute[] System.Xml.Xsl.Xslt.XsltInput::attributes
0x20807  ldarg.0
0x20808  ldfld    valuetype Record[] System.Xml.Xsl.Xslt.XsltInput::records
0x2080d  ldc.i4.0
0x2080e  ldelema  Record
0x20813  ldnull
0x20814  stfld    string Record::value
0x20819  ldc.i4.0
0x2081a  stloc.0
0x2081b  ldc.i4.0
0x2081c  stloc.1
0x2081d  ldc.i4.0
0x2081e  stloc.2
0x2081f  ldc.i4.0
0x20820  stloc.3
0x20821  ldc.i4.0
0x20822  stloc.s  4
0x20824  ldarg.0
0x20825  call     instance bool System.Xml.Xsl.Xslt.XsltInput::IsXsltNamespace()
0x2082a  brfalse.s loc_2083F
0x2082c  ldarg.0
0x2082d  ldarg.0
0x2082e  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltInput::atoms
0x20833  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Output
0x20838  call     instance bool System.Xml.Xsl.Xslt.XsltInput::IsKeyword(string kwd)
0x2083d  br.s     loc_20840
0x2083f  ldc.i4.0
0x20840  stloc.s  5
0x20842  ldarg.0
0x20843  call     instance bool System.Xml.Xsl.Xslt.XsltInput::IsXsltNamespace()
0x20848  brfalse.s loc_20873
0x2084a  ldarg.0
0x2084b  ldarg.0
0x2084c  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltInput::atoms
0x20851  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Stylesheet
0x20856  call     instance bool System.Xml.Xsl.Xslt.XsltInput::IsKeyword(string kwd)
0x2085b  brtrue.s loc_20870
0x2085d  ldarg.0
0x2085e  ldarg.0
0x2085f  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltInput::atoms
0x20864  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Transform
0x20869  call     instance bool System.Xml.Xsl.Xslt.XsltInput::IsKeyword(string kwd)
0x2086e  br.s     loc_20874
0x20870  ldc.i4.1
0x20871  br.s     loc_20874
0x20873  ldc.i4.0
0x20874  stloc.s  6
0x20876  ldarg.0
0x20877  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltInput::compiler
0x2087c  ldfld    int32 System.Xml.Xsl.Xslt.Compiler::Version
0x20881  ldc.i4.2
0x20882  ceq
0x20884  stloc.s  7
0x20886  ldc.i4.0
0x20887  stloc.s  9
0x20889  br.s     loc_2089B
0x2088b  ldarg.0
0x2088c  ldfld    int32[] System.Xml.Xsl.Xslt.XsltInput::xsltAttributeNumber
0x20891  ldloc.s  9
0x20893  ldc.i4.0
0x20894  stelem.i4
0x20895  ldloc.s  9
0x20897  ldc.i4.1
0x20898  add
0x20899  stloc.s  9
0x2089b  ldloc.s  9
0x2089d  ldarg.1
0x2089e  ldlen
0x2089f  conv.i4
0x208a0  blt.s    loc_2088B
0x208a2  ldarg.0
0x208a3  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltInput::compiler
0x208a8  callvirt instance void System.Xml.Xsl.Xslt.Compiler::EnterForwardsCompatible()
0x208ad  ldloc.s  6
0x208af  brtrue.s loc_208B9
0x208b1  ldloc.s  7
0x208b3  brfalse.s loc_208F3
0x208b5  ldloc.s  5
0x208b7  brtrue.s loc_208F3
0x208b9  ldc.i4.1
0x208ba  stloc.s  0xA
0x208bc  br.s     loc_208E9
0x208be  ldarg.0
0x208bf  call     instance bool System.Xml.Xsl.Xslt.XsltInput::IsNullNamespace()
0x208c4  brfalse.s loc_208E3
0x208c6  ldarg.0
0x208c7  ldarg.0
0x208c8  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltInput::atoms
0x208cd  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Version
0x208d2  call     instance bool System.Xml.Xsl.Xslt.XsltInput::IsKeyword(string kwd)
0x208d7  brfalse.s loc_208E3
0x208d9  ldarg.0
0x208da  ldloc.s  0xA
0x208dc  call     instance void System.Xml.Xsl.Xslt.XsltInput::SetVersion(int32 attVersion)
0x208e1  br.s     loc_208F3
0x208e3  ldloc.s  0xA
0x208e5  ldc.i4.1
0x208e6  add
0x208e7  stloc.s  0xA
0x208e9  ldarg.0
0x208ea  ldloc.s  0xA
0x208ec  call     instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToAttributeBase(int32 attNum)
0x208f1  brtrue.s loc_208BE
0x208f3  ldarg.0
0x208f4  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltInput::compiler
0x208f9  ldfld    int32 System.Xml.Xsl.Xslt.Compiler::Version
0x208fe  brtrue.s loc_2090F
0x20900  ldarg.0
0x20901  ldc.r8   1.0
0x2090a  call     instance void System.Xml.Xsl.Xslt.XsltInput::SetVersion(float64 version)
0x2090f  ldarg.0
0x20910  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltInput::compiler
0x20915  ldfld    int32 System.Xml.Xsl.Xslt.Compiler::Version
0x2091a  ldc.i4.2
0x2091b  ceq
0x2091d  stloc.s  7
0x2091f  ldloc.s  7
0x20921  brtrue.s loc_20930
0x20923  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Opt
0x20928  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V1Req
0x2092d  or
0x2092e  br.s     loc_2093B
0x20930  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Opt
0x20935  ldsfld   int32 System.Xml.Xsl.Xslt.XsltLoader::V2Req
0x2093a  or
0x2093b  stloc.s  8
0x2093d  ldc.i4.1
0x2093e  stloc.s  0xB
0x20940  br       loc_20AB6
0x20945  ldarg.0
0x20946  call     instance bool System.Xml.Xsl.Xslt.XsltInput::IsNullNamespace()
0x2094b  brfalse  loc_20A7A
0x20950  ldarg.0
0x20951  call     instance string System.Xml.Xsl.Xslt.XsltInput::get_LocalName()
0x20956  stloc.s  0xC
0x20958  ldc.i4.0
0x20959  stloc.s  0xD
0x2095b  br.s     loc_20998
0x2095d  ldloc.s  0xC
0x2095f  ldarg.1
0x20960  ldloc.s  0xD
0x20962  ldelema  XsltAttribute
0x20967  ldfld    string XsltAttribute::name
0x2096c  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x20971  brfalse.s loc_20992
0x20973  ldarg.1
0x20974  ldloc.s  0xD
0x20976  ldelema  XsltAttribute
0x2097b  ldfld    int32 XsltAttribute::flags
0x20980  ldloc.s  8
0x20982  and
0x20983  brfalse.s loc_20992
0x20985  ldarg.0
0x20986  ldfld    int32[] System.Xml.Xsl.Xslt.XsltInput::xsltAttributeNumber
0x2098b  ldloc.s  0xD
0x2098d  ldloc.s  0xB
0x2098f  stelem.i4
0x20990  br.s     loc_2099F
0x20992  ldloc.s  0xD
0x20994  ldc.i4.1
0x20995  add
0x20996  stloc.s  0xD
0x20998  ldloc.s  0xD
0x2099a  ldarg.1
0x2099b  ldlen
0x2099c  conv.i4
0x2099d  blt.s    loc_2095D
0x2099f  ldloc.s  0xD
0x209a1  ldarg.1
0x209a2  ldlen
0x209a3  conv.i4
0x209a4  bne.un   loc_20AB0
0x209a9  ldloc.s  0xC
0x209ab  ldarg.0
0x209ac  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltInput::atoms
0x209b1  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::ExcludeResultPrefixes
0x209b6  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x209bb  brfalse.s loc_209CC
0x209bd  ldloc.s  6
0x209bf  ldloc.s  7
0x209c1  or
0x209c2  brfalse.s loc_209CC
0x209c4  ldloc.s  0xB
0x209c6  stloc.1
0x209c7  br       loc_20AB0
0x209cc  ldloc.s  0xC
0x209ce  ldarg.0
0x209cf  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltInput::atoms
0x209d4  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::ExtensionElementPrefixes
0x209d9  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x209de  brfalse.s loc_209EF
0x209e0  ldloc.s  6
0x209e2  ldloc.s  7
0x209e4  or
0x209e5  brfalse.s loc_209EF
0x209e7  ldloc.s  0xB
0x209e9  stloc.0
0x209ea  br       loc_20AB0
0x209ef  ldloc.s  0xC
0x209f1  ldarg.0
0x209f2  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltInput::atoms
0x209f7  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::XPathDefaultNamespace
0x209fc  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x20a01  ldloc.s  7
0x20a03  and
0x20a04  brfalse.s loc_20A0E
0x20a06  ldloc.s  0xB
0x20a08  stloc.2
0x20a09  br       loc_20AB0
0x20a0e  ldloc.s  0xC
0x20a10  ldarg.0
0x20a11  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltInput::atoms
0x20a16  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::DefaultCollation
0x20a1b  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x20a20  ldloc.s  7
0x20a22  and
0x20a23  brfalse.s loc_20A2D
0x20a25  ldloc.s  0xB
0x20a27  stloc.3
0x20a28  br       loc_20AB0
0x20a2d  ldloc.s  0xC
0x20a2f  ldarg.0
0x20a30  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltInput::atoms
0x20a35  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::UseWhen
0x20a3a  call     bool [System.Xml]System.Xml.Ref::Equal(string, string)
0x20a3f  ldloc.s  7
0x20a41  and
0x20a42  brfalse.s loc_20A4A
0x20a44  ldloc.s  0xB
0x20a46  stloc.s  4
0x20a48  br.s     loc_20AB0
0x20a4a  ldarg.0
0x20a4b  ldstr    aXsltInvalidatt// "Xslt_InvalidAttribute"
0x20a50  ldc.i4.2
0x20a51  newarr   [mscorlib]System.String
0x20a56  dup
0x20a57  ldc.i4.0
0x20a58  ldarg.0
0x20a59  call     instance string System.Xml.Xsl.Xslt.XsltInput::get_QualifiedName()
0x20a5e  stelem.ref
0x20a5f  dup
0x20a60  ldc.i4.1
0x20a61  ldarg.0
0x20a62  ldfld    valuetype Record[] System.Xml.Xsl.Xslt.XsltInput::records
0x20a67  ldc.i4.0
0x20a68  ldelema  Record
0x20a6d  call     instance string Record::get_QualifiedName()
0x20a72  stelem.ref
0x20a73  call     instance void System.Xml.Xsl.Xslt.XsltInput::ReportError(string res, string[] args)
0x20a78  br.s     loc_20AB0
0x20a7a  ldarg.0
0x20a7b  call     instance bool System.Xml.Xsl.Xslt.XsltInput::IsXsltNamespace()
0x20a80  brfalse.s loc_20AB0
0x20a82  ldarg.0
0x20a83  ldstr    aXsltInvalidatt// "Xslt_InvalidAttribute"
0x20a88  ldc.i4.2
0x20a89  newarr   [mscorlib]System.String
0x20a8e  dup
0x20a8f  ldc.i4.0
0x20a90  ldarg.0
0x20a91  call     instance string System.Xml.Xsl.Xslt.XsltInput::get_QualifiedName()
0x20a96  stelem.ref
0x20a97  dup
0x20a98  ldc.i4.1
0x20a99  ldarg.0
0x20a9a  ldfld    valuetype Record[] System.Xml.Xsl.Xslt.XsltInput::records
0x20a9f  ldc.i4.0
0x20aa0  ldelema  Record
0x20aa5  call     instance string Record::get_QualifiedName()
0x20aaa  stelem.ref
0x20aab  call     instance void System.Xml.Xsl.Xslt.XsltInput::ReportError(string res, string[] args)
0x20ab0  ldloc.s  0xB
0x20ab2  ldc.i4.1
0x20ab3  add
0x20ab4  stloc.s  0xB
0x20ab6  ldarg.0
0x20ab7  ldloc.s  0xB
0x20ab9  call     instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToAttributeBase(int32 attNum)
0x20abe  brtrue   loc_20945
0x20ac3  ldarg.0
0x20ac4  ldc.i4.1
0x20ac5  stfld    bool System.Xml.Xsl.Xslt.XsltInput::attributesRead
0x20aca  ldarg.0
0x20acb  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltInput::compiler
0x20ad0  ldarg.0
0x20ad1  call     instance bool System.Xml.Xsl.Xslt.XsltInput::get_ForwardCompatibility()
0x20ad6  callvirt instance bool System.Xml.Xsl.Xslt.Compiler::ExitForwardsCompatible(bool fwdCompat)
0x20adb  pop
0x20adc  ldarg.0
0x20add  ldloc.0
0x20ade  ldarg.0
0x20adf  ldfld    class ContextInfo System.Xml.Xsl.Xslt.XsltInput::ctxInfo
0x20ae4  ldc.i4.1
0x20ae5  call     instance void System.Xml.Xsl.Xslt.XsltInput::InsertExNamespaces(int32 attExPrefixes, class ContextInfo ctxInfo, bool extensions)
0x20aea  ldarg.0
0x20aeb  ldloc.1
0x20aec  ldarg.0
0x20aed  ldfld    class ContextInfo System.Xml.Xsl.Xslt.XsltInput::ctxInfo
  ... truncated ...
```
