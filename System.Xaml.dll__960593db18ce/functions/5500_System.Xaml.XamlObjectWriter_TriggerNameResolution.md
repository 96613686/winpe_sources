# System.Xaml.XamlObjectWriter::TriggerNameResolution

- ea: `0x5500`
- end: `0x55f4`
- name: `System.Xaml.XamlObjectWriter::TriggerNameResolution`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x2ca0`

## callees

- `0x5500`
- `0x5660`
- `0x56d0`
- `0x20530`
- `0x20630`
- `0x20700`
- `0x20710`
- `0x20a40`
- `0x20a60`
- `0x20b20`
- `0x20bf0`
- `0x20c10`
- `0x20c70`
- `0x20cb0`
- `0x216d0`
- `0x219b0`
- `0x21ed0`

## pseudocode

```c

```

## disassembly

```asm
0x5500  ldarg.0
0x5501  ldfld    class MS.Internal.Xaml.Context.NameFixupGraph System.Xaml.XamlObjectWriter::_nameFixupGraph
0x5506  ldarg.1
0x5507  ldarg.2
0x5508  callvirt instance void MS.Internal.Xaml.Context.NameFixupGraph::ResolveDependenciesTo(object instance, string name)
0x550d  br       loc_55E3
0x5512  ldarg.0
0x5513  ldfld    class MS.Internal.Xaml.Context.NameFixupGraph System.Xaml.XamlObjectWriter::_nameFixupGraph
0x5518  callvirt instance class MS.Internal.Xaml.Context.NameFixupToken MS.Internal.Xaml.Context.NameFixupGraph::GetNextResolvedTokenPendingProcessing()
0x551d  stloc.0
0x551e  ldarg.0
0x551f  ldloc.0
0x5520  ldc.i4.0
0x5521  call     instance void System.Xaml.XamlObjectWriter::ProcessNameFixup(class MS.Internal.Xaml.Context.NameFixupToken token, bool nameResolutionIsComplete)
0x5526  ldloc.0
0x5527  callvirt instance valuetype MS.Internal.Xaml.Context.FixupType MS.Internal.Xaml.Context.NameFixupToken::get_FixupType()
0x552c  ldc.i4.3
0x552d  bne.un.s loc_5581
0x552f  ldloc.0
0x5530  callvirt instance bool MS.Internal.Xaml.Context.NameFixupToken::get_CanAssignDirectly()
0x5535  brtrue.s loc_5581
0x5537  ldloc.0
0x5538  callvirt instance class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.Context.NameFixupToken::get_TargetContext()
0x553d  callvirt instance string MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstanceRegisteredName()
0x5542  brfalse.s loc_5581
0x5544  ldarg.0
0x5545  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x554a  ldloc.0
0x554b  callvirt instance class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.Context.NameFixupToken::get_TargetContext()
0x5550  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x5555  callvirt instance bool MS.Internal.Xaml.Context.ObjectWriterContext::IsOnTheLiveStack(object instance)
0x555a  brtrue.s loc_5581
0x555c  ldloc.0
0x555d  callvirt instance class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.Context.NameFixupToken::get_TargetContext()
0x5562  callvirt instance string MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstanceRegisteredName()
0x5567  stloc.2
0x5568  ldloc.0
0x5569  callvirt instance class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.Context.NameFixupToken::get_TargetContext()
0x556e  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x5573  stloc.3
0x5574  ldarg.0
0x5575  ldfld    class MS.Internal.Xaml.Context.NameFixupGraph System.Xaml.XamlObjectWriter::_nameFixupGraph
0x557a  ldloc.3
0x557b  ldloc.2
0x557c  callvirt instance void MS.Internal.Xaml.Context.NameFixupGraph::ResolveDependenciesTo(object instance, string name)
0x5581  ldloc.0
0x5582  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x5587  callvirt instance bool MS.Internal.Xaml.Context.FixupTarget::get_InstanceIsOnTheStack()
0x558c  brtrue.s loc_55A9
0x558e  ldarg.0
0x558f  ldfld    class MS.Internal.Xaml.Context.NameFixupGraph System.Xaml.XamlObjectWriter::_nameFixupGraph
0x5594  ldloc.0
0x5595  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x559a  callvirt instance object MS.Internal.Xaml.Context.FixupTarget::get_Instance()
0x559f  callvirt instance bool MS.Internal.Xaml.Context.NameFixupGraph::HasUnresolvedOrPendingChildren(object instance)
0x55a4  ldc.i4.0
0x55a5  ceq
0x55a7  br.s     loc_55AA
0x55a9  ldc.i4.0
0x55aa  stloc.1
0x55ab  ldloc.1
0x55ac  brfalse.s loc_55E3
0x55ae  ldarg.0
0x55af  ldloc.0
0x55b0  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x55b5  call     instance void System.Xaml.XamlObjectWriter::CompleteDeferredInitialization(class MS.Internal.Xaml.Context.FixupTarget target)
0x55ba  ldloc.0
0x55bb  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x55c0  callvirt instance object MS.Internal.Xaml.Context.FixupTarget::get_Instance()
0x55c5  stloc.s  4
0x55c7  ldloc.0
0x55c8  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x55cd  callvirt instance string MS.Internal.Xaml.Context.FixupTarget::get_InstanceName()
0x55d2  stloc.s  5
0x55d4  ldarg.0
0x55d5  ldfld    class MS.Internal.Xaml.Context.NameFixupGraph System.Xaml.XamlObjectWriter::_nameFixupGraph
0x55da  ldloc.s  4
0x55dc  ldloc.s  5
0x55de  callvirt instance void MS.Internal.Xaml.Context.NameFixupGraph::ResolveDependenciesTo(object instance, string name)
0x55e3  ldarg.0
0x55e4  ldfld    class MS.Internal.Xaml.Context.NameFixupGraph System.Xaml.XamlObjectWriter::_nameFixupGraph
0x55e9  callvirt instance bool MS.Internal.Xaml.Context.NameFixupGraph::get_HasResolvedTokensPendingProcessing()
0x55ee  brtrue   loc_5512
0x55f3  ret
```
