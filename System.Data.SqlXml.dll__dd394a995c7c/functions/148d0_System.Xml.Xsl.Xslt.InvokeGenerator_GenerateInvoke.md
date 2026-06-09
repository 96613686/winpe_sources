# System.Xml.Xsl.Xslt.InvokeGenerator::GenerateInvoke

- ea: `0x148d0`
- end: `0x14a03`
- name: `System.Xml.Xsl.Xslt.InvokeGenerator::GenerateInvoke`
- size: `307`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x15c80`
- `0x17f90`
- `0x18110`

## callees

- `0x2030`
- `0x148d0`
- `0x14a10`
- `0x26450`
- `0x35a00`
- `0x36ec0`
- `0x374d0`
- `0x376c0`
- `0x37740`
- `0x37750`
- `0x377c0`
- `0x37990`
- `0x379b0`
- `0x37af0`
- `0x38120`
- `0x381f0`
- `0x383a0`

## string_xrefs

- `0x1493a`: `urn:schemas-microsoft-com:xslt-debug`

## pseudocode

```c

```

## disassembly

```asm
0x148d0  ldarg.0
0x148d1  ldfld    class [System]System.Collections.Generic.Stack`1<class System.Xml.Xsl.Qil.QilIterator> System.Xml.Xsl.Xslt.InvokeGenerator::iterStack
0x148d6  callvirt instance void class [System]System.Collections.Generic.Stack`1<class System.Xml.Xsl.Qil.QilIterator>::Clear()
0x148db  ldarg.0
0x148dc  ldarg.1
0x148dd  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilFunction::get_Arguments()
0x148e2  stfld    class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.InvokeGenerator::formalArgs
0x148e7  ldarg.0
0x148e8  ldarg.0
0x148e9  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.InvokeGenerator::fac
0x148ee  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilPatternFactory::ActualParameterList()
0x148f3  stfld    class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.InvokeGenerator::invokeArgs
0x148f8  ldarg.0
0x148f9  ldc.i4.0
0x148fa  stfld    int32 System.Xml.Xsl.Xslt.InvokeGenerator::curArg
0x148ff  br       loc_149B1
0x14904  ldarg.0
0x14905  ldfld    class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.InvokeGenerator::formalArgs
0x1490a  ldarg.0
0x1490b  ldfld    int32 System.Xml.Xsl.Xslt.InvokeGenerator::curArg
0x14910  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x14915  castclass System.Xml.Xsl.Qil.QilParameter
0x1491a  stloc.1
0x1491b  ldarg.0
0x1491c  ldloc.1
0x1491d  ldarg.2
0x1491e  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.InvokeGenerator::FindActualArg(class System.Xml.Xsl.Qil.QilParameter formalArg, class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode> actualArgs)
0x14923  stloc.2
0x14924  ldloc.2
0x14925  brtrue.s loc_14970
0x14927  ldarg.0
0x14928  ldfld    bool System.Xml.Xsl.Xslt.InvokeGenerator::debug
0x1492d  brfalse.s loc_14963
0x1492f  ldloc.1
0x14930  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilParameter::get_Name()
0x14935  callvirt instance string System.Xml.Xsl.Qil.QilName::get_NamespaceUri()
0x1493a  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:xslt-debug"
0x1493f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14944  brfalse.s loc_14955
0x14946  ldarg.0
0x14947  ldloc.1
0x14948  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilParameter::get_DefaultValue()
0x1494d  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilCloneVisitor::Clone(class System.Xml.Xsl.Qil.QilNode node)
0x14952  stloc.2
0x14953  br.s     loc_14970
0x14955  ldarg.0
0x14956  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.InvokeGenerator::fac
0x1495b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.XsltQilFactory::DefaultValueMarker()
0x14960  stloc.2
0x14961  br.s     loc_14970
0x14963  ldarg.0
0x14964  ldloc.1
0x14965  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilParameter::get_DefaultValue()
0x1496a  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilCloneVisitor::Clone(class System.Xml.Xsl.Qil.QilNode node)
0x1496f  stloc.2
0x14970  ldloc.1
0x14971  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x14976  stloc.3
0x14977  ldloc.2
0x14978  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x1497d  stloc.s  4
0x1497f  ldloc.s  4
0x14981  ldloc.3
0x14982  callvirt instance bool System.Xml.Xsl.XmlQueryType::IsSubtypeOf(class System.Xml.Xsl.XmlQueryType baseType)
0x14987  brtrue.s loc_14997
0x14989  ldarg.0
0x1498a  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.InvokeGenerator::fac
0x1498f  ldloc.2
0x14990  ldloc.3
0x14991  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::TypeAssert(class System.Xml.Xsl.Qil.QilNode expr, class System.Xml.Xsl.XmlQueryType t)
0x14996  stloc.2
0x14997  ldarg.0
0x14998  ldfld    class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.InvokeGenerator::invokeArgs
0x1499d  ldloc.2
0x1499e  callvirt instance void System.Xml.Xsl.Qil.QilNode::Add(class System.Xml.Xsl.Qil.QilNode node)
0x149a3  ldarg.0
0x149a4  ldarg.0
0x149a5  ldfld    int32 System.Xml.Xsl.Xslt.InvokeGenerator::curArg
0x149aa  ldc.i4.1
0x149ab  add
0x149ac  stfld    int32 System.Xml.Xsl.Xslt.InvokeGenerator::curArg
0x149b1  ldarg.0
0x149b2  ldfld    int32 System.Xml.Xsl.Xslt.InvokeGenerator::curArg
0x149b7  ldarg.0
0x149b8  ldfld    class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.InvokeGenerator::formalArgs
0x149bd  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x149c2  blt      loc_14904
0x149c7  ldarg.0
0x149c8  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.InvokeGenerator::fac
0x149cd  ldarg.1
0x149ce  ldarg.0
0x149cf  ldfld    class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.InvokeGenerator::invokeArgs
0x149d4  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Invoke(class System.Xml.Xsl.Qil.QilFunction func, class System.Xml.Xsl.Qil.QilList args)
0x149d9  stloc.0
0x149da  br.s     loc_149F4
0x149dc  ldarg.0
0x149dd  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.InvokeGenerator::fac
0x149e2  ldarg.0
0x149e3  ldfld    class [System]System.Collections.Generic.Stack`1<class System.Xml.Xsl.Qil.QilIterator> System.Xml.Xsl.Xslt.InvokeGenerator::iterStack
0x149e8  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class System.Xml.Xsl.Qil.QilIterator>::Pop()
0x149ed  ldloc.0
0x149ee  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Loop(class System.Xml.Xsl.Qil.QilIterator variable, class System.Xml.Xsl.Qil.QilNode body)
0x149f3  stloc.0
0x149f4  ldarg.0
0x149f5  ldfld    class [System]System.Collections.Generic.Stack`1<class System.Xml.Xsl.Qil.QilIterator> System.Xml.Xsl.Xslt.InvokeGenerator::iterStack
0x149fa  callvirt instance int32 class [System]System.Collections.Generic.Stack`1<class System.Xml.Xsl.Qil.QilIterator>::get_Count()
0x149ff  brtrue.s loc_149DC
0x14a01  ldloc.0
0x14a02  ret
```
