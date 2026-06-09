# System.Xml.Xsl.Xslt.QilGenerator::.ctor

- ea: `0x16100`
- end: `0x162c2`
- name: `System.Xml.Xsl.Xslt.QilGenerator::.ctor`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x160e0`

## callees

- `0x2be0`
- `0x144b0`
- `0x146a0`
- `0x148a0`
- `0x15760`
- `0x15de0`
- `0x16060`
- `0x1bf00`
- `0x1cd10`
- `0x1daa0`
- `0x26400`
- `0x26f40`
- `0x35ec0`
- `0x37a00`
- `0x37a60`
- `0x56100`

## string_xrefs

- `0x1623f`: `urn:schemas-microsoft-com:xslt-debug`
- `0x1625a`: `urn:schemas-microsoft-com:xslt-debug`
- `0x16275`: `urn:schemas-microsoft-com:xslt-debug`
- `0x16290`: `urn:schemas-microsoft-com:xslt-debug`
- `0x162ab`: `urn:schemas-microsoft-com:xslt-debug`

## pseudocode

```c

```

## disassembly

```asm
0x16100  ldarg.0
0x16101  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x16106  stfld    class [mscorlib]System.Text.StringBuilder System.Xml.Xsl.Xslt.QilGenerator::unescapedText
0x1610b  ldarg.0
0x1610c  ldc.i4.1
0x1610d  stfld    bool System.Xml.Xsl.Xslt.QilGenerator::allowVariables
0x16112  ldarg.0
0x16113  ldc.i4.1
0x16114  stfld    bool System.Xml.Xsl.Xslt.QilGenerator::allowCurrent
0x16119  ldarg.0
0x1611a  ldc.i4.1
0x1611b  stfld    bool System.Xml.Xsl.Xslt.QilGenerator::allowKey
0x16120  ldarg.0
0x16121  call     instance void [mscorlib]System.Object::.ctor()
0x16126  ldarg.0
0x16127  newobj   instance void class System.Xml.Xsl.Xslt.CompilerScopeManager`1<class System.Xml.Xsl.Qil.QilIterator>::.ctor()
0x1612c  stfld    class System.Xml.Xsl.Xslt.CompilerScopeManager`1<class System.Xml.Xsl.Qil.QilIterator> System.Xml.Xsl.Xslt.QilGenerator::scope
0x16131  ldarg.0
0x16132  newobj   instance void System.Xml.Xsl.Xslt.OutputScopeManager::.ctor()
0x16137  stfld    class System.Xml.Xsl.Xslt.OutputScopeManager System.Xml.Xsl.Xslt.QilGenerator::outputScope
0x1613c  ldarg.0
0x1613d  newobj   instance void [System]System.Collections.Specialized.HybridDictionary::.ctor()
0x16142  stfld    class [System]System.Collections.Specialized.HybridDictionary System.Xml.Xsl.Xslt.QilGenerator::prefixesInUse
0x16147  ldarg.0
0x16148  newobj   instance void System.Xml.Xsl.Qil.QilFactory::.ctor()
0x1614d  ldarg.1
0x1614e  newobj   instance void System.Xml.Xsl.Xslt.XsltQilFactory::.ctor(class System.Xml.Xsl.Qil.QilFactory f, bool debug)
0x16153  stfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x16158  ldarg.0
0x16159  ldarg.0
0x1615a  newobj   instance void System.Xml.Xsl.XPath.XPathBuilder::.ctor(class System.Xml.Xsl.XPath.IXPathEnvironment environment)
0x1615f  stfld    class System.Xml.Xsl.XPath.XPathBuilder System.Xml.Xsl.Xslt.QilGenerator::xpathBuilder
0x16164  ldarg.0
0x16165  newobj   instance void class System.Xml.Xsl.XPath.XPathParser`1<class System.Xml.Xsl.Qil.QilNode>::.ctor()
0x1616a  stfld    class System.Xml.Xsl.XPath.XPathParser`1<class System.Xml.Xsl.Qil.QilNode> System.Xml.Xsl.Xslt.QilGenerator::xpathParser
0x1616f  ldarg.0
0x16170  ldarg.0
0x16171  newobj   instance void System.Xml.Xsl.Xslt.XPathPatternBuilder::.ctor(class System.Xml.Xsl.XPath.IXPathEnvironment environment)
0x16176  stfld    class System.Xml.Xsl.Xslt.XPathPatternBuilder System.Xml.Xsl.Xslt.QilGenerator::ptrnBuilder
0x1617b  ldarg.0
0x1617c  newobj   instance void System.Xml.Xsl.Xslt.XPathPatternParser::.ctor()
0x16181  stfld    class System.Xml.Xsl.Xslt.XPathPatternParser System.Xml.Xsl.Xslt.QilGenerator::ptrnParser
0x16186  ldarg.0
0x16187  ldarg.0
0x16188  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1618d  callvirt instance class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilPatternFactory::get_BaseFactory()
0x16192  newobj   instance void System.Xml.Xsl.Xslt.ReferenceReplacer::.ctor(class System.Xml.Xsl.Qil.QilFactory f)
0x16197  stfld    class System.Xml.Xsl.Xslt.ReferenceReplacer System.Xml.Xsl.Xslt.QilGenerator::refReplacer
0x1619c  ldarg.0
0x1619d  ldarg.0
0x1619e  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x161a3  ldarg.1
0x161a4  newobj   instance void System.Xml.Xsl.Xslt.InvokeGenerator::.ctor(class System.Xml.Xsl.Xslt.XsltQilFactory f, bool debug)
0x161a9  stfld    class System.Xml.Xsl.Xslt.InvokeGenerator System.Xml.Xsl.Xslt.QilGenerator::invkGen
0x161ae  ldarg.0
0x161af  ldarg.0
0x161b0  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x161b5  ldarg.0
0x161b6  ldfld    class System.Xml.Xsl.Xslt.ReferenceReplacer System.Xml.Xsl.Xslt.QilGenerator::refReplacer
0x161bb  ldarg.0
0x161bc  ldfld    class System.Xml.Xsl.Xslt.InvokeGenerator System.Xml.Xsl.Xslt.QilGenerator::invkGen
0x161c1  newobj   instance void System.Xml.Xsl.Xslt.MatcherBuilder::.ctor(class System.Xml.Xsl.XPath.XPathQilFactory f, class System.Xml.Xsl.Xslt.ReferenceReplacer refReplacer, class System.Xml.Xsl.Xslt.InvokeGenerator invkGen)
0x161c6  stfld    class System.Xml.Xsl.Xslt.MatcherBuilder System.Xml.Xsl.Xslt.QilGenerator::matcherBuilder
0x161cb  ldarg.0
0x161cc  ldarg.0
0x161cd  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x161d2  newobj   instance void System.Xml.Xsl.Xslt.SingletonFocus::.ctor(class System.Xml.Xsl.XPath.XPathQilFactory f)
0x161d7  stfld    valuetype System.Xml.Xsl.Xslt.SingletonFocus System.Xml.Xsl.Xslt.QilGenerator::singlFocus
0x161dc  ldarg.0
0x161dd  ldflda   valuetype System.Xml.Xsl.Xslt.FunctionFocus System.Xml.Xsl.Xslt.QilGenerator::funcFocus
0x161e2  initobj  System.Xml.Xsl.Xslt.FunctionFocus
0x161e8  ldarg.0
0x161e9  ldarg.0
0x161ea  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x161ef  newobj   instance void System.Xml.Xsl.Xslt.LoopFocus::.ctor(class System.Xml.Xsl.XPath.XPathQilFactory f)
0x161f4  stfld    valuetype System.Xml.Xsl.Xslt.LoopFocus System.Xml.Xsl.Xslt.QilGenerator::curLoop
0x161f9  ldarg.0
0x161fa  ldarg.0
0x161fb  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x16200  newobj   instance void System.Xml.Xsl.Xslt.QilStrConcatenator::.ctor(class System.Xml.Xsl.XPath.XPathQilFactory f)
0x16205  stfld    class System.Xml.Xsl.Xslt.QilStrConcatenator System.Xml.Xsl.Xslt.QilGenerator::strConcat
0x1620a  ldarg.0
0x1620b  ldarg.0
0x1620c  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x16211  newobj   instance void VariableHelper::.ctor(class System.Xml.Xsl.XPath.XPathQilFactory f)
0x16216  stfld    class VariableHelper System.Xml.Xsl.Xslt.QilGenerator::varHelper
0x1621b  ldarg.0
0x1621c  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::DocumentOrElement
0x16221  stfld    class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Xslt.QilGenerator::elementOrDocumentType
0x16226  ldarg.0
0x16227  ldc.i4.s 0xC
0x16229  call     class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::NodeChoice(valuetype System.Xml.Xsl.XmlNodeKindFlags kinds)
0x1622e  stfld    class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Xslt.QilGenerator::textOrAttributeType
0x16233  ldarg.0
0x16234  ldarg.0
0x16235  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1623a  ldstr    aCurrent// "current"
0x1623f  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:xslt-debug"
0x16244  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilPatternFactory::QName(string local, string uri)
0x16249  stfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.QilGenerator::nameCurrent
0x1624e  ldarg.0
0x1624f  ldarg.0
0x16250  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x16255  ldstr    aPosition// "position"
0x1625a  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:xslt-debug"
0x1625f  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilPatternFactory::QName(string local, string uri)
0x16264  stfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.QilGenerator::namePosition
0x16269  ldarg.0
0x1626a  ldarg.0
0x1626b  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x16270  ldstr    aLast// "last"
0x16275  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:xslt-debug"
0x1627a  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilPatternFactory::QName(string local, string uri)
0x1627f  stfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.QilGenerator::nameLast
0x16284  ldarg.0
0x16285  ldarg.0
0x16286  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1628b  ldstr    aNamespaces// "namespaces"
0x16290  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:xslt-debug"
0x16295  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilPatternFactory::QName(string local, string uri)
0x1629a  stfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.QilGenerator::nameNamespaces
0x1629f  ldarg.0
0x162a0  ldarg.0
0x162a1  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x162a6  ldstr    aInit// "init"
0x162ab  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:xslt-debug"
0x162b0  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilPatternFactory::QName(string local, string uri)
0x162b5  stfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.QilGenerator::nameInit
0x162ba  ldarg.0
0x162bb  ldc.i4.0
0x162bc  stfld    int32 System.Xml.Xsl.Xslt.QilGenerator::formatterCnt
0x162c1  ret
```
