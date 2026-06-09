# System.Xaml.XamlObjectWriter::CompleteNameReferences

- ea: `0x5280`
- end: `0x5404`
- name: `System.Xaml.XamlObjectWriter::CompleteNameReferences`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x2ca0`

## callees

- `0x5280`
- `0x5410`
- `0x5660`
- `0x56d0`
- `0x20510`
- `0x20790`
- `0x207c0`
- `0x207d0`
- `0x207e0`
- `0x20a40`
- `0x20c70`
- `0x20cb0`
- `0x20d10`
- `0x20d20`
- `0x20d30`
- `0x20d40`
- `0x216d0`

## pseudocode

```c

```

## disassembly

```asm
0x5280  ldarg.0
0x5281  ldfld    class MS.Internal.Xaml.Context.NameFixupGraph System.Xaml.XamlObjectWriter::_nameFixupGraph
0x5286  brtrue.s loc_5289
0x5288  ret
0x5289  ldnull
0x528a  stloc.0
0x528b  ldarg.0
0x528c  ldfld    class MS.Internal.Xaml.Context.NameFixupGraph System.Xaml.XamlObjectWriter::_nameFixupGraph
0x5291  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class MS.Internal.Xaml.Context.NameFixupToken> MS.Internal.Xaml.Context.NameFixupGraph::GetRemainingSimpleFixups()
0x5296  stloc.1
0x5297  ldloc.1
0x5298  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class MS.Internal.Xaml.Context.NameFixupToken>::GetEnumerator()
0x529d  stloc.s  4
0x529f  br.s     loc_5312
0x52a1  ldloc.s  4
0x52a3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class MS.Internal.Xaml.Context.NameFixupToken>::get_Current()
0x52a8  stloc.s  5
0x52aa  ldloc.s  5
0x52ac  ldloc.s  5
0x52ae  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> MS.Internal.Xaml.Context.NameFixupToken::get_NeededNames()
0x52b3  ldc.i4.0
0x52b4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x52b9  callvirt instance object MS.Internal.Xaml.Context.NameFixupToken::ResolveName(string name)
0x52be  stloc.s  6
0x52c0  ldloc.s  6
0x52c2  brtrue.s loc_52D7
0x52c4  ldloc.0
0x52c5  brtrue.s loc_52CD
0x52c7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class MS.Internal.Xaml.Context.NameFixupToken>::.ctor()
0x52cc  stloc.0
0x52cd  ldloc.0
0x52ce  ldloc.s  5
0x52d0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MS.Internal.Xaml.Context.NameFixupToken>::Add(var<u1>)
0x52d5  br.s     loc_5312
0x52d7  ldloc.0
0x52d8  brtrue.s loc_5312
0x52da  ldloc.s  5
0x52dc  ldloc.s  6
0x52de  callvirt instance void MS.Internal.Xaml.Context.NameFixupToken::set_ReferencedObject(object value)
0x52e3  ldloc.s  5
0x52e5  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> MS.Internal.Xaml.Context.NameFixupToken::get_NeededNames()
0x52ea  ldc.i4.0
0x52eb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::RemoveAt(int32)
0x52f0  ldarg.0
0x52f1  ldloc.s  5
0x52f3  ldc.i4.1
0x52f4  call     instance void System.Xaml.XamlObjectWriter::ProcessNameFixup(class MS.Internal.Xaml.Context.NameFixupToken token, bool nameResolutionIsComplete)
0x52f9  ldarg.0
0x52fa  ldfld    class MS.Internal.Xaml.Context.NameFixupGraph System.Xaml.XamlObjectWriter::_nameFixupGraph
0x52ff  ldloc.s  5
0x5301  callvirt instance object MS.Internal.Xaml.Context.NameFixupToken::get_ReferencedObject()
0x5306  ldloc.s  5
0x5308  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x530d  callvirt instance void MS.Internal.Xaml.Context.NameFixupGraph::AddEndOfParseDependency(object childThatHasUnresolvedChildren, class MS.Internal.Xaml.Context.FixupTarget parentObject)
0x5312  ldloc.s  4
0x5314  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5319  brtrue.s loc_52A1
0x531b  leave.s  loc_5329
0x531d  ldloc.s  4
0x531f  brfalse.s loc_5328
0x5321  ldloc.s  4
0x5323  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5328  endfinally
0x5329  ldloc.0
0x532a  brfalse.s loc_5333
0x532c  ldarg.0
0x532d  ldloc.0
0x532e  call     instance void System.Xaml.XamlObjectWriter::ThrowUnresolvedRefs(class [mscorlib]System.Collections.Generic.IEnumerable`1<class MS.Internal.Xaml.Context.NameFixupToken> unresolvedRefs)
0x5333  ldarg.0
0x5334  ldfld    class MS.Internal.Xaml.Context.NameFixupGraph System.Xaml.XamlObjectWriter::_nameFixupGraph
0x5339  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class MS.Internal.Xaml.Context.NameFixupToken> MS.Internal.Xaml.Context.NameFixupGraph::GetRemainingReparses()
0x533e  stloc.2
0x533f  ldloc.2
0x5340  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class MS.Internal.Xaml.Context.NameFixupToken>::GetEnumerator()
0x5345  stloc.s  7
0x5347  br.s     loc_5379
0x5349  ldloc.s  7
0x534b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class MS.Internal.Xaml.Context.NameFixupToken>::get_Current()
0x5350  stloc.s  8
0x5352  ldarg.0
0x5353  ldloc.s  8
0x5355  ldc.i4.1
0x5356  call     instance void System.Xaml.XamlObjectWriter::ProcessNameFixup(class MS.Internal.Xaml.Context.NameFixupToken token, bool nameResolutionIsComplete)
0x535b  ldarg.0
0x535c  ldfld    class MS.Internal.Xaml.Context.NameFixupGraph System.Xaml.XamlObjectWriter::_nameFixupGraph
0x5361  ldloc.s  8
0x5363  callvirt instance class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.Context.NameFixupToken::get_TargetContext()
0x5368  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x536d  ldloc.s  8
0x536f  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x5374  callvirt instance void MS.Internal.Xaml.Context.NameFixupGraph::AddEndOfParseDependency(object childThatHasUnresolvedChildren, class MS.Internal.Xaml.Context.FixupTarget parentObject)
0x5379  ldloc.s  7
0x537b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5380  brtrue.s loc_5349
0x5382  leave.s  loc_5390
0x5384  ldloc.s  7
0x5386  brfalse.s loc_538F
0x5388  ldloc.s  7
0x538a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x538f  endfinally
0x5390  ldarg.0
0x5391  ldfld    class MS.Internal.Xaml.Context.NameFixupGraph System.Xaml.XamlObjectWriter::_nameFixupGraph
0x5396  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class MS.Internal.Xaml.Context.NameFixupToken> MS.Internal.Xaml.Context.NameFixupGraph::GetRemainingObjectDependencies()
0x539b  stloc.3
0x539c  ldloc.3
0x539d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class MS.Internal.Xaml.Context.NameFixupToken>::GetEnumerator()
0x53a2  stloc.s  9
0x53a4  br.s     loc_53EC
0x53a6  ldloc.s  9
0x53a8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class MS.Internal.Xaml.Context.NameFixupToken>::get_Current()
0x53ad  stloc.s  0xA
0x53af  ldarg.0
0x53b0  ldloc.s  0xA
0x53b2  ldc.i4.1
0x53b3  call     instance void System.Xaml.XamlObjectWriter::ProcessNameFixup(class MS.Internal.Xaml.Context.NameFixupToken token, bool nameResolutionIsComplete)
0x53b8  ldloc.s  0xA
0x53ba  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x53bf  callvirt instance object MS.Internal.Xaml.Context.FixupTarget::get_Instance()
0x53c4  brfalse.s loc_53EC
0x53c6  ldarg.0
0x53c7  ldfld    class MS.Internal.Xaml.Context.NameFixupGraph System.Xaml.XamlObjectWriter::_nameFixupGraph
0x53cc  ldloc.s  0xA
0x53ce  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x53d3  callvirt instance object MS.Internal.Xaml.Context.FixupTarget::get_Instance()
0x53d8  callvirt instance bool MS.Internal.Xaml.Context.NameFixupGraph::HasUnresolvedChildren(object parent)
0x53dd  brtrue.s loc_53EC
0x53df  ldarg.0
0x53e0  ldloc.s  0xA
0x53e2  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x53e7  call     instance void System.Xaml.XamlObjectWriter::CompleteDeferredInitialization(class MS.Internal.Xaml.Context.FixupTarget target)
0x53ec  ldloc.s  9
0x53ee  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x53f3  brtrue.s loc_53A6
0x53f5  leave.s  loc_5403
0x53f7  ldloc.s  9
0x53f9  brfalse.s loc_5402
0x53fb  ldloc.s  9
0x53fd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5402  endfinally
0x5403  ret
```
