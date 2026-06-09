# System.Xml.Xsl.Qil.QilXmlReader::EndElement

- ea: `0x3bbb0`
- end: `0x3c313`
- name: `System.Xml.Xsl.Qil.QilXmlReader::EndElement`
- size: `1891`
- prototype: ``
- caller_count: `1`
- callee_count: `37`
- tags: `registry_config`

## callers

- `0x3b700`

## callees

- `0x2330`
- `0x35d40`
- `0x35e00`
- `0x35e20`
- `0x35e80`
- `0x35f10`
- `0x35f20`
- `0x35f30`
- `0x35f40`
- `0x35f50`
- `0x35f60`
- `0x35f70`
- `0x35f80`
- `0x36010`
- `0x36030`
- `0x36150`
- `0x361f0`
- `0x36210`
- `0x36230`
- `0x363d0`
- `0x36890`
- `0x36d60`
- `0x374b0`
- `0x375d0`
- `0x376a0`
- `0x376c0`
- `0x376e0`
- `0x376f0`
- `0x37700`
- `0x37710`
- `0x37740`
- `0x37750`
- `0x37760`
- `0x377c0`
- `0x38ce0`
- `0x3bbb0`
- `0x50af0`

## pseudocode

```c

```

## disassembly

```asm
0x3bbb0  ldnull
0x3bbb1  stloc.0
0x3bbb2  ldarg.0
0x3bbb3  ldfld    class [System]System.Collections.Generic.Stack`1<class System.Xml.Xsl.Qil.QilList> System.Xml.Xsl.Qil.QilXmlReader::stk
0x3bbb8  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class System.Xml.Xsl.Qil.QilList>::Pop()
0x3bbbd  stloc.2
0x3bbbe  ldloc.2
0x3bbbf  callvirt instance object System.Xml.Xsl.Qil.QilNode::get_Annotation()
0x3bbc4  castclass ReaderAnnotation
0x3bbc9  stloc.s  4
0x3bbcb  ldarg.0
0x3bbcc  ldfld    class [System.Xml]System.Xml.XmlReader System.Xml.Xsl.Qil.QilXmlReader::r
0x3bbd1  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x3bbd6  stloc.s  5
0x3bbd8  ldarg.0
0x3bbd9  ldfld    class [System.Xml]System.Xml.XmlReader System.Xml.Xsl.Qil.QilXmlReader::r
0x3bbde  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x3bbe3  stloc.s  6
0x3bbe5  ldloc.s  6
0x3bbe7  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x3bbec  stloc.s  7
0x3bbee  ldloc.s  7
0x3bbf0  ldc.i4   0x64CEC188
0x3bbf5  bgt.un   loc_3BC89
0x3bbfa  ldloc.s  7
0x3bbfc  ldc.i4   0x1B6192D7
0x3bc01  bgt.un.s loc_3BC46
0x3bc03  ldloc.s  7
0x3bc05  ldc.i4   0xF7E1B30
0x3bc0a  bgt.un.s loc_3BC29
0x3bc0c  ldloc.s  7
0x3bc0e  ldc.i4   0x45DA515
0x3bc13  beq      loc_3BDC2
0x3bc18  ldloc.s  7
0x3bc1a  ldc.i4   0xF7E1B30
0x3bc1f  beq      loc_3BD6A
0x3bc24  br       loc_3C2A2
0x3bc29  ldloc.s  7
0x3bc2b  ldc.i4   0x1848BBB0
0x3bc30  beq      loc_3BD3E
0x3bc35  ldloc.s  7
0x3bc37  ldc.i4   0x1B6192D7
0x3bc3c  beq      loc_3BD96
0x3bc41  br       loc_3C2A2
0x3bc46  ldloc.s  7
0x3bc48  ldc.i4   0x4A235316
0x3bc4d  bgt.un.s loc_3BC6C
0x3bc4f  ldloc.s  7
0x3bc51  ldc.i4   0x42663901
0x3bc56  beq      loc_3BE46
0x3bc5b  ldloc.s  7
0x3bc5d  ldc.i4   0x4A235316
0x3bc62  beq      loc_3BDD8
0x3bc67  br       loc_3C2A2
0x3bc6c  ldloc.s  7
0x3bc6e  ldc.i4   0x4B7F7829
0x3bc73  beq      loc_3BE1A
0x3bc78  ldloc.s  7
0x3bc7a  ldc.i4   0x64CEC188
0x3bc7f  beq      loc_3BDAC
0x3bc84  br       loc_3C2A2
0x3bc89  ldloc.s  7
0x3bc8b  ldc.i4   0xB2F59B9A
0x3bc90  bgt.un.s loc_3BCCF
0x3bc92  ldloc.s  7
0x3bc94  ldc.i4   0x7E82EE73
0x3bc99  bgt.un.s loc_3BCB2
0x3bc9b  ldloc.s  7
0x3bc9d  ldc.i4   0x7562142F
0x3bca2  beq.s    loc_3BD12
0x3bca4  ldloc.s  7
0x3bca6  ldc.i4   0x7E82EE73
0x3bcab  beq.s    loc_3BD28
0x3bcad  br       loc_3C2A2
0x3bcb2  ldloc.s  7
0x3bcb4  ldc.i4   0x98A79A69
0x3bcb9  beq      loc_3BD80
0x3bcbe  ldloc.s  7
0x3bcc0  ldc.i4   0xB2F59B9A
0x3bcc5  beq      loc_3BD54
0x3bcca  br       loc_3C2A2
0x3bccf  ldloc.s  7
0x3bcd1  ldc.i4   0xE4248F82
0x3bcd6  bgt.un.s loc_3BCF5
0x3bcd8  ldloc.s  7
0x3bcda  ldc.i4   0xD8ED0255
0x3bcdf  beq      loc_3BDEE
0x3bce4  ldloc.s  7
0x3bce6  ldc.i4   0xE4248F82
0x3bceb  beq      loc_3BE04
0x3bcf0  br       loc_3C2A2
0x3bcf5  ldloc.s  7
0x3bcf7  ldc.i4   0xEC1CC8F9
0x3bcfc  beq      loc_3BE5C
0x3bd01  ldloc.s  7
0x3bd03  ldc.i4   0xEEB224C0
0x3bd08  beq      loc_3BE30
0x3bd0d  br       loc_3C2A2
0x3bd12  ldloc.s  6
0x3bd14  ldstr    aQilexpression// "QilExpression"
0x3bd19  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3bd1e  brtrue   loc_3BE72
0x3bd23  br       loc_3C2A2
0x3bd28  ldloc.s  6
0x3bd2a  ldstr    aForwarddecls// "ForwardDecls"
0x3bd2f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3bd34  brtrue   loc_3BF38
0x3bd39  br       loc_3C2A2
0x3bd3e  ldloc.s  6
0x3bd40  ldstr    aParameter// "Parameter"
0x3bd45  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3bd4a  brtrue   loc_3BF40
0x3bd4f  br       loc_3C2A2
0x3bd54  ldloc.s  6
0x3bd56  ldstr    aLet// "Let"
0x3bd5b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3bd60  brtrue   loc_3BF40
0x3bd65  br       loc_3C2A2
0x3bd6a  ldloc.s  6
0x3bd6c  ldstr    aFor_0// "For"
0x3bd71  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3bd76  brtrue   loc_3BF40
0x3bd7b  br       loc_3C2A2
0x3bd80  ldloc.s  6
0x3bd82  ldstr    aFunction_0// "Function"
0x3bd87  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3bd8c  brtrue   loc_3BF40
0x3bd91  br       loc_3C2A2
0x3bd96  ldloc.s  6
0x3bd98  ldstr    aRefto// "RefTo"
0x3bd9d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3bda2  brtrue   loc_3C15D
0x3bda7  br       loc_3C2A2
0x3bdac  ldloc.s  6
0x3bdae  ldstr    aSequence_0// "Sequence"
0x3bdb3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3bdb8  brtrue   loc_3C184
0x3bdbd  br       loc_3C2A2
0x3bdc2  ldloc.s  6
0x3bdc4  ldstr    aFunctionlist// "FunctionList"
0x3bdc9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3bdce  brtrue   loc_3C196
0x3bdd3  br       loc_3C2A2
0x3bdd8  ldloc.s  6
0x3bdda  ldstr    aGlobalvariable// "GlobalVariableList"
0x3bddf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3bde4  brtrue   loc_3C1A8
0x3bde9  br       loc_3C2A2
0x3bdee  ldloc.s  6
0x3bdf0  ldstr    aGlobalparamete// "GlobalParameterList"
0x3bdf5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3bdfa  brtrue   loc_3C1BA
0x3bdff  br       loc_3C2A2
0x3be04  ldloc.s  6
0x3be06  ldstr    aActualparamete// "ActualParameterList"
0x3be0b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3be10  brtrue   loc_3C1CC
0x3be15  br       loc_3C2A2
0x3be1a  ldloc.s  6
0x3be1c  ldstr    aFormalparamete// "FormalParameterList"
0x3be21  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3be26  brtrue   loc_3C1DE
0x3be2b  br       loc_3C2A2
0x3be30  ldloc.s  6
0x3be32  ldstr    aSortkeylist// "SortKeyList"
0x3be37  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3be3c  brtrue   loc_3C1F0
0x3be41  br       loc_3C2A2
0x3be46  ldloc.s  6
0x3be48  ldstr    aBranchlist// "BranchList"
0x3be4d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3be52  brtrue   loc_3C202
0x3be57  br       loc_3C2A2
0x3be5c  ldloc.s  6
0x3be5e  ldstr    aXsltinvokeearl// "XsltInvokeEarlyBound"
0x3be63  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3be68  brtrue   loc_3C214
0x3be6d  br       loc_3C2A2
0x3be72  ldarg.0
0x3be73  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilXmlReader::f
0x3be78  ldloc.2
0x3be79  ldloc.2
0x3be7a  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x3be7f  ldc.i4.1
0x3be80  sub
0x3be81  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x3be86  callvirt instance class System.Xml.Xsl.Qil.QilExpression System.Xml.Xsl.Qil.QilFactory::QilExpression(class System.Xml.Xsl.Qil.QilNode root)
0x3be8b  stloc.s  8
0x3be8d  ldc.i4.0
0x3be8e  stloc.s  9
0x3be90  br       loc_3BF21
0x3be95  ldloc.2
0x3be96  ldloc.s  9
0x3be98  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x3be9d  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x3bea2  stloc.s  0xA
0x3bea4  ldloc.s  0xA
0x3bea6  ldc.i4.1
0x3bea7  sub
0x3bea8  switch   loc_3BEDB, loc_3BEF1, loc_3BF07
0x3beb9  ldloc.s  0xA
0x3bebb  ldc.i4.s 0x12
0x3bebd  sub
0x3bebe  ldc.i4.1
0x3bebf  bgt.un.s loc_3BF1B
0x3bec1  ldloc.s  8
0x3bec3  ldloc.2
0x3bec4  ldloc.s  9
0x3bec6  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x3becb  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x3bed0  ldc.i4.s 0x12
0x3bed2  ceq
0x3bed4  callvirt instance void System.Xml.Xsl.Qil.QilExpression::set_IsDebug(bool value)
0x3bed9  br.s     loc_3BF1B
0x3bedb  ldloc.s  8
0x3bedd  ldloc.2
0x3bede  ldloc.s  9
0x3bee0  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x3bee5  castclass System.Xml.Xsl.Qil.QilList
0x3beea  callvirt instance void System.Xml.Xsl.Qil.QilExpression::set_FunctionList(class System.Xml.Xsl.Qil.QilList value)
0x3beef  br.s     loc_3BF1B
0x3bef1  ldloc.s  8
0x3bef3  ldloc.2
0x3bef4  ldloc.s  9
0x3bef6  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x3befb  castclass System.Xml.Xsl.Qil.QilList
0x3bf00  callvirt instance void System.Xml.Xsl.Qil.QilExpression::set_GlobalVariableList(class System.Xml.Xsl.Qil.QilList value)
0x3bf05  br.s     loc_3BF1B
0x3bf07  ldloc.s  8
0x3bf09  ldloc.2
0x3bf0a  ldloc.s  9
0x3bf0c  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x3bf11  castclass System.Xml.Xsl.Qil.QilList
0x3bf16  callvirt instance void System.Xml.Xsl.Qil.QilExpression::set_GlobalParameterList(class System.Xml.Xsl.Qil.QilList value)
0x3bf1b  ldloc.s  9
0x3bf1d  ldc.i4.1
0x3bf1e  add
0x3bf1f  stloc.s  9
0x3bf21  ldloc.s  9
0x3bf23  ldloc.2
0x3bf24  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x3bf29  ldc.i4.1
0x3bf2a  sub
0x3bf2b  blt      loc_3BE95
0x3bf30  ldloc.s  8
0x3bf32  stloc.3
0x3bf33  br       loc_3C2F5
0x3bf38  ldarg.0
0x3bf39  ldc.i4.0
0x3bf3a  stfld    bool System.Xml.Xsl.Qil.QilXmlReader::inFwdDecls
0x3bf3f  ret
0x3bf40  ldloc.s  4
0x3bf42  ldfld    string ReaderAnnotation::Id
0x3bf47  stloc.s  0xB
0x3bf49  ldloc.s  4
0x3bf4b  ldfld    class System.Xml.Xsl.Qil.QilName ReaderAnnotation::Name
0x3bf50  stloc.s  0xC
0x3bf52  ldarg.0
0x3bf53  ldfld    class [System.Xml]System.Xml.XmlReader System.Xml.Xsl.Qil.QilXmlReader::r
0x3bf58  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x3bf5d  stloc.s  0xD
0x3bf5f  ldloc.s  0xD
0x3bf61  ldstr    aParameter// "Parameter"
0x3bf66  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3bf6b  brtrue.s loc_3BF91
0x3bf6d  ldloc.s  0xD
0x3bf6f  ldstr    aLet// "Let"
0x3bf74  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3bf79  brtrue.s loc_3BFDD
0x3bf7b  ldloc.s  0xD
0x3bf7d  ldstr    aFor_0// "For"
0x3bf82  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3bf87  brtrue   loc_3C020
0x3bf8c  br       loc_3C035
0x3bf91  ldarg.0
0x3bf92  ldfld    bool System.Xml.Xsl.Qil.QilXmlReader::inFwdDecls
0x3bf97  brtrue.s loc_3BFA1
0x3bf99  ldloc.2
0x3bf9a  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x3bf9f  brtrue.s loc_3BFBC
0x3bfa1  ldarg.0
0x3bfa2  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilXmlReader::f
0x3bfa7  ldnull
0x3bfa8  ldloc.s  0xC
0x3bfaa  ldloc.s  4
0x3bfac  ldfld    class System.Xml.Xsl.XmlQueryType ReaderAnnotation::XmlType
0x3bfb1  callvirt instance class System.Xml.Xsl.Qil.QilParameter System.Xml.Xsl.Qil.QilFactory::Parameter(class System.Xml.Xsl.Qil.QilNode defaultValue, class System.Xml.Xsl.Qil.QilNode name, class System.Xml.Xsl.XmlQueryType xmlType)
0x3bfb6  stloc.3
0x3bfb7  br       loc_3C0A5
0x3bfbc  ldarg.0
0x3bfbd  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilXmlReader::f
0x3bfc2  ldloc.2
0x3bfc3  ldc.i4.0
0x3bfc4  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x3bfc9  ldloc.s  0xC
0x3bfcb  ldloc.s  4
0x3bfcd  ldfld    class System.Xml.Xsl.XmlQueryType ReaderAnnotation::XmlType
0x3bfd2  callvirt instance class System.Xml.Xsl.Qil.QilParameter System.Xml.Xsl.Qil.QilFactory::Parameter(class System.Xml.Xsl.Qil.QilNode defaultValue, class System.Xml.Xsl.Qil.QilNode name, class System.Xml.Xsl.XmlQueryType xmlType)
0x3bfd7  stloc.3
0x3bfd8  br       loc_3C0A5
  ... truncated ...
```
