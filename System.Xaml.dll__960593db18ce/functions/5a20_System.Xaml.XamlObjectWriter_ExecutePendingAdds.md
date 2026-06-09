# System.Xaml.XamlObjectWriter::ExecutePendingAdds

- ea: `0x5a20`
- end: `0x5b98`
- name: `System.Xaml.XamlObjectWriter::ExecutePendingAdds`
- size: `376`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: ``

## callers

- `0x2ca0`
- `0x5660`

## callees

- `0x2830`
- `0x2850`
- `0x2870`
- `0x3b20`
- `0x4a40`
- `0x5a20`
- `0xd130`
- `0xd230`
- `0x201e0`
- `0x201f0`
- `0x202f0`
- `0x20300`
- `0x21540`
- `0x21590`
- `0x215f0`
- `0x216f0`
- `0x21c50`
- `0x27b50`
- `0x27b60`
- `0x27b70`
- `0x27b80`
- `0x27b90`
- `0x27bb0`
- `0x27bd0`

## pseudocode

```c

```

## disassembly

```asm
0x5a20  ldarg.0
0x5a21  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<object, class [mscorlib]System.Collections.Generic.List`1<class PendingCollectionAdd>> System.Xaml.XamlObjectWriter::_pendingCollectionAdds
0x5a26  brfalse  loc_5B97
0x5a2b  ldarg.0
0x5a2c  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, class [mscorlib]System.Collections.Generic.List`1<class PendingCollectionAdd>> System.Xaml.XamlObjectWriter::get_PendingCollectionAdds()
0x5a31  ldarg.2
0x5a32  ldloca.s 0
0x5a34  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<object, class [mscorlib]System.Collections.Generic.List`1<class PendingCollectionAdd>>::TryGetValue(var<u1>, !!T0)
0x5a39  brfalse  loc_5B97
0x5a3e  ldloc.0
0x5a3f  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class PendingCollectionAdd>::GetEnumerator()
0x5a44  stloc.1
0x5a45  br       loc_5B4B
0x5a4a  ldloca.s 1
0x5a4c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class PendingCollectionAdd>::get_Current()
0x5a51  stloc.2
0x5a52  ldloc.2
0x5a53  callvirt instance class System.Xaml.XamlType PendingCollectionAdd::get_ItemType()
0x5a58  dup
0x5a59  brtrue.s loc_5A62
0x5a5b  pop
0x5a5c  ldarg.1
0x5a5d  callvirt instance class System.Xaml.XamlType System.Xaml.XamlType::get_ItemType()
0x5a62  stloc.3
0x5a63  ldarg.0
0x5a64  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x5a69  callvirt instance class MS.Internal.Xaml.Runtime.IAddLineInfo MS.Internal.Xaml.Runtime.XamlRuntime::get_LineInfo()
0x5a6e  stloc.s  4
0x5a70  ldarg.0
0x5a71  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x5a76  ldloc.2
0x5a77  callvirt instance void MS.Internal.Xaml.Runtime.XamlRuntime::set_LineInfo(class MS.Internal.Xaml.Runtime.IAddLineInfo value)
0x5a7c  ldarg.1
0x5a7d  callvirt instance bool System.Xaml.XamlType::get_IsDictionary()
0x5a82  brfalse  loc_5B22
0x5a87  ldloc.2
0x5a88  callvirt instance bool PendingCollectionAdd::get_KeyIsSet()
0x5a8d  brtrue.s loc_5AAA
0x5a8f  ldloc.2
0x5a90  ldarg.0
0x5a91  ldloc.2
0x5a92  callvirt instance object PendingCollectionAdd::get_Item()
0x5a97  ldloc.3
0x5a98  ldloc.2
0x5a99  call     instance object System.Xaml.XamlObjectWriter::GetKeyFromInstance(object instance, class System.Xaml.XamlType instanceType, class MS.Internal.Xaml.Runtime.IAddLineInfo lineInfo)
0x5a9e  callvirt instance void PendingCollectionAdd::set_Key(object value)
0x5aa3  ldloc.2
0x5aa4  ldc.i4.1
0x5aa5  callvirt instance void PendingCollectionAdd::set_KeyIsSet(bool value)
0x5aaa  ldloc.2
0x5aab  callvirt instance bool PendingCollectionAdd::get_KeyIsUnconverted()
0x5ab0  brfalse.s loc_5B06
0x5ab2  ldarg.0
0x5ab3  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, class MS.Internal.Xaml.Context.ObjectWriterContext> System.Xaml.XamlObjectWriter::get_PendingKeyConversionContexts()
0x5ab8  ldarg.2
0x5ab9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<object, class MS.Internal.Xaml.Context.ObjectWriterContext>::get_Item(void)
0x5abe  stloc.s  5
0x5ac0  ldloc.s  5
0x5ac2  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::PopScope()
0x5ac7  ldloc.s  5
0x5ac9  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::PushScope()
0x5ace  ldloc.s  5
0x5ad0  ldloc.3
0x5ad1  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentType(class System.Xaml.XamlType value)
0x5ad6  ldloc.s  5
0x5ad8  ldloc.2
0x5ad9  callvirt instance object PendingCollectionAdd::get_Item()
0x5ade  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentInstance(object value)
0x5ae3  ldloc.s  5
0x5ae5  ldloc.2
0x5ae6  callvirt instance bool PendingCollectionAdd::get_KeyIsUnconverted()
0x5aeb  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentKeyIsUnconverted(bool value)
0x5af0  ldarg.0
0x5af1  ldloc.s  5
0x5af3  ldloc.2
0x5af4  callvirt instance object PendingCollectionAdd::get_Key()
0x5af9  ldloc.2
0x5afa  callvirt instance object PendingCollectionAdd::get_Item()
0x5aff  call     instance void System.Xaml.XamlObjectWriter::Logic_AddToParentDictionary(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, object key, object value)
0x5b04  leave.s  loc_5B4B
0x5b06  ldarg.0
0x5b07  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x5b0c  ldarg.2
0x5b0d  ldarg.1
0x5b0e  ldloc.2
0x5b0f  callvirt instance object PendingCollectionAdd::get_Item()
0x5b14  ldloc.3
0x5b15  ldloc.2
0x5b16  callvirt instance object PendingCollectionAdd::get_Key()
0x5b1b  callvirt instance void MS.Internal.Xaml.Runtime.XamlRuntime::AddToDictionary(object collection, class System.Xaml.XamlType dictionaryType, object value, class System.Xaml.XamlType valueXamlType, object key)
0x5b20  leave.s  loc_5B4B
0x5b22  ldarg.0
0x5b23  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x5b28  ldarg.2
0x5b29  ldarg.1
0x5b2a  ldloc.2
0x5b2b  callvirt instance object PendingCollectionAdd::get_Item()
0x5b30  ldloc.2
0x5b31  callvirt instance class System.Xaml.XamlType PendingCollectionAdd::get_ItemType()
0x5b36  callvirt instance void MS.Internal.Xaml.Runtime.XamlRuntime::Add(object collection, class System.Xaml.XamlType collectionType, object value, class System.Xaml.XamlType valueXamlType)
0x5b3b  leave.s  loc_5B4B
0x5b3d  ldarg.0
0x5b3e  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x5b43  ldloc.s  4
0x5b45  callvirt instance void MS.Internal.Xaml.Runtime.XamlRuntime::set_LineInfo(class MS.Internal.Xaml.Runtime.IAddLineInfo value)
0x5b4a  endfinally
0x5b4b  ldloca.s 1
0x5b4d  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class PendingCollectionAdd>::MoveNext()
0x5b52  brtrue   loc_5A4A
0x5b57  leave.s  loc_5B67
0x5b59  ldloca.s 1
0x5b5b  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class PendingCollectionAdd>
0x5b61  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b66  endfinally
0x5b67  ldarg.0
0x5b68  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, class [mscorlib]System.Collections.Generic.List`1<class PendingCollectionAdd>> System.Xaml.XamlObjectWriter::get_PendingCollectionAdds()
0x5b6d  ldarg.2
0x5b6e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<object, class [mscorlib]System.Collections.Generic.List`1<class PendingCollectionAdd>>::Remove(var<u1>)
0x5b73  pop
0x5b74  ldarg.0
0x5b75  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<object, class MS.Internal.Xaml.Context.ObjectWriterContext> System.Xaml.XamlObjectWriter::_pendingKeyConversionContexts
0x5b7a  brfalse.s loc_5B97
0x5b7c  ldarg.0
0x5b7d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<object, class MS.Internal.Xaml.Context.ObjectWriterContext> System.Xaml.XamlObjectWriter::_pendingKeyConversionContexts
0x5b82  ldarg.2
0x5b83  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<object, class MS.Internal.Xaml.Context.ObjectWriterContext>::ContainsKey(var<u1>)
0x5b88  brfalse.s loc_5B97
0x5b8a  ldarg.0
0x5b8b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<object, class MS.Internal.Xaml.Context.ObjectWriterContext> System.Xaml.XamlObjectWriter::_pendingKeyConversionContexts
0x5b90  ldarg.2
0x5b91  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<object, class MS.Internal.Xaml.Context.ObjectWriterContext>::Remove(var<u1>)
0x5b96  pop
0x5b97  ret
```
