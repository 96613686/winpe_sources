# System.Xaml.XamlObjectWriter::Logic_PendAssignmentToParentCollection

- ea: `0x4b10`
- end: `0x4c50`
- name: `System.Xaml.XamlObjectWriter::Logic_PendAssignmentToParentCollection`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: ``

## callers

- `0x4940`

## callees

- `0x2810`
- `0x2830`
- `0x2850`
- `0x2870`
- `0x48b0`
- `0x4b10`
- `0x20ab0`
- `0x20b10`
- `0x20c70`
- `0x20e20`
- `0x215d0`
- `0x216d0`
- `0x21790`
- `0x21a50`
- `0x21a70`
- `0x21c30`
- `0x22010`
- `0x27b60`
- `0x27b80`
- `0x27b90`
- `0x27ba0`
- `0x27bc0`
- `0x27be0`
- `0x27c00`
- `0x27c20`
- `0x27c50`

## pseudocode

```c

```

## disassembly

```asm
0x4b10  ldarg.1
0x4b11  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentCollection()
0x4b16  stloc.0
0x4b17  ldarg.1
0x4b18  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x4b1d  stloc.1
0x4b1e  ldarg.2
0x4b1f  isinst   MS.Internal.Xaml.Context.NameFixupToken
0x4b24  stloc.2
0x4b25  ldloc.1
0x4b26  isinst   MS.Internal.Xaml.Context.NameFixupToken
0x4b2b  stloc.3
0x4b2c  ldnull
0x4b2d  stloc.s  4
0x4b2f  ldarg.0
0x4b30  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<object, class [mscorlib]System.Collections.Generic.List`1<class PendingCollectionAdd>> System.Xaml.XamlObjectWriter::_pendingCollectionAdds
0x4b35  brfalse.s loc_4B46
0x4b37  ldarg.0
0x4b38  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, class [mscorlib]System.Collections.Generic.List`1<class PendingCollectionAdd>> System.Xaml.XamlObjectWriter::get_PendingCollectionAdds()
0x4b3d  ldloc.0
0x4b3e  ldloca.s 4
0x4b40  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<object, class [mscorlib]System.Collections.Generic.List`1<class PendingCollectionAdd>>::TryGetValue(var<u1>, !!T0)
0x4b45  pop
0x4b46  ldloc.s  4
0x4b48  brtrue.s loc_4B77
0x4b4a  ldloc.2
0x4b4b  brtrue.s loc_4B62
0x4b4d  ldloc.3
0x4b4e  brtrue.s loc_4B62
0x4b50  ldarg.0
0x4b51  ldarg.2
0x4b52  call     instance bool System.Xaml.XamlObjectWriter::HasUnresolvedChildren(object parent)
0x4b57  brtrue.s loc_4B62
0x4b59  ldarg.0
0x4b5a  ldloc.1
0x4b5b  call     instance bool System.Xaml.XamlObjectWriter::HasUnresolvedChildren(object parent)
0x4b60  brfalse.s loc_4B77
0x4b62  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class PendingCollectionAdd>::.ctor()
0x4b67  stloc.s  4
0x4b69  ldarg.0
0x4b6a  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, class [mscorlib]System.Collections.Generic.List`1<class PendingCollectionAdd>> System.Xaml.XamlObjectWriter::get_PendingCollectionAdds()
0x4b6f  ldloc.0
0x4b70  ldloc.s  4
0x4b72  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<object, class [mscorlib]System.Collections.Generic.List`1<class PendingCollectionAdd>>::Add(var<u1>, !!T0)
0x4b77  ldloc.2
0x4b78  brfalse.s loc_4B98
0x4b7a  ldloc.2
0x4b7b  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x4b80  ldnull
0x4b81  callvirt instance void MS.Internal.Xaml.Context.FixupTarget::set_KeyHolder(class MS.Internal.Xaml.Context.FixupTargetKeyHolder value)
0x4b86  ldloc.2
0x4b87  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x4b8c  ldloc.s  4
0x4b8e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class PendingCollectionAdd>::get_Count()
0x4b93  callvirt instance void MS.Internal.Xaml.Context.FixupTarget::set_TemporaryCollectionIndex(int32 value)
0x4b98  ldloc.3
0x4b99  brfalse.s loc_4BB5
0x4b9b  ldarg.0
0x4b9c  ldarg.1
0x4b9d  ldloc.3
0x4b9e  call     instance void System.Xaml.XamlObjectWriter::Logic_PendCurrentFixupToken_SetValue(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, class MS.Internal.Xaml.Context.NameFixupToken token)
0x4ba3  ldloc.3
0x4ba4  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x4ba9  ldloc.s  4
0x4bab  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class PendingCollectionAdd>::get_Count()
0x4bb0  callvirt instance void MS.Internal.Xaml.Context.FixupTarget::set_TemporaryCollectionIndex(int32 value)
0x4bb5  ldloc.s  4
0x4bb7  brfalse  loc_4C4E
0x4bbc  newobj   instance void PendingCollectionAdd::.ctor()
0x4bc1  dup
0x4bc2  ldarg.2
0x4bc3  callvirt instance void PendingCollectionAdd::set_Key(object value)
0x4bc8  dup
0x4bc9  ldarg.3
0x4bca  callvirt instance void PendingCollectionAdd::set_KeyIsSet(bool value)
0x4bcf  dup
0x4bd0  ldarg.1
0x4bd1  callvirt instance bool MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentKeyIsUnconverted()
0x4bd6  callvirt instance void PendingCollectionAdd::set_KeyIsUnconverted(bool value)
0x4bdb  dup
0x4bdc  ldloc.1
0x4bdd  callvirt instance void PendingCollectionAdd::set_Item(object value)
0x4be2  dup
0x4be3  ldarg.1
0x4be4  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x4be9  callvirt instance void PendingCollectionAdd::set_ItemType(class System.Xaml.XamlType value)
0x4bee  dup
0x4bef  ldarg.1
0x4bf0  callvirt instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_LineNumber()
0x4bf5  callvirt instance void PendingCollectionAdd::set_LineNumber(int32 value)
0x4bfa  dup
0x4bfb  ldarg.1
0x4bfc  callvirt instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_LinePosition()
0x4c01  callvirt instance void PendingCollectionAdd::set_LinePosition(int32 value)
0x4c06  stloc.s  5
0x4c08  ldloc.s  4
0x4c0a  ldloc.s  5
0x4c0c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class PendingCollectionAdd>::Add(var<u1>)
0x4c11  ldloc.s  5
0x4c13  callvirt instance bool PendingCollectionAdd::get_KeyIsUnconverted()
0x4c18  brfalse.s loc_4C4C
0x4c1a  ldarg.0
0x4c1b  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, class MS.Internal.Xaml.Context.ObjectWriterContext> System.Xaml.XamlObjectWriter::get_PendingKeyConversionContexts()
0x4c20  ldloc.0
0x4c21  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<object, class MS.Internal.Xaml.Context.ObjectWriterContext>::ContainsKey(var<u1>)
0x4c26  brtrue.s loc_4C4C
0x4c28  ldarg.1
0x4c29  ldc.i4.2
0x4c2a  callvirt instance class System.Xaml.XamlSavedContext MS.Internal.Xaml.Context.ObjectWriterContext::GetSavedContext(valuetype System.Xaml.SavedContextType savedContextType)
0x4c2f  stloc.s  6
0x4c31  ldarg.0
0x4c32  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, class MS.Internal.Xaml.Context.ObjectWriterContext> System.Xaml.XamlObjectWriter::get_PendingKeyConversionContexts()
0x4c37  ldloc.0
0x4c38  ldloc.s  6
0x4c3a  ldnull
0x4c3b  ldnull
0x4c3c  ldarg.0
0x4c3d  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x4c42  newobj   instance void MS.Internal.Xaml.Context.ObjectWriterContext::.ctor(class System.Xaml.XamlSavedContext savedContext, class System.Xaml.XamlObjectWriterSettings settings, class System.Windows.Markup.INameScope rootNameScope, class MS.Internal.Xaml.Runtime.XamlRuntime runtime)
0x4c47  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<object, class MS.Internal.Xaml.Context.ObjectWriterContext>::Add(var<u1>, !!T0)
0x4c4c  ldc.i4.1
0x4c4d  ret
0x4c4e  ldc.i4.0
0x4c4f  ret
```
