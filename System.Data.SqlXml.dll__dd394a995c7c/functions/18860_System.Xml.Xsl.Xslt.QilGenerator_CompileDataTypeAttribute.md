# System.Xml.Xsl.Xslt.QilGenerator::CompileDataTypeAttribute

- ea: `0x18860`
- end: `0x18ab1`
- name: `System.Xml.Xsl.Xslt.QilGenerator::CompileDataTypeAttribute`
- size: `593`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18c10`

## callees

- `0x139f0`
- `0x13aa0`
- `0x17b50`
- `0x18860`
- `0x1a0a0`
- `0x1a680`
- `0x1a6d0`
- `0x294a0`
- `0x297d0`
- `0x299c0`
- `0x373b0`
- `0x376a0`
- `0x37720`
- `0x37a00`
- `0x37a20`
- `0x37a40`
- `0x37c50`
- `0x37c90`
- `0x37ca0`
- `0x37de0`
- `0x380a0`
- `0x38120`
- `0x56130`

## pseudocode

```c

```

## disassembly

```asm
0x18860  ldarg.0
0x18861  ldarg.1
0x18862  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileStringAvt(string avt)
0x18867  stloc.0
0x18868  ldloc.0
0x18869  brfalse  loc_18A9D
0x1886e  ldloc.0
0x1886f  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x18874  ldc.i4.s 0x14
0x18876  bne.un   loc_18922
0x1887b  ldloc.0
0x1887c  castclass System.Xml.Xsl.Qil.QilLiteral
0x18881  call     string System.Xml.Xsl.Qil.QilLiteral::op_Implicit(class System.Xml.Xsl.Qil.QilLiteral literal)
0x18886  stloc.1
0x18887  ldloc.1
0x18888  ldstr    aNumber// "number"
0x1888d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18892  brfalse.s loc_188A8
0x18894  ldarg.3
0x18895  ldarg.0
0x18896  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1889b  ldarg.3
0x1889c  ldind.ref
0x1889d  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::ConvertToNumber(class System.Xml.Xsl.Qil.QilNode n)
0x188a2  stind.ref
0x188a3  ldarg.s  4
0x188a5  ldnull
0x188a6  stind.ref
0x188a7  ret
0x188a8  ldloc.1
0x188a9  ldstr    aText// "text"
0x188ae  call     bool [mscorlib]System.String::op_Equality(string, string)
0x188b3  brtrue   loc_18A9D
0x188b8  ldarg.2
0x188b9  brtrue   loc_18A9D
0x188be  ldarg.0
0x188bf  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.QilGenerator::compiler
0x188c4  ldloc.1
0x188c5  ldloca.s 2
0x188c7  ldloca.s 3
0x188c9  ldarg.0
0x188ca  callvirt instance bool System.Xml.Xsl.Xslt.Compiler::ParseQName(string qname, [out] string& prefix, [out] string& localName, class System.Xml.Xsl.IErrorHelper errorHelper)
0x188cf  stloc.s  5
0x188d1  ldloc.s  5
0x188d3  brtrue.s loc_188E2
0x188d5  ldarg.0
0x188d6  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.QilGenerator::compiler
0x188db  callvirt instance string System.Xml.Xsl.Xslt.Compiler::CreatePhantomNamespace()
0x188e0  br.s     loc_188EA
0x188e2  ldarg.0
0x188e3  ldc.i4.1
0x188e4  ldloc.2
0x188e5  call     instance string System.Xml.Xsl.Xslt.QilGenerator::ResolvePrefix(bool ignoreDefaultNs, string prefix)
0x188ea  stloc.s  4
0x188ec  ldloc.s  4
0x188ee  callvirt instance int32 [mscorlib]System.String::get_Length()
0x188f3  pop
0x188f4  ldarg.0
0x188f5  ldstr    aXsltBistateatt// "Xslt_BistateAttribute"
0x188fa  ldc.i4.3
0x188fb  newarr   [mscorlib]System.String
0x18900  dup
0x18901  ldc.i4.0
0x18902  ldstr    aDataType// "data-type"
0x18907  stelem.ref
0x18908  dup
0x18909  ldc.i4.1
0x1890a  ldstr    aText// "text"
0x1890f  stelem.ref
0x18910  dup
0x18911  ldc.i4.2
0x18912  ldstr    aNumber// "number"
0x18917  stelem.ref
0x18918  call     instance void System.Xml.Xsl.Xslt.QilGenerator::ReportError(string res, string[] args)
0x1891d  br       loc_18A9D
0x18922  ldarg.0
0x18923  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x18928  ldarg.0
0x18929  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1892e  ldloc.0
0x1892f  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilPatternFactory::Let(class System.Xml.Xsl.Qil.QilNode binding)
0x18934  dup
0x18935  stloc.s  6
0x18937  ldarg.0
0x18938  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1893d  ldarg.0
0x1893e  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x18943  ldloc.s  6
0x18945  ldarg.0
0x18946  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1894b  ldstr    aNumber// "number"
0x18950  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilPatternFactory::String(string val)
0x18955  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Eq(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x1895a  ldarg.0
0x1895b  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x18960  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::False()
0x18965  ldarg.0
0x18966  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1896b  ldarg.0
0x1896c  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x18971  ldloc.s  6
0x18973  ldarg.0
0x18974  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x18979  ldstr    aText// "text"
0x1897e  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilPatternFactory::String(string val)
0x18983  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Eq(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x18988  ldarg.0
0x18989  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1898e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::True()
0x18993  ldarg.2
0x18994  brtrue.s loc_189F3
0x18996  ldarg.0
0x18997  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1899c  ldarg.0
0x1899d  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x189a2  ldarg.0
0x189a3  ldc.i4.1
0x189a4  ldloc.s  6
0x189a6  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::ResolveQNameDynamic(bool ignoreDefaultNs, class System.Xml.Xsl.Qil.QilNode qilName)
0x189ab  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilPatternFactory::Let(class System.Xml.Xsl.Qil.QilNode binding)
0x189b0  dup
0x189b1  stloc.s  7
0x189b3  ldarg.0
0x189b4  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x189b9  ldarg.0
0x189ba  ldfld    class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.QilGenerator::lastScope
0x189bf  ldfld    class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Xslt.XslNode::SourceLine
0x189c4  ldstr    aXsltBistateatt// "Xslt_BistateAttribute"
0x189c9  ldc.i4.3
0x189ca  newarr   [mscorlib]System.String
0x189cf  dup
0x189d0  ldc.i4.0
0x189d1  ldstr    aDataType// "data-type"
0x189d6  stelem.ref
0x189d7  dup
0x189d8  ldc.i4.1
0x189d9  ldstr    aText// "text"
0x189de  stelem.ref
0x189df  dup
0x189e0  ldc.i4.2
0x189e1  ldstr    aNumber// "number"
0x189e6  stelem.ref
0x189e7  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::Error(class System.Xml.Xsl.ISourceLineInfo lineInfo, string res, string[] args)
0x189ec  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Loop(class System.Xml.Xsl.Qil.QilIterator variable, class System.Xml.Xsl.Qil.QilNode body)
0x189f1  br.s     loc_189FE
0x189f3  ldarg.0
0x189f4  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x189f9  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::True()
0x189fe  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Conditional(class System.Xml.Xsl.Qil.QilNode condition, class System.Xml.Xsl.Qil.QilNode trueBranch, class System.Xml.Xsl.Qil.QilNode falseBranch)
0x18a03  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Conditional(class System.Xml.Xsl.Qil.QilNode condition, class System.Xml.Xsl.Qil.QilNode trueBranch, class System.Xml.Xsl.Qil.QilNode falseBranch)
0x18a08  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Loop(class System.Xml.Xsl.Qil.QilIterator variable, class System.Xml.Xsl.Qil.QilNode body)
0x18a0d  stloc.0
0x18a0e  ldarg.0
0x18a0f  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x18a14  ldloc.0
0x18a15  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilPatternFactory::Let(class System.Xml.Xsl.Qil.QilNode binding)
0x18a1a  stloc.s  8
0x18a1c  ldarg.0
0x18a1d  ldfld    class VariableHelper System.Xml.Xsl.Xslt.QilGenerator::varHelper
0x18a22  ldloc.s  8
0x18a24  callvirt instance void VariableHelper::AddVariable(class System.Xml.Xsl.Qil.QilIterator let)
0x18a29  ldarg.s  4
0x18a2b  ldarg.3
0x18a2c  ldind.ref
0x18a2d  ldarg.0
0x18a2e  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x18a33  callvirt instance class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilPatternFactory::get_BaseFactory()
0x18a38  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::DeepClone(class System.Xml.Xsl.Qil.QilFactory f)
0x18a3d  stind.ref
0x18a3e  ldarg.3
0x18a3f  ldarg.0
0x18a40  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x18a45  ldloc.s  8
0x18a47  ldarg.0
0x18a48  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x18a4d  ldarg.3
0x18a4e  ldind.ref
0x18a4f  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::ConvertToString(class System.Xml.Xsl.Qil.QilNode n)
0x18a54  ldarg.0
0x18a55  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x18a5a  ldsfld   string [mscorlib]System.String::Empty
0x18a5f  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilPatternFactory::String(string val)
0x18a64  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Conditional(class System.Xml.Xsl.Qil.QilNode condition, class System.Xml.Xsl.Qil.QilNode trueBranch, class System.Xml.Xsl.Qil.QilNode falseBranch)
0x18a69  stind.ref
0x18a6a  ldarg.s  4
0x18a6c  ldarg.0
0x18a6d  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x18a72  ldloc.s  8
0x18a74  ldarg.0
0x18a75  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x18a7a  ldc.r8   0.0
0x18a83  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilPatternFactory::Double(float64 val)
0x18a88  ldarg.0
0x18a89  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x18a8e  ldarg.s  4
0x18a90  ldind.ref
0x18a91  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::ConvertToNumber(class System.Xml.Xsl.Qil.QilNode n)
0x18a96  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Conditional(class System.Xml.Xsl.Qil.QilNode condition, class System.Xml.Xsl.Qil.QilNode trueBranch, class System.Xml.Xsl.Qil.QilNode falseBranch)
0x18a9b  stind.ref
0x18a9c  ret
0x18a9d  ldarg.3
0x18a9e  ldarg.0
0x18a9f  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x18aa4  ldarg.3
0x18aa5  ldind.ref
0x18aa6  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::ConvertToString(class System.Xml.Xsl.Qil.QilNode n)
0x18aab  stind.ref
0x18aac  ldarg.s  4
0x18aae  ldnull
0x18aaf  stind.ref
0x18ab0  ret
```
