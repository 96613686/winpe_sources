# System.Xml.Xsl.Xslt.QilGenerator::CompileApplyTemplates

- ea: `0x17df0`
- end: `0x17f65`
- name: `System.Xml.Xsl.Xslt.QilGenerator::CompileApplyTemplates`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x17280`

## callees

- `0x146d0`
- `0x147c0`
- `0x147f0`
- `0x162d0`
- `0x17d00`
- `0x17df0`
- `0x186c0`
- `0x18700`
- `0x19d90`
- `0x1a160`
- `0x1a810`
- `0x1db80`
- `0x1dba0`
- `0x37510`
- `0x37a60`
- `0x37c40`
- `0x37c50`
- `0x38ce0`
- `0x56120`
- `0x56130`
- `0x56140`

## string_xrefs

- `0x17e9d`: `urn:schemas-microsoft-com:xslt-debug`

## pseudocode

```c

```

## disassembly

```asm
0x17df0  ldarg.1
0x17df1  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XslNode::get_Content()
0x17df6  stloc.1
0x17df7  ldarg.0
0x17df8  ldfld    class VariableHelper System.Xml.Xsl.Xslt.QilGenerator::varHelper
0x17dfd  callvirt instance int32 VariableHelper::StartVariables()
0x17e02  stloc.2
0x17e03  ldarg.0
0x17e04  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x17e09  ldarg.0
0x17e0a  ldarg.1
0x17e0b  callvirt instance string System.Xml.Xsl.Xslt.XslNode::get_Select()
0x17e10  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileNodeSetExpression(string expr)
0x17e15  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilPatternFactory::Let(class System.Xml.Xsl.Qil.QilNode binding)
0x17e1a  stloc.3
0x17e1b  ldarg.0
0x17e1c  ldfld    class VariableHelper System.Xml.Xsl.Xslt.QilGenerator::varHelper
0x17e21  ldloc.3
0x17e22  callvirt instance void VariableHelper::AddVariable(class System.Xml.Xsl.Qil.QilIterator let)
0x17e27  ldc.i4.0
0x17e28  stloc.s  6
0x17e2a  br       loc_17ECD
0x17e2f  ldloc.1
0x17e30  ldloc.s  6
0x17e32  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode>::get_Item(!!T0)
0x17e37  isinst   System.Xml.Xsl.Xslt.VarPar
0x17e3c  stloc.s  7
0x17e3e  ldloc.s  7
0x17e40  brfalse  loc_17EC7
0x17e45  ldarg.0
0x17e46  ldloc.s  7
0x17e48  call     instance void System.Xml.Xsl.Xslt.QilGenerator::CompileWithParam(class System.Xml.Xsl.Xslt.VarPar withParam)
0x17e4d  ldloc.s  7
0x17e4f  ldfld    class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.VarPar::Value
0x17e54  stloc.s  8
0x17e56  ldarg.0
0x17e57  call     instance bool System.Xml.Xsl.Xslt.QilGenerator::get_IsDebug()
0x17e5c  brtrue.s loc_17E70
0x17e5e  ldloc.s  8
0x17e60  isinst   System.Xml.Xsl.Qil.QilIterator
0x17e65  brtrue.s loc_17EC7
0x17e67  ldloc.s  8
0x17e69  isinst   System.Xml.Xsl.Qil.QilLiteral
0x17e6e  brtrue.s loc_17EC7
0x17e70  ldarg.0
0x17e71  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x17e76  ldloc.s  8
0x17e78  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilPatternFactory::Let(class System.Xml.Xsl.Qil.QilNode binding)
0x17e7d  stloc.s  9
0x17e7f  ldloc.s  9
0x17e81  ldarg.0
0x17e82  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x17e87  ldstr    aWithParam_0// "with-param "
0x17e8c  ldloc.s  7
0x17e8e  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XslNode::Name
0x17e93  callvirt instance string System.Xml.Xsl.Qil.QilName::get_QualifiedName()
0x17e98  call     string [mscorlib]System.String::Concat(string, string)
0x17e9d  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:xslt-debug"
0x17ea2  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilPatternFactory::QName(string local, string uri)
0x17ea7  callvirt instance string [mscorlib]System.Object::ToString()
0x17eac  callvirt instance void System.Xml.Xsl.Qil.QilReference::set_DebugName(string value)
0x17eb1  ldarg.0
0x17eb2  ldfld    class VariableHelper System.Xml.Xsl.Xslt.QilGenerator::varHelper
0x17eb7  ldloc.s  9
0x17eb9  callvirt instance void VariableHelper::AddVariable(class System.Xml.Xsl.Qil.QilIterator let)
0x17ebe  ldloc.s  7
0x17ec0  ldloc.s  9
0x17ec2  stfld    class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.VarPar::Value
0x17ec7  ldloc.s  6
0x17ec9  ldc.i4.1
0x17eca  add
0x17ecb  stloc.s  6
0x17ecd  ldloc.s  6
0x17ecf  ldloc.1
0x17ed0  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Xslt.XslNode>::get_Count()
0x17ed5  blt      loc_17E2F
0x17eda  ldarg.0
0x17edb  ldfld    valuetype System.Xml.Xsl.Xslt.LoopFocus System.Xml.Xsl.Xslt.QilGenerator::curLoop
0x17ee0  stloc.s  4
0x17ee2  ldarg.0
0x17ee3  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x17ee8  ldloc.3
0x17ee9  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilPatternFactory::For(class System.Xml.Xsl.Qil.QilNode binding)
0x17eee  stloc.s  5
0x17ef0  ldarg.0
0x17ef1  ldflda   valuetype System.Xml.Xsl.Xslt.LoopFocus System.Xml.Xsl.Xslt.QilGenerator::curLoop
0x17ef6  ldloc.s  5
0x17ef8  call     instance void System.Xml.Xsl.Xslt.LoopFocus::SetFocus(class System.Xml.Xsl.Qil.QilIterator current)
0x17efd  ldarg.0
0x17efe  ldflda   valuetype System.Xml.Xsl.Xslt.LoopFocus System.Xml.Xsl.Xslt.QilGenerator::curLoop
0x17f03  ldarg.0
0x17f04  ldloc.1
0x17f05  ldloca.s 4
0x17f07  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileSorts(class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode> content, valuetype System.Xml.Xsl.Xslt.LoopFocus& parentLoop)
0x17f0c  call     instance void System.Xml.Xsl.Xslt.LoopFocus::Sort(class System.Xml.Xsl.Qil.QilNode sortKeys)
0x17f11  ldarg.0
0x17f12  ldarg.0
0x17f13  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.QilGenerator::compiler
0x17f18  ldfld    class System.Xml.Xsl.Xslt.RootLevel System.Xml.Xsl.Xslt.Compiler::Root
0x17f1d  ldarg.1
0x17f1e  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::GenerateApply(class System.Xml.Xsl.Xslt.StylesheetLevel sheet, class System.Xml.Xsl.Xslt.XslNode node)
0x17f23  stloc.0
0x17f24  ldarg.0
0x17f25  ldarg.1
0x17f26  ldfld    class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Xslt.XslNodeEx::ElemNameLi
0x17f2b  ldloc.0
0x17f2c  ldarg.1
0x17f2d  ldfld    class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Xslt.XslNodeEx::EndTagLi
0x17f32  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::WrapLoopBody(class System.Xml.Xsl.ISourceLineInfo before, class System.Xml.Xsl.Qil.QilNode expr, class System.Xml.Xsl.ISourceLineInfo after)
0x17f37  stloc.0
0x17f38  ldarg.0
0x17f39  ldloc.0
0x17f3a  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::AddCurrentPositionLast(class System.Xml.Xsl.Qil.QilNode content)
0x17f3f  stloc.0
0x17f40  ldarg.0
0x17f41  ldflda   valuetype System.Xml.Xsl.Xslt.LoopFocus System.Xml.Xsl.Xslt.QilGenerator::curLoop
0x17f46  ldloc.0
0x17f47  call     instance class System.Xml.Xsl.Qil.QilLoop System.Xml.Xsl.Xslt.LoopFocus::ConstructLoop(class System.Xml.Xsl.Qil.QilNode body)
0x17f4c  stloc.0
0x17f4d  ldarg.0
0x17f4e  ldloc.s  4
0x17f50  stfld    valuetype System.Xml.Xsl.Xslt.LoopFocus System.Xml.Xsl.Xslt.QilGenerator::curLoop
0x17f55  ldarg.0
0x17f56  ldfld    class VariableHelper System.Xml.Xsl.Xslt.QilGenerator::varHelper
0x17f5b  ldloc.0
0x17f5c  ldloc.2
0x17f5d  callvirt instance class System.Xml.Xsl.Qil.QilNode VariableHelper::FinishVariables(class System.Xml.Xsl.Qil.QilNode node, int32 varScope)
0x17f62  stloc.0
0x17f63  ldloc.0
0x17f64  ret
```
