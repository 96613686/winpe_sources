# System.Xml.Xsl.Xslt.XslAstRewriter::Refactor

- ea: `0x1f5b0`
- end: `0x1f7ae`
- name: `System.Xml.Xsl.Xslt.XslAstRewriter::Refactor`
- size: `510`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1f4b0`

## callees

- `0x13aa0`
- `0x13ad0`
- `0x1db00`
- `0x1dba0`
- `0x1dbc0`
- `0x1dbd0`
- `0x1e140`
- `0x1e280`
- `0x1e2c0`
- `0x1e2e0`
- `0x1f5b0`
- `0x254e0`
- `0x374b0`
- `0x374d0`
- `0x374f0`
- `0x37510`
- `0x56c60`

## string_xrefs

- `0x1f5d4`: `compiler`

## pseudocode

```c

```

## disassembly

```asm
0x1f5b0  ldarg.1
0x1f5b1  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.XslNode::get_Content()
0x1f5b6  castclass class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode>
0x1f5bb  stloc.0
0x1f5bc  ldloc.0
0x1f5bd  ldarg.2
0x1f5be  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode>::get_Item(!!T0)
0x1f5c3  stloc.1
0x1f5c4  ldstr    aGenerated// "generated"
0x1f5c9  ldarg.0
0x1f5ca  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XslAstRewriter::compiler
0x1f5cf  callvirt instance string System.Xml.Xsl.Xslt.Compiler::CreatePhantomNamespace()
0x1f5d4  ldstr    aCompiler// "compiler"
0x1f5d9  call     class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.AstFactory::QName(string local, string uri, string prefix)
0x1f5de  stloc.2
0x1f5df  ldloc.1
0x1f5e0  ldfld    class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Xslt.XslNode::SourceLine
0x1f5e5  newobj   instance void ContextInfo::.ctor(class System.Xml.Xsl.ISourceLineInfo lineinfo)
0x1f5ea  stloc.3
0x1f5eb  ldloc.2
0x1f5ec  ldloc.3
0x1f5ed  call     class System.Xml.Xsl.Xslt.XslNodeEx System.Xml.Xsl.Xslt.AstFactory::CallTemplate(class System.Xml.Xsl.Qil.QilName name, class ContextInfo ctxInfo)
0x1f5f2  stloc.s  4
0x1f5f4  ldloc.s  4
0x1f5f6  ldnull
0x1f5f7  ldloc.3
0x1f5f8  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::SetInfo(class System.Xml.Xsl.Xslt.XslNode to, class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content, class ContextInfo info)
0x1f5fd  pop
0x1f5fe  ldloc.2
0x1f5ff  ldnull
0x1f600  ldsfld   class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XsltLoader::nullMode
0x1f605  ldc.r8   NaN
0x1f60e  ldloc.1
0x1f60f  ldfld    valuetype System.Xml.Xsl.Xslt.XslVersion System.Xml.Xsl.Xslt.XslNode::XslVersion
0x1f614  call     class System.Xml.Xsl.Xslt.Template System.Xml.Xsl.Xslt.AstFactory::Template(class System.Xml.Xsl.Qil.QilName name, string match, class System.Xml.Xsl.Qil.QilName mode, float64 priority, valuetype System.Xml.Xsl.Xslt.XslVersion xslVer)
0x1f619  stloc.s  5
0x1f61b  ldloc.s  5
0x1f61d  ldnull
0x1f61e  ldloc.3
0x1f61f  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::SetInfo(class System.Xml.Xsl.Xslt.XslNode to, class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content, class ContextInfo info)
0x1f624  pop
0x1f625  ldarg.0
0x1f626  ldfld    class [System]System.Collections.Generic.Stack`1<class System.Xml.Xsl.Xslt.Template> System.Xml.Xsl.Xslt.XslAstRewriter::newTemplates
0x1f62b  ldloc.s  5
0x1f62d  callvirt instance void class [System]System.Collections.Generic.Stack`1<class System.Xml.Xsl.Xslt.Template>::Push(var<u1>)
0x1f632  ldloc.s  5
0x1f634  ldloc.0
0x1f635  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode>::get_Count()
0x1f63a  ldarg.2
0x1f63b  sub
0x1f63c  ldc.i4.8
0x1f63d  add
0x1f63e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode>::.ctor(int32)
0x1f643  callvirt instance void System.Xml.Xsl.Xslt.XslNode::SetContent(class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content)
0x1f648  ldarg.0
0x1f649  ldfld    class System.Xml.Xsl.Xslt.CompilerScopeManager`1<class System.Xml.Xsl.Xslt.VarPar> System.Xml.Xsl.Xslt.XslAstRewriter::scope
0x1f64e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype ScopeRecord<var<u1>>> class System.Xml.Xsl.Xslt.CompilerScopeManager`1<class System.Xml.Xsl.Xslt.VarPar>::GetActiveRecords()
0x1f653  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype ScopeRecord<class System.Xml.Xsl.Xslt.VarPar>>::GetEnumerator()
0x1f658  stloc.s  6
0x1f65a  br       loc_1F753
0x1f65f  ldloc.s  6
0x1f661  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype ScopeRecord<class System.Xml.Xsl.Xslt.VarPar>>::get_Current()
0x1f666  stloc.s  7
0x1f668  ldloca.s 7
0x1f66a  call     instance bool valuetype ScopeRecord<class System.Xml.Xsl.Xslt.VarPar>::get_IsVariable()
0x1f66f  brtrue.s loc_1F697
0x1f671  ldloc.s  5
0x1f673  ldloc.s  5
0x1f675  ldfld    class System.Xml.Xsl.Xslt.NsDecl System.Xml.Xsl.Xslt.XslNode::Namespaces
0x1f67a  ldloc.s  7
0x1f67c  ldfld    string valuetype ScopeRecord<class System.Xml.Xsl.Xslt.VarPar>::ncName
0x1f681  ldloc.s  7
0x1f683  ldfld    string valuetype ScopeRecord<class System.Xml.Xsl.Xslt.VarPar>::nsUri
0x1f688  newobj   instance void System.Xml.Xsl.Xslt.NsDecl::.ctor(class System.Xml.Xsl.Xslt.NsDecl prev, string prefix, string nsUri)
0x1f68d  stfld    class System.Xml.Xsl.Xslt.NsDecl System.Xml.Xsl.Xslt.XslNode::Namespaces
0x1f692  br       loc_1F753
0x1f697  ldloc.s  7
0x1f699  ldfld    var<u1> valuetype ScopeRecord<class System.Xml.Xsl.Xslt.VarPar>::value
0x1f69e  stloc.s  8
0x1f6a0  ldarg.0
0x1f6a1  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XslAstRewriter::compiler
0x1f6a6  ldloc.s  8
0x1f6a8  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XslNode::Name
0x1f6ad  callvirt instance string System.Xml.Xsl.Qil.QilName::get_NamespaceUri()
0x1f6b2  callvirt instance bool System.Xml.Xsl.Xslt.Compiler::IsPhantomNamespace(string namespaceName)
0x1f6b7  brtrue   loc_1F753
0x1f6bc  ldloc.s  8
0x1f6be  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XslNode::Name
0x1f6c3  callvirt instance string System.Xml.Xsl.Qil.QilName::get_LocalName()
0x1f6c8  ldloc.s  8
0x1f6ca  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XslNode::Name
0x1f6cf  callvirt instance string System.Xml.Xsl.Qil.QilName::get_NamespaceUri()
0x1f6d4  ldloc.s  8
0x1f6d6  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XslNode::Name
0x1f6db  callvirt instance string System.Xml.Xsl.Qil.QilName::get_Prefix()
0x1f6e0  call     class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.AstFactory::QName(string local, string uri, string prefix)
0x1f6e5  stloc.s  9
0x1f6e7  ldc.i4.s 0x1F
0x1f6e9  ldloc.s  9
0x1f6eb  ldstr    asc_5B2E4// "$"
0x1f6f0  ldloc.s  9
0x1f6f2  callvirt instance string System.Xml.Xsl.Qil.QilName::get_QualifiedName()
0x1f6f7  call     string [mscorlib]System.String::Concat(string, string)
0x1f6fc  ldc.i4.0
0x1f6fd  call     class System.Xml.Xsl.Xslt.VarPar System.Xml.Xsl.Xslt.AstFactory::VarPar(valuetype System.Xml.Xsl.Xslt.XslNodeType nt, class System.Xml.Xsl.Qil.QilName name, string select, valuetype System.Xml.Xsl.Xslt.XslVersion xslVer)
0x1f702  stloc.s  0xA
0x1f704  ldloc.s  0xA
0x1f706  ldnull
0x1f707  ldloc.3
0x1f708  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::SetInfo(class System.Xml.Xsl.Xslt.XslNode to, class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content, class ContextInfo info)
0x1f70d  pop
0x1f70e  ldloc.s  0xA
0x1f710  ldloc.s  8
0x1f712  ldfld    class System.Xml.Xsl.Xslt.NsDecl System.Xml.Xsl.Xslt.XslNode::Namespaces
0x1f717  stfld    class System.Xml.Xsl.Xslt.NsDecl System.Xml.Xsl.Xslt.XslNode::Namespaces
0x1f71c  ldloc.s  4
0x1f71e  ldloc.s  0xA
0x1f720  callvirt instance void System.Xml.Xsl.Xslt.XslNode::AddContent(class System.Xml.Xsl.Xslt.XslNode node)
0x1f725  ldc.i4.s 0x16
0x1f727  ldloc.s  9
0x1f729  ldnull
0x1f72a  ldc.i4.0
0x1f72b  call     class System.Xml.Xsl.Xslt.VarPar System.Xml.Xsl.Xslt.AstFactory::VarPar(valuetype System.Xml.Xsl.Xslt.XslNodeType nt, class System.Xml.Xsl.Qil.QilName name, string select, valuetype System.Xml.Xsl.Xslt.XslVersion xslVer)
0x1f730  stloc.s  0xB
0x1f732  ldloc.s  0xB
0x1f734  ldnull
0x1f735  ldloc.3
0x1f736  call     class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.XsltLoader::SetInfo(class System.Xml.Xsl.Xslt.XslNode to, class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode> content, class ContextInfo info)
0x1f73b  pop
0x1f73c  ldloc.s  0xB
0x1f73e  ldloc.s  8
0x1f740  ldfld    class System.Xml.Xsl.Xslt.NsDecl System.Xml.Xsl.Xslt.XslNode::Namespaces
0x1f745  stfld    class System.Xml.Xsl.Xslt.NsDecl System.Xml.Xsl.Xslt.XslNode::Namespaces
0x1f74a  ldloc.s  5
0x1f74c  ldloc.s  0xB
0x1f74e  callvirt instance void System.Xml.Xsl.Xslt.XslNode::AddContent(class System.Xml.Xsl.Xslt.XslNode node)
0x1f753  ldloc.s  6
0x1f755  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1f75a  brtrue   loc_1F65F
0x1f75f  leave.s  loc_1F76D
0x1f761  ldloc.s  6
0x1f763  brfalse.s loc_1F76C
0x1f765  ldloc.s  6
0x1f767  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f76c  endfinally
0x1f76d  ldarg.2
0x1f76e  stloc.s  0xC
0x1f770  br.s     loc_1F787
0x1f772  ldloc.s  5
0x1f774  ldloc.0
0x1f775  ldloc.s  0xC
0x1f777  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode>::get_Item(!!T0)
0x1f77c  callvirt instance void System.Xml.Xsl.Xslt.XslNode::AddContent(class System.Xml.Xsl.Xslt.XslNode node)
0x1f781  ldloc.s  0xC
0x1f783  ldc.i4.1
0x1f784  add
0x1f785  stloc.s  0xC
0x1f787  ldloc.s  0xC
0x1f789  ldloc.0
0x1f78a  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode>::get_Count()
0x1f78f  blt.s    loc_1F772
0x1f791  ldloc.0
0x1f792  ldarg.2
0x1f793  ldloc.s  4
0x1f795  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode>::set_Item(int32, var<u1>)
0x1f79a  ldloc.0
0x1f79b  ldarg.2
0x1f79c  ldc.i4.1
0x1f79d  add
0x1f79e  ldloc.0
0x1f79f  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode>::get_Count()
0x1f7a4  ldarg.2
0x1f7a5  sub
0x1f7a6  ldc.i4.1
0x1f7a7  sub
0x1f7a8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.XslNode>::RemoveRange(int32, int32)
0x1f7ad  ret
```
