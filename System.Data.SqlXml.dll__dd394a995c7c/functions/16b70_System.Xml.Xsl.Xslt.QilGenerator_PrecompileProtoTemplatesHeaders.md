# System.Xml.Xsl.Xslt.QilGenerator::PrecompileProtoTemplatesHeaders

- ea: `0x16b70`
- end: `0x170f5`
- name: `System.Xml.Xsl.Xslt.QilGenerator::PrecompileProtoTemplatesHeaders`
- size: `1413`
- prototype: ``
- caller_count: `1`
- callee_count: `40`
- tags: `registry_config, broker_com_uri`

## callers

- `0x16300`

## callees

- `0x145b0`
- `0x14620`
- `0x162d0`
- `0x167e0`
- `0x16810`
- `0x16950`
- `0x16a10`
- `0x16b70`
- `0x17100`
- `0x18600`
- `0x1a680`
- `0x1a750`
- `0x1a870`
- `0x1dba0`
- `0x1dc60`
- `0x36ec0`
- `0x36ee0`
- `0x36ef0`
- `0x374b0`
- `0x374d0`
- `0x37510`
- `0x376c0`
- `0x376e0`
- `0x376f0`
- `0x37710`
- `0x37740`
- `0x37750`
- `0x37790`
- `0x377c0`
- `0x379a0`
- `0x379b0`
- `0x379c0`
- `0x37af0`
- `0x37b50`
- `0x37c60`
- `0x37cb0`
- `0x381c0`
- `0x381f0`
- `0x38cd0`
- `0x38ce0`

## pseudocode

```c

```

## disassembly

```asm
0x16b70  ldnull
0x16b71  stloc.0
0x16b72  ldnull
0x16b73  stloc.1
0x16b74  ldnull
0x16b75  stloc.2
0x16b76  ldarg.0
0x16b77  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.QilGenerator::compiler
0x16b7c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ProtoTemplate> System.Xml.Xsl.Xslt.Compiler::AllTemplates
0x16b81  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ProtoTemplate>::GetEnumerator()
0x16b86  stloc.3
0x16b87  br       loc_16FD1
0x16b8c  ldloca.s 3
0x16b8e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Xslt.ProtoTemplate>::get_Current()
0x16b93  stloc.s  4
0x16b95  ldarg.0
0x16b96  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x16b9b  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilPatternFactory::FormalParameterList()
0x16ba0  stloc.s  5
0x16ba2  ldarg.0
0x16ba3  call     instance bool System.Xml.Xsl.Xslt.QilGenerator::get_IsDebug()
0x16ba8  brfalse.s loc_16BB1
0x16baa  ldc.i4   0x700
0x16baf  br.s     loc_16BB8
0x16bb1  ldloc.s  4
0x16bb3  ldfld    valuetype System.Xml.Xsl.XslFlags System.Xml.Xsl.Xslt.XslNode::Flags
0x16bb8  stloc.s  6
0x16bba  ldarg.0
0x16bbb  ldloc.s  4
0x16bbd  call     instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.QilGenerator::EnterScope(class System.Xml.Xsl.Xslt.XslNode node)
0x16bc2  stloc.s  7
0x16bc4  ldloc.s  6
0x16bc6  ldc.i4   0x100
0x16bcb  and
0x16bcc  brfalse.s loc_16BEC
0x16bce  ldloc.s  5
0x16bd0  ldarg.0
0x16bd1  ldarg.0
0x16bd2  ldarg.0
0x16bd3  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.QilGenerator::nameCurrent
0x16bd8  call     instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.QilGenerator::CloneName(class System.Xml.Xsl.Qil.QilName name)
0x16bdd  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::NodeNotRtf
0x16be2  call     instance class System.Xml.Xsl.Qil.QilParameter System.Xml.Xsl.Xslt.QilGenerator::CreateXslParam(class System.Xml.Xsl.Qil.QilName name, class System.Xml.Xsl.XmlQueryType xt)
0x16be7  callvirt instance void System.Xml.Xsl.Qil.QilNode::Add(class System.Xml.Xsl.Qil.QilNode node)
0x16bec  ldloc.s  6
0x16bee  ldc.i4   0x200
0x16bf3  and
0x16bf4  brfalse.s loc_16C14
0x16bf6  ldloc.s  5
0x16bf8  ldarg.0
0x16bf9  ldarg.0
0x16bfa  ldarg.0
0x16bfb  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.QilGenerator::namePosition
0x16c00  call     instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.QilGenerator::CloneName(class System.Xml.Xsl.Qil.QilName name)
0x16c05  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::DoubleX
0x16c0a  call     instance class System.Xml.Xsl.Qil.QilParameter System.Xml.Xsl.Xslt.QilGenerator::CreateXslParam(class System.Xml.Xsl.Qil.QilName name, class System.Xml.Xsl.XmlQueryType xt)
0x16c0f  callvirt instance void System.Xml.Xsl.Qil.QilNode::Add(class System.Xml.Xsl.Qil.QilNode node)
0x16c14  ldloc.s  6
0x16c16  ldc.i4   0x400
0x16c1b  and
0x16c1c  brfalse.s loc_16C3C
0x16c1e  ldloc.s  5
0x16c20  ldarg.0
0x16c21  ldarg.0
0x16c22  ldarg.0
0x16c23  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.QilGenerator::nameLast
0x16c28  call     instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.QilGenerator::CloneName(class System.Xml.Xsl.Qil.QilName name)
0x16c2d  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::DoubleX
0x16c32  call     instance class System.Xml.Xsl.Qil.QilParameter System.Xml.Xsl.Xslt.QilGenerator::CreateXslParam(class System.Xml.Xsl.Qil.QilName name, class System.Xml.Xsl.XmlQueryType xt)
0x16c37  callvirt instance void System.Xml.Xsl.Qil.QilNode::Add(class System.Xml.Xsl.Qil.QilNode node)
0x16c3c  ldarg.0
0x16c3d  call     instance bool System.Xml.Xsl.Xslt.QilGenerator::get_IsDebug()
0x16c42  brfalse.s loc_16C79
0x16c44  ldloc.s  7
0x16c46  brfalse.s loc_16C79
0x16c48  ldarg.0
0x16c49  ldarg.0
0x16c4a  ldarg.0
0x16c4b  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.QilGenerator::nameNamespaces
0x16c50  call     instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.QilGenerator::CloneName(class System.Xml.Xsl.Qil.QilName name)
0x16c55  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::NamespaceS
0x16c5a  call     instance class System.Xml.Xsl.Qil.QilParameter System.Xml.Xsl.Xslt.QilGenerator::CreateXslParam(class System.Xml.Xsl.Qil.QilName name, class System.Xml.Xsl.XmlQueryType xt)
0x16c5f  stloc.s  9
0x16c61  ldloc.s  9
0x16c63  ldarg.0
0x16c64  ldloc.s  7
0x16c66  call     instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Xslt.QilGenerator::GetNsVar(class System.Xml.Xsl.Qil.QilList nsList)
0x16c6b  callvirt instance void System.Xml.Xsl.Qil.QilParameter::set_DefaultValue(class System.Xml.Xsl.Qil.QilNode value)
0x16c70  ldloc.s  5
0x16c72  ldloc.s  9
0x16c74  callvirt instance void System.Xml.Xsl.Qil.QilNode::Add(class System.Xml.Xsl.Qil.QilNode node)
0x16c79  ldloc.s  4
0x16c7b  isinst   System.Xml.Xsl.Xslt.Template
0x16c80  stloc.s  8
0x16c82  ldloc.s  8
0x16c84  brfalse  loc_16F45
0x16c89  ldarg.0
0x16c8a  ldflda   valuetype System.Xml.Xsl.Xslt.FunctionFocus System.Xml.Xsl.Xslt.QilGenerator::funcFocus
0x16c8f  ldloc.s  5
0x16c91  ldloc.s  6
0x16c93  call     instance void System.Xml.Xsl.Xslt.FunctionFocus::StartFocus(class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode> args, valuetype System.Xml.Xsl.XslFlags flags)
0x16c98  ldc.i4.0
0x16c99  stloc.s  0xA
0x16c9b  br       loc_16F27
0x16ca0  ldloc.s  4
0x16ca2  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XslNode::get_Content()
0x16ca7  ldloc.s  0xA
0x16ca9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode>::get_Item(!!T0)
0x16cae  stloc.s  0xB
0x16cb0  ldloc.s  0xB
0x16cb2  ldfld    valuetype System.Xml.Xsl.Xslt.XslNodeType System.Xml.Xsl.Xslt.XslNode::NodeType
0x16cb7  ldc.i4.s 0x1A
0x16cb9  beq      loc_16F21
0x16cbe  ldloc.s  0xB
0x16cc0  ldfld    valuetype System.Xml.Xsl.Xslt.XslNodeType System.Xml.Xsl.Xslt.XslNode::NodeType
0x16cc5  ldc.i4.s 0x16
0x16cc7  bne.un   loc_16F3A
0x16ccc  ldloc.s  0xB
0x16cce  castclass System.Xml.Xsl.Xslt.VarPar
0x16cd3  stloc.s  0xC
0x16cd5  ldarg.0
0x16cd6  ldloc.s  0xC
0x16cd8  call     instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.QilGenerator::EnterScope(class System.Xml.Xsl.Xslt.XslNode node)
0x16cdd  pop
0x16cde  ldarg.0
0x16cdf  ldfld    class System.Xml.Xsl.Xslt.CompilerScopeManager`1<class System.Xml.Xsl.Qil.QilIterator> System.Xml.Xsl.Xslt.QilGenerator::scope
0x16ce4  ldloc.s  0xC
0x16ce6  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XslNode::Name
0x16ceb  callvirt instance string System.Xml.Xsl.Qil.QilName::get_LocalName()
0x16cf0  ldloc.s  0xC
0x16cf2  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XslNode::Name
0x16cf7  callvirt instance string System.Xml.Xsl.Qil.QilName::get_NamespaceUri()
0x16cfc  callvirt instance bool class System.Xml.Xsl.Xslt.CompilerScopeManager`1<class System.Xml.Xsl.Qil.QilIterator>::IsLocalVariable(string, string)
0x16d01  brfalse.s loc_16D23
0x16d03  ldarg.0
0x16d04  ldstr    aXsltDuplocalva// "Xslt_DupLocalVariable"
0x16d09  ldc.i4.1
0x16d0a  newarr   [mscorlib]System.String
0x16d0f  dup
0x16d10  ldc.i4.0
0x16d11  ldloc.s  0xC
0x16d13  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XslNode::Name
0x16d18  callvirt instance string System.Xml.Xsl.Qil.QilName::get_QualifiedName()
0x16d1d  stelem.ref
0x16d1e  call     instance void System.Xml.Xsl.Xslt.QilGenerator::ReportError(string res, string[] args)
0x16d23  ldarg.0
0x16d24  ldloc.s  0xC
0x16d26  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XslNode::Name
0x16d2b  ldarg.0
0x16d2c  ldloc.s  0xC
0x16d2e  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Xslt.QilGenerator::ChooseBestType(class System.Xml.Xsl.Xslt.VarPar var)
0x16d33  call     instance class System.Xml.Xsl.Qil.QilParameter System.Xml.Xsl.Xslt.QilGenerator::CreateXslParam(class System.Xml.Xsl.Qil.QilName name, class System.Xml.Xsl.XmlQueryType xt)
0x16d38  stloc.s  0xD
0x16d3a  ldarg.0
0x16d3b  call     instance bool System.Xml.Xsl.Xslt.QilGenerator::get_IsDebug()
0x16d40  brfalse.s loc_16D50
0x16d42  ldloc.s  0xD
0x16d44  ldloc.s  0xC
0x16d46  callvirt instance void System.Xml.Xsl.Qil.QilNode::set_Annotation(object value)
0x16d4b  br       loc_16EEF
0x16d50  ldloc.s  0xC
0x16d52  ldfld    valuetype System.Xml.Xsl.XslFlags System.Xml.Xsl.Xslt.VarPar::DefValueFlags
0x16d57  ldc.i4   0x1000
0x16d5c  and
0x16d5d  brtrue.s loc_16D73
0x16d5f  ldloc.s  0xD
0x16d61  ldarg.0
0x16d62  ldloc.s  0xC
0x16d64  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileVarParValue(class System.Xml.Xsl.Xslt.XslNode node)
0x16d69  callvirt instance void System.Xml.Xsl.Qil.QilParameter::set_DefaultValue(class System.Xml.Xsl.Qil.QilNode value)
0x16d6e  br       loc_16EEF
0x16d73  ldarg.0
0x16d74  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x16d79  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilPatternFactory::FormalParameterList()
0x16d7e  stloc.s  0xE
0x16d80  ldarg.0
0x16d81  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x16d86  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilPatternFactory::ActualParameterList()
0x16d8b  stloc.s  0xF
0x16d8d  ldc.i4.0
0x16d8e  stloc.s  0x11
0x16d90  br       loc_16E1F
0x16d95  ldarg.0
0x16d96  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x16d9b  ldloc.s  5
0x16d9d  ldloc.s  0x11
0x16d9f  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x16da4  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x16da9  callvirt instance class System.Xml.Xsl.Qil.QilParameter System.Xml.Xsl.Qil.QilPatternFactory::Parameter(class System.Xml.Xsl.XmlQueryType t)
0x16dae  stloc.s  0x12
0x16db0  ldloc.s  0x12
0x16db2  ldloc.s  5
0x16db4  ldloc.s  0x11
0x16db6  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x16dbb  castclass System.Xml.Xsl.Qil.QilParameter
0x16dc0  callvirt instance string System.Xml.Xsl.Qil.QilReference::get_DebugName()
0x16dc5  callvirt instance void System.Xml.Xsl.Qil.QilReference::set_DebugName(string value)
0x16dca  ldloc.s  0x12
0x16dcc  ldarg.0
0x16dcd  ldloc.s  5
0x16dcf  ldloc.s  0x11
0x16dd1  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x16dd6  castclass System.Xml.Xsl.Qil.QilParameter
0x16ddb  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilParameter::get_Name()
0x16de0  call     instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.QilGenerator::CloneName(class System.Xml.Xsl.Qil.QilName name)
0x16de5  callvirt instance void System.Xml.Xsl.Qil.QilParameter::set_Name(class System.Xml.Xsl.Qil.QilName value)
0x16dea  ldloc.s  0x12
0x16dec  ldloc.s  5
0x16dee  ldloc.s  0x11
0x16df0  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x16df5  callvirt instance class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Qil.QilNode::get_SourceLine()
0x16dfa  call     class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::SetLineInfo(class System.Xml.Xsl.Qil.QilNode n, class System.Xml.Xsl.ISourceLineInfo lineInfo)
0x16dff  pop
0x16e00  ldloc.s  0xE
0x16e02  ldloc.s  0x12
0x16e04  callvirt instance void System.Xml.Xsl.Qil.QilNode::Add(class System.Xml.Xsl.Qil.QilNode node)
0x16e09  ldloc.s  0xF
0x16e0b  ldloc.s  5
0x16e0d  ldloc.s  0x11
0x16e0f  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x16e14  callvirt instance void System.Xml.Xsl.Qil.QilNode::Add(class System.Xml.Xsl.Qil.QilNode node)
0x16e19  ldloc.s  0x11
0x16e1b  ldc.i4.1
0x16e1c  add
0x16e1d  stloc.s  0x11
0x16e1f  ldloc.s  0x11
0x16e21  ldloc.s  5
0x16e23  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x16e28  blt      loc_16D95
0x16e2d  ldloc.s  0xC
0x16e2f  dup
0x16e30  ldfld    valuetype System.Xml.Xsl.XslFlags System.Xml.Xsl.Xslt.XslNode::Flags
0x16e35  ldloc.s  8
0x16e37  ldfld    valuetype System.Xml.Xsl.XslFlags System.Xml.Xsl.Xslt.XslNode::Flags
0x16e3c  ldc.i4   0x700
0x16e41  and
0x16e42  or
0x16e43  stfld    valuetype System.Xml.Xsl.XslFlags System.Xml.Xsl.Xslt.XslNode::Flags
0x16e48  ldarg.0
0x16e49  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x16e4e  ldloc.s  0xE
0x16e50  ldarg.0
0x16e51  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x16e56  ldloc.s  0xC
0x16e58  ldfld    valuetype System.Xml.Xsl.XslFlags System.Xml.Xsl.Xslt.VarPar::DefValueFlags
0x16e5d  ldc.i4   0x4000
0x16e62  and
0x16e63  ldc.i4.0
0x16e64  cgt.un
0x16e66  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Boolean(bool b)
0x16e6b  ldarg.0
0x16e6c  ldloc.s  0xC
0x16e6e  call     instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Xslt.QilGenerator::ChooseBestType(class System.Xml.Xsl.Xslt.VarPar var)
0x16e73  callvirt instance class System.Xml.Xsl.Qil.QilFunction System.Xml.Xsl.Qil.QilPatternFactory::Function(class System.Xml.Xsl.Qil.QilList args, class System.Xml.Xsl.Qil.QilNode sideEffects, class System.Xml.Xsl.XmlQueryType resultType)
0x16e78  stloc.s  0x10
0x16e7a  ldloc.s  0x10
0x16e7c  ldsfld   class System.Xml.Xsl.SourceLineInfo System.Xml.Xsl.SourceLineInfo::NoSource
0x16e81  callvirt instance void System.Xml.Xsl.Qil.QilNode::set_SourceLine(class System.Xml.Xsl.ISourceLineInfo value)
0x16e86  ldloc.s  0x10
0x16e88  ldstr    aXslParamName// "<xsl:param name=\""
0x16e8d  ldloc.s  0xC
0x16e8f  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XslNode::Name
0x16e94  callvirt instance string System.Xml.Xsl.Qil.QilName::get_QualifiedName()
0x16e99  ldstr    asc_59D0C// "\">"
0x16e9e  call     string [mscorlib]System.String::Concat(string, string, string)
0x16ea3  callvirt instance void System.Xml.Xsl.Qil.QilReference::set_DebugName(string value)
0x16ea8  ldloc.s  0xD
0x16eaa  ldarg.0
0x16eab  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x16eb0  ldloc.s  0x10
0x16eb2  ldloc.s  0xF
0x16eb4  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Invoke(class System.Xml.Xsl.Qil.QilFunction func, class System.Xml.Xsl.Qil.QilList args)
0x16eb9  callvirt instance void System.Xml.Xsl.Qil.QilParameter::set_DefaultValue(class System.Xml.Xsl.Qil.QilNode value)
0x16ebe  ldloc.0
0x16ebf  brtrue.s loc_16ED3
0x16ec1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.VarPar>::.ctor()
0x16ec6  stloc.0
0x16ec7  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xml.Xsl.Xslt.VarPar, class System.Xml.Xsl.Xslt.Template>::.ctor()
0x16ecc  stloc.1
0x16ecd  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xml.Xsl.Xslt.VarPar, class System.Xml.Xsl.Qil.QilFunction>::.ctor()
0x16ed2  stloc.2
0x16ed3  ldloc.0
0x16ed4  ldloc.s  0xC
0x16ed6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.VarPar>::Add(var<u1>)
0x16edb  ldloc.1
0x16edc  ldloc.s  0xC
0x16ede  ldloc.s  8
0x16ee0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xml.Xsl.Xslt.VarPar, class System.Xml.Xsl.Xslt.Template>::Add(var<u1>, !!T0)
0x16ee5  ldloc.2
0x16ee6  ldloc.s  0xC
0x16ee8  ldloc.s  0x10
0x16eea  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xml.Xsl.Xslt.VarPar, class System.Xml.Xsl.Qil.QilFunction>::Add(var<u1>, !!T0)
0x16eef  ldloc.s  0xD
0x16ef1  ldloc.s  0xC
0x16ef3  ldfld    class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Xslt.XslNode::SourceLine
0x16ef8  call     class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::SetLineInfo(class System.Xml.Xsl.Qil.QilNode n, class System.Xml.Xsl.ISourceLineInfo lineInfo)
0x16efd  pop
0x16efe  ldarg.0
0x16eff  call     instance void System.Xml.Xsl.Xslt.QilGenerator::ExitScope()
0x16f04  ldarg.0
  ... truncated ...
```
