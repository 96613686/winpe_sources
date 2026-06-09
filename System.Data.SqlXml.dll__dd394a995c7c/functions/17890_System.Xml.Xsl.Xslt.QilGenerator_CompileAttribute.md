# System.Xml.Xsl.Xslt.QilGenerator::CompileAttribute

- ea: `0x17890`
- end: `0x179b4`
- name: `System.Xml.Xsl.Xslt.QilGenerator::CompileAttribute`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x17280`

## callees

- `0x139f0`
- `0x13aa0`
- `0x15f90`
- `0x17250`
- `0x17890`
- `0x17b50`
- `0x1a0a0`
- `0x1a680`
- `0x1a6d0`
- `0x1dba0`
- `0x373b0`
- `0x376a0`
- `0x37a50`
- `0x38080`
- `0x382e0`

## string_xrefs

- `0x1791c`: `xmlns`
- `0x1792a`: `xmlns`
- `0x17940`: `Xslt_XmlnsAttr`

## pseudocode

```c

```

## disassembly

```asm
0x17890  ldarg.0
0x17891  ldarg.1
0x17892  ldfld    string System.Xml.Xsl.Xslt.NodeCtor::NsAvt
0x17897  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileStringAvt(string avt)
0x1789c  stloc.0
0x1789d  ldarg.0
0x1789e  ldarg.1
0x1789f  ldfld    string System.Xml.Xsl.Xslt.NodeCtor::NameAvt
0x178a4  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileStringAvt(string avt)
0x178a9  stloc.1
0x178aa  ldc.i4.0
0x178ab  stloc.3
0x178ac  ldloc.1
0x178ad  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x178b2  ldc.i4.s 0x14
0x178b4  bne.un   loc_17971
0x178b9  ldloc.0
0x178ba  brfalse.s loc_178C9
0x178bc  ldloc.0
0x178bd  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x178c2  ldc.i4.s 0x14
0x178c4  bne.un   loc_17971
0x178c9  ldloc.1
0x178ca  castclass System.Xml.Xsl.Qil.QilLiteral
0x178cf  call     string System.Xml.Xsl.Qil.QilLiteral::op_Implicit(class System.Xml.Xsl.Qil.QilLiteral literal)
0x178d4  stloc.s  4
0x178d6  ldarg.0
0x178d7  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.QilGenerator::compiler
0x178dc  ldloc.s  4
0x178de  ldloca.s 5
0x178e0  ldloca.s 6
0x178e2  ldarg.0
0x178e3  callvirt instance bool System.Xml.Xsl.Xslt.Compiler::ParseQName(string qname, [out] string& prefix, [out] string& localName, class System.Xml.Xsl.IErrorHelper errorHelper)
0x178e8  stloc.s  8
0x178ea  ldloc.0
0x178eb  brtrue.s loc_1790B
0x178ed  ldloc.s  8
0x178ef  brtrue.s loc_178FE
0x178f1  ldarg.0
0x178f2  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.QilGenerator::compiler
0x178f7  callvirt instance string System.Xml.Xsl.Xslt.Compiler::CreatePhantomNamespace()
0x178fc  br.s     loc_17907
0x178fe  ldarg.0
0x178ff  ldc.i4.1
0x17900  ldloc.s  5
0x17902  call     instance string System.Xml.Xsl.Xslt.QilGenerator::ResolvePrefix(bool ignoreDefaultNs, string prefix)
0x17907  stloc.s  7
0x17909  br.s     loc_1791A
0x1790b  ldloc.0
0x1790c  castclass System.Xml.Xsl.Qil.QilLiteral
0x17911  call     string System.Xml.Xsl.Qil.QilLiteral::op_Implicit(class System.Xml.Xsl.Qil.QilLiteral literal)
0x17916  stloc.s  7
0x17918  ldc.i4.1
0x17919  stloc.3
0x1791a  ldloc.s  4
0x1791c  ldstr    aXmlns// "xmlns"
0x17921  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17926  brtrue.s loc_1793F
0x17928  ldloc.s  6
0x1792a  ldstr    aXmlns// "xmlns"
0x1792f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17934  brfalse.s loc_1795D
0x17936  ldloc.s  7
0x17938  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1793d  brtrue.s loc_1795D
0x1793f  ldarg.0
0x17940  ldstr    aXsltXmlnsattr// "Xslt_XmlnsAttr"
0x17945  ldc.i4.2
0x17946  newarr   [mscorlib]System.String
0x1794b  dup
0x1794c  ldc.i4.0
0x1794d  ldstr    aName// "name"
0x17952  stelem.ref
0x17953  dup
0x17954  ldc.i4.1
0x17955  ldloc.s  4
0x17957  stelem.ref
0x17958  call     instance void System.Xml.Xsl.Xslt.QilGenerator::ReportError(string res, string[] args)
0x1795d  ldarg.0
0x1795e  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x17963  ldloc.s  6
0x17965  ldloc.s  7
0x17967  ldloc.s  5
0x17969  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilPatternFactory::QName(string local, string uri, string prefix)
0x1796e  stloc.2
0x1796f  br.s     loc_1798D
0x17971  ldloc.0
0x17972  brfalse.s loc_17984
0x17974  ldarg.0
0x17975  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1797a  ldloc.1
0x1797b  ldloc.0
0x1797c  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::StrParseQName(class System.Xml.Xsl.Qil.QilNode str, class System.Xml.Xsl.Qil.QilNode ns)
0x17981  stloc.2
0x17982  br.s     loc_1798D
0x17984  ldarg.0
0x17985  ldc.i4.1
0x17986  ldloc.1
0x17987  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::ResolveQNameDynamic(bool ignoreDefaultNs, class System.Xml.Xsl.Qil.QilNode qilName)
0x1798c  stloc.2
0x1798d  ldloc.3
0x1798e  brfalse.s loc_1799B
0x17990  ldarg.0
0x17991  ldfld    class System.Xml.Xsl.Xslt.OutputScopeManager System.Xml.Xsl.Xslt.QilGenerator::outputScope
0x17996  callvirt instance void System.Xml.Xsl.Xslt.OutputScopeManager::InvalidateNonDefaultPrefixes()
0x1799b  ldarg.0
0x1799c  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x179a1  ldloc.2
0x179a2  ldarg.0
0x179a3  ldarg.1
0x179a4  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XslNode::get_Content()
0x179a9  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileInstructions(class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode> instructions)
0x179ae  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::AttributeCtor(class System.Xml.Xsl.Qil.QilNode name, class System.Xml.Xsl.Qil.QilNode val)
0x179b3  ret
```
