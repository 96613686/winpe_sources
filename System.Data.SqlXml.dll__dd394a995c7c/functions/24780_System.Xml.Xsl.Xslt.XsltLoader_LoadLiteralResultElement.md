# System.Xml.Xsl.Xslt.XsltLoader::LoadLiteralResultElement

- ea: `0x24780`
- end: `0x248c4`
- name: `System.Xml.Xsl.Xslt.XsltLoader::LoadLiteralResultElement`
- size: `324`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config`

## callers

- `0x21800`
- `0x23380`

## callees

- `0x1e1e0`
- `0x1e1f0`
- `0x1e200`
- `0x1e2e0`
- `0x1f8c0`
- `0x1f8e0`
- `0x1f900`
- `0x1f920`
- `0x20570`
- `0x20620`
- `0x20630`
- `0x206c0`
- `0x206f0`
- `0x20bc0`
- `0x23370`
- `0x24780`
- `0x24940`
- `0x24950`
- `0x24a10`
- `0x25080`
- `0x254b0`
- `0x254e0`

## pseudocode

```c

```

## disassembly

```asm
0x24780  ldarg.0
0x24781  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24786  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_Prefix()
0x2478b  stloc.0
0x2478c  ldarg.0
0x2478d  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24792  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_LocalName()
0x24797  stloc.1
0x24798  ldarg.0
0x24799  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2479e  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_NamespaceUri()
0x247a3  stloc.2
0x247a4  ldarg.0
0x247a5  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x247aa  ldarg.1
0x247ab  callvirt instance class ContextInfo System.Xml.Xsl.Xslt.XsltInput::GetLiteralAttributes(bool asStylesheet)
0x247b0  stloc.3
0x247b1  ldarg.0
0x247b2  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x247b7  ldloc.2
0x247b8  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsExtensionNamespace(string uri)
0x247bd  brfalse.s loc_247D2
0x247bf  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.AstFactory::List()
0x247c4  ldarg.0
0x247c5  ldloc.1
0x247c6  call     instance class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XsltLoader::LoadFallbacks(string instrName)
0x247cb  ldloc.3
0x247cc  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::SetInfo(class System.Xml.Xsl.Xslt.XslNode to, class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content, class ContextInfo info)
0x247d1  ret
0x247d2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode>::.ctor()
0x247d7  stloc.s  4
0x247d9  ldc.i4.1
0x247da  stloc.s  5
0x247dc  br.s     loc_24811
0x247de  ldarg.0
0x247df  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x247e4  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsXsltNamespace()
0x247e9  brfalse.s loc_2480B
0x247eb  ldarg.0
0x247ec  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x247f1  ldarg.0
0x247f2  ldfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.Xslt.XsltLoader::atoms
0x247f7  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::UseAttributeSets
0x247fc  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsKeyword(string kwd)
0x24801  brfalse.s loc_2480B
0x24803  ldarg.0
0x24804  ldloc.s  4
0x24806  call     instance void System.Xml.Xsl.Xslt.XsltLoader::AddUseAttributeSets(class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> list)
0x2480b  ldloc.s  5
0x2480d  ldc.i4.1
0x2480e  add
0x2480f  stloc.s  5
0x24811  ldarg.0
0x24812  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24817  ldloc.s  5
0x24819  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToLiteralAttribute(int32 attNum)
0x2481e  brtrue.s loc_247DE
0x24820  ldc.i4.1
0x24821  stloc.s  6
0x24823  br.s     loc_2488F
0x24825  ldarg.0
0x24826  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2482b  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::IsXsltNamespace()
0x24830  brtrue.s loc_24889
0x24832  ldarg.0
0x24833  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24838  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_LocalName()
0x2483d  ldarg.0
0x2483e  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24843  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_NamespaceUri()
0x24848  ldarg.0
0x24849  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2484e  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_Prefix()
0x24853  call     class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.AstFactory::QName(string local, string uri, string prefix)
0x24858  ldarg.0
0x24859  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2485e  callvirt instance string System.Xml.Xsl.Xslt.XsltInput::get_Value()
0x24863  ldarg.0
0x24864  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24869  callvirt instance valuetype System.Xml.Xsl.Xslt.XslVersion System.Xml.Xsl.Xslt.XsltInput::get_XslVersion()
0x2486e  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.AstFactory::LiteralAttribute(class System.Xml.Xsl.Qil.QilName name, string value, valuetype System.Xml.Xsl.Xslt.XslVersion xslVer)
0x24873  stloc.s  7
0x24875  ldloc.s  4
0x24877  ldloc.s  7
0x24879  ldloc.3
0x2487a  ldfld    class System.Xml.Xsl.ISourceLineInfo ContextInfo::lineInfo
0x2487f  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::SetLineInfo(class System.Xml.Xsl.Xslt.XslNode node, class System.Xml.Xsl.ISourceLineInfo lineInfo)
0x24884  call     void System.Xml.Xsl.Xslt.XsltLoader::AddInstruction(class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content, class System.Xml.Xsl.Xslt.XslNode instruction)
0x24889  ldloc.s  6
0x2488b  ldc.i4.1
0x2488c  add
0x2488d  stloc.s  6
0x2488f  ldarg.0
0x24890  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x24895  ldloc.s  6
0x24897  callvirt instance bool System.Xml.Xsl.Xslt.XsltInput::MoveToLiteralAttribute(int32 attNum)
0x2489c  brtrue.s loc_24825
0x2489e  ldarg.0
0x2489f  ldarg.0
0x248a0  ldloc.s  4
0x248a2  call     instance class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XsltLoader::LoadInstructions(class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content)
0x248a7  call     instance class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XsltLoader::LoadEndTag(class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content)
0x248ac  stloc.s  4
0x248ae  ldloc.1
0x248af  ldloc.2
0x248b0  ldloc.0
0x248b1  call     class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.AstFactory::QName(string local, string uri, string prefix)
0x248b6  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.AstFactory::LiteralElement(class System.Xml.Xsl.Qil.QilName name)
0x248bb  ldloc.s  4
0x248bd  ldloc.3
0x248be  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::SetInfo(class System.Xml.Xsl.Xslt.XslNode to, class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content, class ContextInfo info)
0x248c3  ret
```
