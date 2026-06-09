# System.Xml.Xsl.XsltOld.ContainerAction::AddScript

- ea: `0x81c0`
- end: `0x8340`
- name: `System.Xml.Xsl.XsltOld.ContainerAction::AddScript`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x79c0`

## callees

- `0x5af0`
- `0x6030`
- `0x6600`
- `0x81c0`
- `0xa8a0`
- `0xa8e0`
- `0xa8f0`
- `0xa910`
- `0xa930`
- `0xa950`
- `0xa980`
- `0xa9a0`
- `0xa9b0`
- `0xa9c0`
- `0xc1b0`

## string_xrefs

- `0x830d`: `Xslt_ScriptEmpty`

## pseudocode

```c

```

## disassembly

```asm
0x81c0  ldarg.1
0x81c1  callvirt instance class System.Xml.Xsl.XsltOld.NavigatorInput System.Xml.Xsl.XsltOld.Compiler::get_Input()
0x81c6  stloc.0
0x81c7  ldc.i4.0
0x81c8  stloc.1
0x81c9  ldnull
0x81ca  stloc.2
0x81cb  ldloc.0
0x81cc  callvirt instance bool System.Xml.Xsl.XsltOld.NavigatorInput::MoveToFirstAttribute()
0x81d1  brfalse  loc_82DA
0x81d6  ldloc.0
0x81d7  callvirt instance string System.Xml.Xsl.XsltOld.NavigatorInput::get_LocalName()
0x81dc  ldloc.0
0x81dd  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x81e2  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::Language
0x81e7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x81ec  brfalse  loc_8273
0x81f1  ldloc.0
0x81f2  callvirt instance string System.Xml.Xsl.XsltOld.NavigatorInput::get_Value()
0x81f7  stloc.3
0x81f8  ldloc.3
0x81f9  ldstr    aJscript// "jscript"
0x81fe  ldc.i4.5
0x81ff  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x8204  brfalse.s loc_8214
0x8206  ldloc.3
0x8207  ldstr    aJavascript// "javascript"
0x820c  ldc.i4.5
0x820d  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x8212  brtrue.s loc_821B
0x8214  ldc.i4.0
0x8215  stloc.1
0x8216  br       loc_82C8
0x821b  ldloc.3
0x821c  ldstr    aC// "c#"
0x8221  ldc.i4.5
0x8222  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x8227  brfalse.s loc_8237
0x8229  ldloc.3
0x822a  ldstr    aCsharp// "csharp"
0x822f  ldc.i4.5
0x8230  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x8235  brtrue.s loc_823E
0x8237  ldc.i4.2
0x8238  stloc.1
0x8239  br       loc_82C8
0x823e  ldloc.3
0x823f  ldstr    aVb// "vb"
0x8244  ldc.i4.5
0x8245  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x824a  brfalse.s loc_825A
0x824c  ldloc.3
0x824d  ldstr    aVisualbasic// "visualbasic"
0x8252  ldc.i4.5
0x8253  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x8258  brtrue.s loc_825E
0x825a  ldc.i4.1
0x825b  stloc.1
0x825c  br.s     loc_82C8
0x825e  ldstr    aXsltScriptinva// "Xslt_ScriptInvalidLanguage"
0x8263  ldc.i4.1
0x8264  newarr   [mscorlib]System.String
0x8269  dup
0x826a  ldc.i4.0
0x826b  ldloc.3
0x826c  stelem.ref
0x826d  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x8272  throw
0x8273  ldloc.0
0x8274  callvirt instance string System.Xml.Xsl.XsltOld.NavigatorInput::get_LocalName()
0x8279  ldloc.0
0x827a  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x827f  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::ImplementsPrefix
0x8284  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8289  brfalse.s loc_82C8
0x828b  ldloc.0
0x828c  callvirt instance string System.Xml.Xsl.XsltOld.NavigatorInput::get_Value()
0x8291  call     bool System.Xml.Xsl.XsltOld.PrefixQName::ValidatePrefix(string prefix)
0x8296  brtrue.s loc_82BB
0x8298  ldstr    aXsltInvalidatt_0// "Xslt_InvalidAttrValue"
0x829d  ldc.i4.2
0x829e  newarr   [mscorlib]System.String
0x82a3  dup
0x82a4  ldc.i4.0
0x82a5  ldloc.0
0x82a6  callvirt instance string System.Xml.Xsl.XsltOld.NavigatorInput::get_LocalName()
0x82ab  stelem.ref
0x82ac  dup
0x82ad  ldc.i4.1
0x82ae  ldloc.0
0x82af  callvirt instance string System.Xml.Xsl.XsltOld.NavigatorInput::get_Value()
0x82b4  stelem.ref
0x82b5  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x82ba  throw
0x82bb  ldarg.1
0x82bc  ldloc.0
0x82bd  callvirt instance string System.Xml.Xsl.XsltOld.NavigatorInput::get_Value()
0x82c2  callvirt instance string System.Xml.Xsl.XsltOld.Compiler::ResolveXmlNamespace(string prefix)
0x82c7  stloc.2
0x82c8  ldloc.0
0x82c9  callvirt instance bool System.Xml.Xsl.XsltOld.NavigatorInput::MoveToNextAttribute()
0x82ce  brtrue   loc_81D6
0x82d3  ldloc.0
0x82d4  callvirt instance bool System.Xml.Xsl.XsltOld.NavigatorInput::ToParent()
0x82d9  pop
0x82da  ldloc.2
0x82db  brtrue.s loc_82FC
0x82dd  ldstr    aXsltMissingatt// "Xslt_MissingAttribute"
0x82e2  ldc.i4.1
0x82e3  newarr   [mscorlib]System.String
0x82e8  dup
0x82e9  ldc.i4.0
0x82ea  ldloc.0
0x82eb  callvirt instance class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::get_Atoms()
0x82f0  ldfld    string System.Xml.Xsl.Xslt.KeywordsTable::ImplementsPrefix
0x82f5  stelem.ref
0x82f6  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x82fb  throw
0x82fc  ldloc.0
0x82fd  callvirt instance bool System.Xml.Xsl.XsltOld.NavigatorInput::Recurse()
0x8302  brfalse.s loc_830D
0x8304  ldloc.0
0x8305  callvirt instance valuetype [System.Xml]System.Xml.XPath.XPathNodeType System.Xml.Xsl.XsltOld.NavigatorInput::get_NodeType()
0x830a  ldc.i4.4
0x830b  beq.s    loc_831E
0x830d  ldstr    aXsltScriptempt// "Xslt_ScriptEmpty"
0x8312  ldc.i4.0
0x8313  newarr   [mscorlib]System.String
0x8318  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x831d  throw
0x831e  ldarg.1
0x831f  ldloc.0
0x8320  callvirt instance string System.Xml.Xsl.XsltOld.NavigatorInput::get_Value()
0x8325  ldloc.1
0x8326  ldloc.2
0x8327  ldloc.0
0x8328  callvirt instance string System.Xml.Xsl.XsltOld.NavigatorInput::get_BaseURI()
0x832d  ldloc.0
0x832e  callvirt instance int32 System.Xml.Xsl.XsltOld.NavigatorInput::get_LineNumber()
0x8333  callvirt instance void System.Xml.Xsl.XsltOld.Compiler::AddScript(string source, valuetype System.Xml.Xsl.XsltOld.ScriptingLanguage lang, string ns, string fileName, int32 lineNumber)
0x8338  ldloc.0
0x8339  callvirt instance bool System.Xml.Xsl.XsltOld.NavigatorInput::ToParent()
0x833e  pop
0x833f  ret
```
