# System.Xml.Xsl.Xslt.QilGenerator::Compile

- ea: `0x16300`
- end: `0x16593`
- name: `System.Xml.Xsl.Xslt.QilGenerator::Compile`
- size: `659`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: `registry_config, broker_com_uri`

## callers

- `0x160e0`

## callees

- `0x3a60`
- `0x3ad0`
- `0x162d0`
- `0x16300`
- `0x165f0`
- `0x167a0`
- `0x16b70`
- `0x17130`
- `0x197f0`
- `0x198c0`
- `0x19a80`
- `0x19b80`
- `0x1c180`
- `0x1c290`
- `0x1e320`
- `0x1f350`
- `0x1f3b0`
- `0x1f7b0`
- `0x2b5d0`
- `0x35d40`
- `0x35d90`
- `0x35dd0`
- `0x35e00`
- `0x35e20`
- `0x35e50`
- `0x35e80`
- `0x36ec0`
- `0x37790`
- `0x379a0`
- `0x379b0`
- `0x37a00`
- `0x37ab0`
- `0x37ac0`
- `0x37ad0`
- `0x37ae0`
- `0x3b550`

## pseudocode

```c

```

## disassembly

```asm
0x16300  ldarg.0
0x16301  ldarg.1
0x16302  stfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.QilGenerator::compiler
0x16307  ldarg.0
0x16308  ldarg.0
0x16309  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1630e  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilPatternFactory::FunctionList()
0x16313  stfld    class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.QilGenerator::functions
0x16318  ldarg.0
0x16319  ldarg.0
0x1631a  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1631f  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilPatternFactory::GlobalParameterList()
0x16324  stfld    class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.QilGenerator::extPars
0x16329  ldarg.0
0x1632a  ldarg.0
0x1632b  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x16330  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilPatternFactory::GlobalVariableList()
0x16335  stfld    class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.QilGenerator::gloVars
0x1633a  ldarg.0
0x1633b  ldarg.0
0x1633c  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x16341  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilPatternFactory::GlobalVariableList()
0x16346  stfld    class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.QilGenerator::nsVars
0x1634b  ldarg.1
0x1634c  ldfld    class System.Xml.Xsl.Xslt.Scripts System.Xml.Xsl.Xslt.Compiler::Scripts
0x16351  callvirt instance void System.Xml.Xsl.Xslt.Scripts::CompileScripts()
0x16356  newobj   instance void System.Xml.Xsl.Xslt.XslAstRewriter::.ctor()
0x1635b  ldarg.1
0x1635c  call     instance void System.Xml.Xsl.Xslt.XslAstRewriter::Rewrite(class System.Xml.Xsl.Xslt.Compiler compiler)
0x16361  ldarg.0
0x16362  call     instance bool System.Xml.Xsl.Xslt.QilGenerator::get_IsDebug()
0x16367  brtrue.s loc_16375
0x16369  newobj   instance void System.Xml.Xsl.Xslt.XslAstAnalyzer::.ctor()
0x1636e  ldarg.1
0x1636f  call     instance valuetype System.Xml.Xsl.XslFlags System.Xml.Xsl.Xslt.XslAstAnalyzer::Analyze(class System.Xml.Xsl.Xslt.Compiler compiler)
0x16374  pop
0x16375  ldarg.0
0x16376  call     instance void System.Xml.Xsl.Xslt.QilGenerator::CreateGlobalVarPars()
0x1637b  ldarg.0
0x1637c  call     instance void System.Xml.Xsl.Xslt.QilGenerator::CompileKeys()
0x16381  ldarg.0
0x16382  ldarg.1
0x16383  ldfld    class System.Xml.Xsl.Xslt.RootLevel System.Xml.Xsl.Xslt.Compiler::Root
0x16388  ldfld    class System.Xml.Xsl.Xslt.Stylesheet[] System.Xml.Xsl.Xslt.StylesheetLevel::Imports
0x1638d  ldc.i4.0
0x1638e  ldelem.ref
0x1638f  call     instance void System.Xml.Xsl.Xslt.QilGenerator::CompileAndSortMatches(class System.Xml.Xsl.Xslt.Stylesheet sheet)
0x16394  ldarg.0
0x16395  call     instance void System.Xml.Xsl.Xslt.QilGenerator::PrecompileProtoTemplatesHeaders()
0x1639a  ldarg.0
0x1639b  call     instance void System.Xml.Xsl.Xslt.QilGenerator::CompileGlobalVariables()
0x163a0  ldarg.1
0x163a1  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ProtoTemplate> System.Xml.Xsl.Xslt.Compiler::AllTemplates
0x163a6  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ProtoTemplate>::GetEnumerator()
0x163ab  stloc.s  4
0x163ad  br.s     loc_163C0
0x163af  ldloca.s 4
0x163b1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Xslt.ProtoTemplate>::get_Current()
0x163b6  stloc.s  5
0x163b8  ldarg.0
0x163b9  ldloc.s  5
0x163bb  call     instance void System.Xml.Xsl.Xslt.QilGenerator::CompileProtoTemplate(class System.Xml.Xsl.Xslt.ProtoTemplate tmpl)
0x163c0  ldloca.s 4
0x163c2  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Xslt.ProtoTemplate>::MoveNext()
0x163c7  brtrue.s loc_163AF
0x163c9  leave.s  loc_163D9
0x163cb  ldloca.s 4
0x163cd  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Xslt.ProtoTemplate>
0x163d3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x163d8  endfinally
0x163d9  leave.s  loc_16411
0x163db  stloc.s  6
0x163dd  ldloc.s  6
0x163df  ldarg.0
0x163e0  ldfld    class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.QilGenerator::lastScope
0x163e5  ldfld    class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Xslt.XslNode::SourceLine
0x163ea  callvirt instance void System.Xml.Xsl.XslLoadException::SetSourceLineInfo(class System.Xml.Xsl.ISourceLineInfo lineInfo)
0x163ef  rethrow
0x163f1  stloc.s  7
0x163f3  ldloc.s  7
0x163f5  call     bool [System.Xml]System.Xml.XmlException::IsCatchableException(class [mscorlib]System.Exception)
0x163fa  brtrue.s loc_163FE
0x163fc  rethrow
0x163fe  ldloc.s  7
0x16400  ldarg.0
0x16401  ldfld    class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.QilGenerator::lastScope
0x16406  ldfld    class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Xslt.XslNode::SourceLine
0x1640b  newobj   instance void System.Xml.Xsl.XslLoadException::.ctor(class [mscorlib]System.Exception inner, class System.Xml.Xsl.ISourceLineInfo lineInfo)
0x16410  throw
0x16411  ldarg.0
0x16412  call     instance void System.Xml.Xsl.Xslt.QilGenerator::CompileInitializationCode()
0x16417  ldarg.0
0x16418  ldarg.1
0x16419  ldfld    class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.Compiler::StartApplyTemplates
0x1641e  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileRootExpression(class System.Xml.Xsl.Xslt.XslNode applyTmpls)
0x16423  stloc.0
0x16424  ldarg.1
0x16425  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ProtoTemplate> System.Xml.Xsl.Xslt.Compiler::AllTemplates
0x1642a  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ProtoTemplate>::GetEnumerator()
0x1642f  stloc.s  8
0x16431  br.s     loc_1649A
0x16433  ldloca.s 8
0x16435  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Xslt.ProtoTemplate>::get_Current()
0x1643a  stloc.s  9
0x1643c  ldloc.s  9
0x1643e  ldfld    class System.Xml.Xsl.Qil.QilFunction System.Xml.Xsl.Xslt.ProtoTemplate::Function
0x16443  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilFunction::get_Arguments()
0x16448  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xml.Xsl.Qil.QilNode> System.Xml.Xsl.Qil.QilNode::GetEnumerator()
0x1644d  stloc.s  0xA
0x1644f  br.s     loc_16483
0x16451  ldloc.s  0xA
0x16453  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xml.Xsl.Qil.QilNode>::get_Current()
0x16458  castclass System.Xml.Xsl.Qil.QilParameter
0x1645d  stloc.s  0xB
0x1645f  ldarg.0
0x16460  call     instance bool System.Xml.Xsl.Xslt.QilGenerator::get_IsDebug()
0x16465  brfalse.s loc_1647B
0x16467  ldloc.s  0xB
0x16469  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilParameter::get_Name()
0x1646e  ldarg.0
0x1646f  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.QilGenerator::nameNamespaces
0x16474  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x16479  brfalse.s loc_16483
0x1647b  ldloc.s  0xB
0x1647d  ldnull
0x1647e  callvirt instance void System.Xml.Xsl.Qil.QilParameter::set_DefaultValue(class System.Xml.Xsl.Qil.QilNode value)
0x16483  ldloc.s  0xA
0x16485  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1648a  brtrue.s loc_16451
0x1648c  leave.s  loc_1649A
0x1648e  ldloc.s  0xA
0x16490  brfalse.s loc_16499
0x16492  ldloc.s  0xA
0x16494  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16499  endfinally
0x1649a  ldloca.s 8
0x1649c  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Xslt.ProtoTemplate>::MoveNext()
0x164a1  brtrue.s loc_16433
0x164a3  leave.s  loc_164B3
0x164a5  ldloca.s 8
0x164a7  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Xslt.ProtoTemplate>
0x164ad  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x164b2  endfinally
0x164b3  ldarg.1
0x164b4  ldfld    class System.Xml.Xsl.Xslt.Scripts System.Xml.Xsl.Xslt.Compiler::Scripts
0x164b9  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type> System.Xml.Xsl.Xslt.Scripts::get_ScriptClasses()
0x164be  stloc.1
0x164bf  ldloc.1
0x164c0  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type>::get_Count()
0x164c5  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Runtime.EarlyBoundInfo>::.ctor(int32)
0x164ca  stloc.2
0x164cb  ldloc.1
0x164cc  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type>::GetEnumerator()
0x164d1  stloc.s  0xC
0x164d3  br.s     loc_16506
0x164d5  ldloca.s 0xC
0x164d7  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [mscorlib]System.Type>::get_Current()
0x164dc  stloc.s  0xD
0x164de  ldloca.s 0xD
0x164e0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Type>::get_Value()
0x164e5  ldnull
0x164e6  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x164eb  brfalse.s loc_16506
0x164ed  ldloc.2
0x164ee  ldloca.s 0xD
0x164f0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Type>::get_Key()
0x164f5  ldloca.s 0xD
0x164f7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Type>::get_Value()
0x164fc  newobj   instance void System.Xml.Xsl.Runtime.EarlyBoundInfo::.ctor(string namespaceUri, class [mscorlib]System.Type ebType)
0x16501  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Runtime.EarlyBoundInfo>::Add(var<u1>)
0x16506  ldloca.s 0xC
0x16508  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [mscorlib]System.Type>::MoveNext()
0x1650d  brtrue.s loc_164D5
0x1650f  leave.s  loc_1651F
0x16511  ldloca.s 0xC
0x16513  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [mscorlib]System.Type>
0x16519  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1651e  endfinally
0x1651f  ldarg.0
0x16520  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x16525  ldloc.0
0x16526  ldarg.0
0x16527  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1652c  callvirt instance class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilPatternFactory::get_BaseFactory()
0x16531  callvirt instance class System.Xml.Xsl.Qil.QilExpression System.Xml.Xsl.Qil.QilPatternFactory::QilExpression(class System.Xml.Xsl.Qil.QilNode root, class System.Xml.Xsl.Qil.QilFactory factory)
0x16536  stloc.3
0x16537  ldloc.3
0x16538  ldloc.2
0x16539  callvirt instance void System.Xml.Xsl.Qil.QilExpression::set_EarlyBoundTypes(class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Runtime.EarlyBoundInfo> value)
0x1653e  ldloc.3
0x1653f  ldarg.0
0x16540  ldfld    class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.QilGenerator::functions
0x16545  callvirt instance void System.Xml.Xsl.Qil.QilExpression::set_FunctionList(class System.Xml.Xsl.Qil.QilList value)
0x1654a  ldloc.3
0x1654b  ldarg.0
0x1654c  ldfld    class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.QilGenerator::extPars
0x16551  callvirt instance void System.Xml.Xsl.Qil.QilExpression::set_GlobalParameterList(class System.Xml.Xsl.Qil.QilList value)
0x16556  ldloc.3
0x16557  ldarg.0
0x16558  ldfld    class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.QilGenerator::gloVars
0x1655d  callvirt instance void System.Xml.Xsl.Qil.QilExpression::set_GlobalVariableList(class System.Xml.Xsl.Qil.QilList value)
0x16562  ldloc.3
0x16563  ldarg.1
0x16564  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.WhitespaceRule> System.Xml.Xsl.Xslt.Compiler::WhitespaceRules
0x16569  callvirt instance void System.Xml.Xsl.Qil.QilExpression::set_WhitespaceRules(class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.WhitespaceRule> value)
0x1656e  ldloc.3
0x1656f  ldarg.0
0x16570  call     instance bool System.Xml.Xsl.Xslt.QilGenerator::get_IsDebug()
0x16575  callvirt instance void System.Xml.Xsl.Qil.QilExpression::set_IsDebug(bool value)
0x1657a  ldloc.3
0x1657b  ldarg.1
0x1657c  ldfld    class System.Xml.Xsl.Xslt.Output System.Xml.Xsl.Xslt.Compiler::Output
0x16581  ldfld    class [System.Xml]System.Xml.XmlWriterSettings System.Xml.Xsl.Xslt.Output::Settings
0x16586  callvirt instance void System.Xml.Xsl.Qil.QilExpression::set_DefaultWriterSettings(class [System.Xml]System.Xml.XmlWriterSettings value)
0x1658b  ldloc.3
0x1658c  call     void System.Xml.Xsl.Qil.QilDepthChecker::Check(class System.Xml.Xsl.Qil.QilNode input)
0x16591  ldloc.3
0x16592  ret
```
