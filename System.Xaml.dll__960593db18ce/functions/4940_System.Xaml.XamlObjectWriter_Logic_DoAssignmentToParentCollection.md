# System.Xaml.XamlObjectWriter::Logic_DoAssignmentToParentCollection

- ea: `0x4940`
- end: `0x4a0a`
- name: `System.Xaml.XamlObjectWriter::Logic_DoAssignmentToParentCollection`
- size: `202`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: ``

## callers

- `0x3690`
- `0x4c50`

## callees

- `0x2870`
- `0x3b20`
- `0x3b70`
- `0x4940`
- `0x4a10`
- `0x4a40`
- `0x4b10`
- `0xd130`
- `0xd230`
- `0xef20`
- `0x202f0`
- `0x20370`
- `0x21220`
- `0x215d0`
- `0x21610`
- `0x216d0`
- `0x21790`
- `0x21bb0`
- `0x21bd0`

## pseudocode

```c

```

## disassembly

```asm
0x4940  ldarg.1
0x4941  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentCollection()
0x4946  stloc.0
0x4947  ldarg.1
0x4948  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentType()
0x494d  stloc.1
0x494e  ldarg.1
0x494f  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x4954  stloc.2
0x4955  ldarg.1
0x4956  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x495b  stloc.3
0x495c  ldloc.1
0x495d  callvirt instance bool System.Xaml.XamlType::get_IsDictionary()
0x4962  brtrue.s loc_49B2
0x4964  ldarg.0
0x4965  ldarg.1
0x4966  ldnull
0x4967  ldc.i4.0
0x4968  call     instance bool System.Xaml.XamlObjectWriter::Logic_PendAssignmentToParentCollection(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, object key, bool keyIsSet)
0x496d  brtrue   loc_4A09
0x4972  ldloc.3
0x4973  isinst   System.Windows.Markup.MarkupExtension
0x4978  stloc.s  4
0x497a  ldloc.s  4
0x497c  brfalse.s loc_49A2
0x497e  ldarg.0
0x497f  ldarg.1
0x4980  ldloc.3
0x4981  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4986  ldc.i4.1
0x4987  call     instance bool System.Xaml.XamlObjectWriter::Logic_WillParentCollectionAdd(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, class [mscorlib]System.Type type, bool excludeObjectType)
0x498c  brtrue.s loc_49A2
0x498e  ldarg.0
0x498f  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x4994  ldloc.s  4
0x4996  ldarg.1
0x4997  callvirt instance class MS.Internal.Xaml.ServiceProviderContext MS.Internal.Xaml.Context.ObjectWriterContext::get_ServiceProviderContext()
0x499c  callvirt instance object MS.Internal.Xaml.Runtime.XamlRuntime::CallProvideValue(class System.Windows.Markup.MarkupExtension me, class [mscorlib]System.IServiceProvider serviceProvider)
0x49a1  stloc.3
0x49a2  ldarg.0
0x49a3  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x49a8  ldloc.0
0x49a9  ldloc.1
0x49aa  ldloc.3
0x49ab  ldloc.2
0x49ac  callvirt instance void MS.Internal.Xaml.Runtime.XamlRuntime::Add(object collection, class System.Xaml.XamlType collectionType, object value, class System.Xaml.XamlType valueXamlType)
0x49b1  ret
0x49b2  ldloc.2
0x49b3  ldnull
0x49b4  call     bool System.Xaml.XamlType::op_Equality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x49b9  brfalse.s loc_49D3
0x49bb  ldloc.3
0x49bc  brfalse.s loc_49CC
0x49be  ldarg.0
0x49bf  ldloc.3
0x49c0  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x49c5  call     instance class System.Xaml.XamlType System.Xaml.XamlObjectWriter::GetXamlType(class [mscorlib]System.Type clrType)
0x49ca  br.s     loc_49D2
0x49cc  ldloc.1
0x49cd  callvirt instance class System.Xaml.XamlType System.Xaml.XamlType::get_ItemType()
0x49d2  stloc.2
0x49d3  ldarg.1
0x49d4  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentKey()
0x49d9  stloc.s  5
0x49db  ldarg.1
0x49dc  callvirt instance bool MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentIsKeySet()
0x49e1  stloc.s  6
0x49e3  ldarg.0
0x49e4  ldarg.1
0x49e5  ldloc.s  5
0x49e7  ldloc.s  6
0x49e9  call     instance bool System.Xaml.XamlObjectWriter::Logic_PendAssignmentToParentCollection(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, object key, bool keyIsSet)
0x49ee  brtrue.s loc_4A09
0x49f0  ldloc.s  6
0x49f2  brtrue.s loc_49FF
0x49f4  ldarg.0
0x49f5  ldloc.3
0x49f6  ldloc.2
0x49f7  ldarg.0
0x49f8  call     instance object System.Xaml.XamlObjectWriter::GetKeyFromInstance(object instance, class System.Xaml.XamlType instanceType, class MS.Internal.Xaml.Runtime.IAddLineInfo lineInfo)
0x49fd  stloc.s  5
0x49ff  ldarg.0
0x4a00  ldarg.1
0x4a01  ldloc.s  5
0x4a03  ldloc.3
0x4a04  call     instance void System.Xaml.XamlObjectWriter::Logic_AddToParentDictionary(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, object key, object value)
0x4a09  ret
```
