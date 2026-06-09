# System.Xml.Xsl.XPath.XPathBuilder::BuildAxisFilter

- ea: `0x27680`
- end: `0x27859`
- name: `System.Xml.Xsl.XPath.XPathBuilder::BuildAxisFilter`
- size: `473`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config`

## callers

- `0x27860`

## callees

- `0x1fc0`
- `0x1fe0`
- `0x2be0`
- `0x2c20`
- `0x27660`
- `0x27680`
- `0x37450`
- `0x37460`
- `0x376a0`
- `0x376c0`
- `0x376d0`
- `0x37a20`
- `0x37a60`
- `0x37c40`
- `0x37c90`
- `0x37ce0`
- `0x37ec0`
- `0x380a0`
- `0x38150`
- `0x38360`
- `0x38370`
- `0x38380`
- `0x383b0`

## pseudocode

```c

```

## disassembly

```asm
0x27680  ldarg.1
0x27681  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x27686  callvirt instance valuetype System.Xml.Xsl.XmlNodeKindFlags System.Xml.Xsl.XmlQueryType::get_NodeKinds()
0x2768b  stloc.0
0x2768c  ldloc.0
0x2768d  ldarg.3
0x2768e  ldarg.2
0x2768f  call     valuetype System.Xml.Xsl.XmlNodeKindFlags System.Xml.Xsl.XPath.XPathBuilder::AxisTypeMask(valuetype System.Xml.Xsl.XmlNodeKindFlags inputTypeMask, valuetype [System.Xml]System.Xml.XPath.XPathNodeType nodeType, valuetype System.Xml.Xsl.XPath.XPathAxis xpathAxis)
0x27694  stloc.1
0x27695  ldloc.1
0x27696  brtrue.s loc_276A4
0x27698  ldarg.0
0x27699  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x2769e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Sequence()
0x276a3  ret
0x276a4  ldloc.1
0x276a5  ldloc.0
0x276a6  beq      loc_277B0
0x276ab  ldarg.0
0x276ac  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x276b1  ldarg.0
0x276b2  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x276b7  ldarg.1
0x276b8  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilPatternFactory::For(class System.Xml.Xsl.Qil.QilNode binding)
0x276bd  dup
0x276be  stloc.2
0x276bf  ldarg.0
0x276c0  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x276c5  ldloc.2
0x276c6  ldloc.1
0x276c7  call     class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::NodeChoice(valuetype System.Xml.Xsl.XmlNodeKindFlags kinds)
0x276cc  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::IsType(class System.Xml.Xsl.Qil.QilNode expr, class System.Xml.Xsl.XmlQueryType t)
0x276d1  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Filter(class System.Xml.Xsl.Qil.QilIterator variable, class System.Xml.Xsl.Qil.QilNode expr)
0x276d6  starg.s  1
0x276d8  ldarg.1
0x276d9  ldloc.1
0x276da  call     class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::NodeChoice(valuetype System.Xml.Xsl.XmlNodeKindFlags kinds)
0x276df  ldarg.1
0x276e0  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x276e5  callvirt instance valuetype System.Xml.Xsl.XmlQueryCardinality System.Xml.Xsl.XmlQueryType::get_Cardinality()
0x276ea  call     class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::PrimeProduct(class System.Xml.Xsl.XmlQueryType t, valuetype System.Xml.Xsl.XmlQueryCardinality c)
0x276ef  callvirt instance void System.Xml.Xsl.Qil.QilNode::set_XmlType(class System.Xml.Xsl.XmlQueryType value)
0x276f4  ldarg.1
0x276f5  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x276fa  ldc.i4.s 0x3D
0x276fc  bne.un   loc_277B0
0x27701  ldarg.1
0x27702  castclass System.Xml.Xsl.Qil.QilLoop
0x27707  stloc.3
0x27708  ldloc.3
0x27709  ldarg.0
0x2770a  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x2770f  ldloc.3
0x27710  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilLoop::get_Body()
0x27715  ldarg.s  4
0x27717  brfalse.s loc_2771D
0x27719  ldarg.s  5
0x2771b  brtrue.s loc_2777E
0x2771d  ldarg.s  5
0x2771f  brtrue.s loc_27758
0x27721  ldarg.s  4
0x27723  brtrue.s loc_27732
0x27725  ldarg.0
0x27726  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x2772b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::True()
0x27730  br.s     loc_277A4
0x27732  ldarg.0
0x27733  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27738  ldarg.0
0x27739  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x2773e  ldloc.2
0x2773f  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::LocalNameOf(class System.Xml.Xsl.Qil.QilNode expr)
0x27744  ldarg.0
0x27745  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x2774a  ldarg.s  4
0x2774c  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilPatternFactory::String(string val)
0x27751  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Eq(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x27756  br.s     loc_277A4
0x27758  ldarg.0
0x27759  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x2775e  ldarg.0
0x2775f  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27764  ldloc.2
0x27765  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::NamespaceUriOf(class System.Xml.Xsl.Qil.QilNode expr)
0x2776a  ldarg.0
0x2776b  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27770  ldarg.s  5
0x27772  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilPatternFactory::String(string val)
0x27777  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Eq(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x2777c  br.s     loc_277A4
0x2777e  ldarg.0
0x2777f  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27784  ldarg.0
0x27785  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x2778a  ldloc.2
0x2778b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::NameOf(class System.Xml.Xsl.Qil.QilNode expr)
0x27790  ldarg.0
0x27791  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27796  ldarg.s  4
0x27798  ldarg.s  5
0x2779a  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilPatternFactory::QName(string local, string uri)
0x2779f  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Eq(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x277a4  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::And(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x277a9  callvirt instance void System.Xml.Xsl.Qil.QilLoop::set_Body(class System.Xml.Xsl.Qil.QilNode value)
0x277ae  ldloc.3
0x277af  ret
0x277b0  ldarg.0
0x277b1  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x277b6  ldarg.0
0x277b7  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x277bc  ldarg.1
0x277bd  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilPatternFactory::For(class System.Xml.Xsl.Qil.QilNode binding)
0x277c2  dup
0x277c3  stloc.2
0x277c4  ldarg.s  4
0x277c6  brfalse.s loc_277CC
0x277c8  ldarg.s  5
0x277ca  brtrue.s loc_2782D
0x277cc  ldarg.s  5
0x277ce  brtrue.s loc_27807
0x277d0  ldarg.s  4
0x277d2  brtrue.s loc_277E1
0x277d4  ldarg.0
0x277d5  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x277da  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::True()
0x277df  br.s     loc_27853
0x277e1  ldarg.0
0x277e2  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x277e7  ldarg.0
0x277e8  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x277ed  ldloc.2
0x277ee  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::LocalNameOf(class System.Xml.Xsl.Qil.QilNode expr)
0x277f3  ldarg.0
0x277f4  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x277f9  ldarg.s  4
0x277fb  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilPatternFactory::String(string val)
0x27800  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Eq(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x27805  br.s     loc_27853
0x27807  ldarg.0
0x27808  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x2780d  ldarg.0
0x2780e  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27813  ldloc.2
0x27814  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::NamespaceUriOf(class System.Xml.Xsl.Qil.QilNode expr)
0x27819  ldarg.0
0x2781a  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x2781f  ldarg.s  5
0x27821  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilPatternFactory::String(string val)
0x27826  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Eq(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x2782b  br.s     loc_27853
0x2782d  ldarg.0
0x2782e  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27833  ldarg.0
0x27834  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27839  ldloc.2
0x2783a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::NameOf(class System.Xml.Xsl.Qil.QilNode expr)
0x2783f  ldarg.0
0x27840  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.XPath.XPathBuilder::f
0x27845  ldarg.s  4
0x27847  ldarg.s  5
0x27849  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilPatternFactory::QName(string local, string uri)
0x2784e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Eq(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x27853  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Filter(class System.Xml.Xsl.Qil.QilIterator variable, class System.Xml.Xsl.Qil.QilNode expr)
0x27858  ret
```
