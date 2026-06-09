# System.Xml.Xsl.Xslt.QilGenerator::CompileProtoTemplate

- ea: `0x17130`
- end: `0x1722a`
- name: `System.Xml.Xsl.Xslt.QilGenerator::CompileProtoTemplate`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x16300`

## callees

- `0x145b0`
- `0x14620`
- `0x162d0`
- `0x167e0`
- `0x16810`
- `0x17130`
- `0x17250`
- `0x18600`
- `0x1a7c0`
- `0x1dba0`
- `0x36ec0`
- `0x36ef0`
- `0x374d0`
- `0x37700`
- `0x37790`
- `0x37990`
- `0x379a0`
- `0x379b0`

## string_xrefs

- `0x1718d`: `urn:schemas-microsoft-com:xslt-debug`

## pseudocode

```c

```

## disassembly

```asm
0x17130  ldarg.0
0x17131  ldarg.1
0x17132  call     instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.QilGenerator::EnterScope(class System.Xml.Xsl.Xslt.XslNode node)
0x17137  pop
0x17138  ldarg.0
0x17139  ldflda   valuetype System.Xml.Xsl.Xslt.FunctionFocus System.Xml.Xsl.Xslt.QilGenerator::funcFocus
0x1713e  ldarg.1
0x1713f  ldfld    class System.Xml.Xsl.Qil.QilFunction System.Xml.Xsl.Xslt.ProtoTemplate::Function
0x17144  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilFunction::get_Arguments()
0x17149  ldarg.0
0x1714a  call     instance bool System.Xml.Xsl.Xslt.QilGenerator::get_IsDebug()
0x1714f  brfalse.s loc_17158
0x17151  ldc.i4   0x700
0x17156  br.s     loc_1715E
0x17158  ldarg.1
0x17159  ldfld    valuetype System.Xml.Xsl.XslFlags System.Xml.Xsl.Xslt.XslNode::Flags
0x1715e  call     instance void System.Xml.Xsl.Xslt.FunctionFocus::StartFocus(class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode> args, valuetype System.Xml.Xsl.XslFlags flags)
0x17163  ldarg.1
0x17164  ldfld    class System.Xml.Xsl.Qil.QilFunction System.Xml.Xsl.Xslt.ProtoTemplate::Function
0x17169  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilFunction::get_Arguments()
0x1716e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xml.Xsl.Qil.QilNode> System.Xml.Xsl.Qil.QilNode::GetEnumerator()
0x17173  stloc.0
0x17174  br.s     loc_171ED
0x17176  ldloc.0
0x17177  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xml.Xsl.Qil.QilNode>::get_Current()
0x1717c  castclass System.Xml.Xsl.Qil.QilParameter
0x17181  stloc.1
0x17182  ldloc.1
0x17183  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilParameter::get_Name()
0x17188  callvirt instance string System.Xml.Xsl.Qil.QilName::get_NamespaceUri()
0x1718d  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:xslt-debug"
0x17192  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x17197  brfalse.s loc_171ED
0x17199  ldarg.0
0x1719a  call     instance bool System.Xml.Xsl.Xslt.QilGenerator::get_IsDebug()
0x1719f  brfalse.s loc_171DB
0x171a1  ldloc.1
0x171a2  callvirt instance object System.Xml.Xsl.Qil.QilNode::get_Annotation()
0x171a7  castclass System.Xml.Xsl.Xslt.VarPar
0x171ac  stloc.2
0x171ad  ldarg.0
0x171ae  ldloc.2
0x171af  call     instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.QilGenerator::EnterScope(class System.Xml.Xsl.Xslt.XslNode node)
0x171b4  stloc.3
0x171b5  ldloc.1
0x171b6  ldarg.0
0x171b7  ldloc.2
0x171b8  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileVarParValue(class System.Xml.Xsl.Xslt.XslNode node)
0x171bd  callvirt instance void System.Xml.Xsl.Qil.QilParameter::set_DefaultValue(class System.Xml.Xsl.Qil.QilNode value)
0x171c2  ldarg.0
0x171c3  call     instance void System.Xml.Xsl.Xslt.QilGenerator::ExitScope()
0x171c8  ldloc.1
0x171c9  ldarg.0
0x171ca  ldloc.1
0x171cb  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilParameter::get_DefaultValue()
0x171d0  ldloc.3
0x171d1  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::SetDebugNs(class System.Xml.Xsl.Qil.QilNode n, class System.Xml.Xsl.Qil.QilList nsList)
0x171d6  callvirt instance void System.Xml.Xsl.Qil.QilParameter::set_DefaultValue(class System.Xml.Xsl.Qil.QilNode value)
0x171db  ldarg.0
0x171dc  ldfld    class System.Xml.Xsl.Xslt.CompilerScopeManager`1<class System.Xml.Xsl.Qil.QilIterator> System.Xml.Xsl.Xslt.QilGenerator::scope
0x171e1  ldloc.1
0x171e2  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilParameter::get_Name()
0x171e7  ldloc.1
0x171e8  callvirt instance void class System.Xml.Xsl.Xslt.CompilerScopeManager`1<class System.Xml.Xsl.Qil.QilIterator>::AddVariable(class System.Xml.Xsl.Qil.QilName, var<u1>)
0x171ed  ldloc.0
0x171ee  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x171f3  brtrue.s loc_17176
0x171f5  leave.s  loc_17201
0x171f7  ldloc.0
0x171f8  brfalse.s loc_17200
0x171fa  ldloc.0
0x171fb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17200  endfinally
0x17201  ldarg.1
0x17202  ldfld    class System.Xml.Xsl.Qil.QilFunction System.Xml.Xsl.Xslt.ProtoTemplate::Function
0x17207  ldarg.0
0x17208  ldarg.1
0x17209  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XslNode::get_Content()
0x1720e  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileInstructions(class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode> instructions)
0x17213  callvirt instance void System.Xml.Xsl.Qil.QilFunction::set_Definition(class System.Xml.Xsl.Qil.QilNode value)
0x17218  ldarg.0
0x17219  ldflda   valuetype System.Xml.Xsl.Xslt.FunctionFocus System.Xml.Xsl.Xslt.QilGenerator::funcFocus
0x1721e  call     instance void System.Xml.Xsl.Xslt.FunctionFocus::StopFocus()
0x17223  ldarg.0
0x17224  call     instance void System.Xml.Xsl.Xslt.QilGenerator::ExitScope()
0x17229  ret
```
