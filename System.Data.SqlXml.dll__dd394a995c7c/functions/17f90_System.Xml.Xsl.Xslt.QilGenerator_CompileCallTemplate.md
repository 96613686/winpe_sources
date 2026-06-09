# System.Xml.Xsl.Xslt.QilGenerator::CompileCallTemplate

- ea: `0x17f90`
- end: `0x18106`
- name: `System.Xml.Xsl.Xslt.QilGenerator::CompileCallTemplate`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x17280`

## callees

- `0x13af0`
- `0x13be0`
- `0x148d0`
- `0x162d0`
- `0x17f90`
- `0x186c0`
- `0x1a1f0`
- `0x1a750`
- `0x1dba0`
- `0x37510`
- `0x37a60`
- `0x37c10`
- `0x37c50`
- `0x37ec0`
- `0x38ce0`
- `0x56120`
- `0x56130`
- `0x56140`

## string_xrefs

- `0x180a1`: `Xslt_InvalidCallTemplate`
- `0x17fff`: `urn:schemas-microsoft-com:xslt-debug`

## pseudocode

```c

```

## disassembly

```asm
0x17f90  ldarg.0
0x17f91  ldfld    class VariableHelper System.Xml.Xsl.Xslt.QilGenerator::varHelper
0x17f96  callvirt instance int32 VariableHelper::StartVariables()
0x17f9b  stloc.0
0x17f9c  ldarg.1
0x17f9d  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XslNode::get_Content()
0x17fa2  stloc.1
0x17fa3  ldloc.1
0x17fa4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Xml.Xsl.Xslt.XslNode>::GetEnumerator()
0x17fa9  stloc.3
0x17faa  br.s     loc_18029
0x17fac  ldloc.3
0x17fad  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xml.Xsl.Xslt.XslNode>::get_Current()
0x17fb2  castclass System.Xml.Xsl.Xslt.VarPar
0x17fb7  stloc.s  4
0x17fb9  ldarg.0
0x17fba  ldloc.s  4
0x17fbc  call     instance void System.Xml.Xsl.Xslt.QilGenerator::CompileWithParam(class System.Xml.Xsl.Xslt.VarPar withParam)
0x17fc1  ldarg.0
0x17fc2  call     instance bool System.Xml.Xsl.Xslt.QilGenerator::get_IsDebug()
0x17fc7  brfalse.s loc_18029
0x17fc9  ldloc.s  4
0x17fcb  ldfld    class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.VarPar::Value
0x17fd0  stloc.s  5
0x17fd2  ldarg.0
0x17fd3  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x17fd8  ldloc.s  5
0x17fda  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilPatternFactory::Let(class System.Xml.Xsl.Qil.QilNode binding)
0x17fdf  stloc.s  6
0x17fe1  ldloc.s  6
0x17fe3  ldarg.0
0x17fe4  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x17fe9  ldstr    aWithParam_0// "with-param "
0x17fee  ldloc.s  4
0x17ff0  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XslNode::Name
0x17ff5  callvirt instance string System.Xml.Xsl.Qil.QilName::get_QualifiedName()
0x17ffa  call     string [mscorlib]System.String::Concat(string, string)
0x17fff  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:xslt-debug"
0x18004  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilPatternFactory::QName(string local, string uri)
0x18009  callvirt instance string [mscorlib]System.Object::ToString()
0x1800e  callvirt instance void System.Xml.Xsl.Qil.QilReference::set_DebugName(string value)
0x18013  ldarg.0
0x18014  ldfld    class VariableHelper System.Xml.Xsl.Xslt.QilGenerator::varHelper
0x18019  ldloc.s  6
0x1801b  callvirt instance void VariableHelper::AddVariable(class System.Xml.Xsl.Qil.QilIterator let)
0x18020  ldloc.s  4
0x18022  ldloc.s  6
0x18024  stfld    class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.VarPar::Value
0x18029  ldloc.3
0x1802a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1802f  brtrue   loc_17FAC
0x18034  leave.s  loc_18040
0x18036  ldloc.3
0x18037  brfalse.s loc_1803F
0x18039  ldloc.3
0x1803a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1803f  endfinally
0x18040  ldarg.0
0x18041  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.QilGenerator::compiler
0x18046  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xml.Xsl.Qil.QilName, class System.Xml.Xsl.Xslt.Template> System.Xml.Xsl.Xslt.Compiler::NamedTemplates
0x1804b  ldarg.1
0x1804c  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XslNode::Name
0x18051  ldloca.s 7
0x18053  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xml.Xsl.Qil.QilName, class System.Xml.Xsl.Xslt.Template>::TryGetValue(var<u1>, !!T0)
0x18058  brfalse.s loc_18082
0x1805a  ldarg.0
0x1805b  ldfld    class System.Xml.Xsl.Xslt.InvokeGenerator System.Xml.Xsl.Xslt.QilGenerator::invkGen
0x18060  ldloc.s  7
0x18062  ldfld    class System.Xml.Xsl.Qil.QilFunction System.Xml.Xsl.Xslt.ProtoTemplate::Function
0x18067  ldarg.0
0x18068  ldarg.1
0x18069  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XslNode::get_Content()
0x1806e  ldloc.s  7
0x18070  ldfld    valuetype System.Xml.Xsl.XslFlags System.Xml.Xsl.Xslt.XslNode::Flags
0x18075  call     instance class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.QilGenerator::AddRemoveImplicitArgs(class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode> args, valuetype System.Xml.Xsl.XslFlags flags)
0x1807a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.InvokeGenerator::GenerateInvoke(class System.Xml.Xsl.Qil.QilFunction func, class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode> actualArgs)
0x1807f  stloc.2
0x18080  br.s     loc_180CB
0x18082  ldarg.0
0x18083  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.QilGenerator::compiler
0x18088  ldarg.1
0x18089  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XslNode::Name
0x1808e  callvirt instance bool System.Xml.Xsl.Xslt.Compiler::IsPhantomName(class System.Xml.Xsl.Qil.QilName qname)
0x18093  brtrue.s loc_180BF
0x18095  ldarg.0
0x18096  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.QilGenerator::compiler
0x1809b  ldarg.1
0x1809c  ldfld    class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Xslt.XslNode::SourceLine
0x180a1  ldstr    aXsltInvalidcal// "Xslt_InvalidCallTemplate"
0x180a6  ldc.i4.1
0x180a7  newarr   [mscorlib]System.String
0x180ac  dup
0x180ad  ldc.i4.0
0x180ae  ldarg.1
0x180af  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XslNode::Name
0x180b4  callvirt instance string System.Xml.Xsl.Qil.QilName::get_QualifiedName()
0x180b9  stelem.ref
0x180ba  callvirt instance void System.Xml.Xsl.Xslt.Compiler::ReportError(class System.Xml.Xsl.ISourceLineInfo lineInfo, string res, string[] args)
0x180bf  ldarg.0
0x180c0  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x180c5  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Sequence()
0x180ca  stloc.2
0x180cb  ldloc.1
0x180cc  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Xslt.XslNode>::get_Count()
0x180d1  ldc.i4.0
0x180d2  ble.s    loc_180E1
0x180d4  ldloc.2
0x180d5  ldarg.1
0x180d6  ldfld    class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Xslt.XslNodeEx::ElemNameLi
0x180db  call     class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::SetLineInfo(class System.Xml.Xsl.Qil.QilNode n, class System.Xml.Xsl.ISourceLineInfo lineInfo)
0x180e0  stloc.2
0x180e1  ldarg.0
0x180e2  ldfld    class VariableHelper System.Xml.Xsl.Xslt.QilGenerator::varHelper
0x180e7  ldloc.2
0x180e8  ldloc.0
0x180e9  callvirt instance class System.Xml.Xsl.Qil.QilNode VariableHelper::FinishVariables(class System.Xml.Xsl.Qil.QilNode node, int32 varScope)
0x180ee  stloc.2
0x180ef  ldarg.0
0x180f0  call     instance bool System.Xml.Xsl.Xslt.QilGenerator::get_IsDebug()
0x180f5  brfalse.s loc_18104
0x180f7  ldarg.0
0x180f8  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x180fd  ldloc.2
0x180fe  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Nop(class System.Xml.Xsl.Qil.QilNode child)
0x18103  ret
0x18104  ldloc.2
0x18105  ret
```
