# System.Xaml.XamlObjectWriter::Logic_ProvideValue

- ea: `0x4770`
- end: `0x48a2`
- name: `System.Xaml.XamlObjectWriter::Logic_ProvideValue`
- size: `306`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: ``

## callers

- `0x4740`
- `0x5790`

## callees

- `0x2870`
- `0x3b70`
- `0x4770`
- `0x8b20`
- `0xa3f0`
- `0xa440`
- `0xa590`
- `0xa6c0`
- `0xb280`
- `0xb2f0`
- `0xd230`
- `0xd7d0`
- `0xefa0`
- `0x1b9d0`
- `0x1ba00`
- `0x1bc70`
- `0x20370`
- `0x21220`
- `0x215c0`
- `0x215f0`
- `0x21610`
- `0x21690`
- `0x216d0`
- `0x216f0`
- `0x21710`

## pseudocode

```c

```

## disassembly

```asm
0x4770  ldarg.1
0x4771  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x4776  stloc.0
0x4777  ldloc.0
0x4778  castclass System.Windows.Markup.MarkupExtension
0x477d  stloc.1
0x477e  ldarg.1
0x477f  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentInstance()
0x4784  stloc.2
0x4785  ldarg.1
0x4786  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentProperty()
0x478b  stloc.3
0x478c  ldloc.3
0x478d  ldnull
0x478e  call     bool System.Xaml.XamlMember::op_Inequality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x4793  brfalse.s loc_4800
0x4795  ldloc.3
0x4796  callvirt instance bool System.Xaml.XamlMember::get_IsUnknown()
0x479b  brtrue.s loc_4800
0x479d  ldnull
0x479e  stloc.s  5
0x47a0  ldloc.3
0x47a1  callvirt instance bool System.Xaml.XamlMember::get_IsAttachable()
0x47a6  brfalse.s loc_47B2
0x47a8  ldloc.3
0x47a9  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_DeclaringType()
0x47ae  stloc.s  5
0x47b0  br.s     loc_47BA
0x47b2  ldarg.1
0x47b3  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentType()
0x47b8  stloc.s  5
0x47ba  ldloc.s  5
0x47bc  ldnull
0x47bd  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x47c2  brfalse.s loc_4800
0x47c4  ldloc.s  5
0x47c6  callvirt instance class [mscorlib]System.EventHandler`1<class System.Windows.Markup.XamlSetMarkupExtensionEventArgs> System.Xaml.XamlType::get_SetMarkupExtensionHandler()
0x47cb  brfalse.s loc_4800
0x47cd  ldloc.3
0x47ce  ldloc.1
0x47cf  ldarg.1
0x47d0  callvirt instance class MS.Internal.Xaml.ServiceProviderContext MS.Internal.Xaml.Context.ObjectWriterContext::get_ServiceProviderContext()
0x47d5  ldloc.2
0x47d6  newobj   instance void System.Windows.Markup.XamlSetMarkupExtensionEventArgs::.ctor(class System.Xaml.XamlMember member, class System.Windows.Markup.MarkupExtension value, class [mscorlib]System.IServiceProvider serviceProvider, object targetObject)
0x47db  stloc.s  6
0x47dd  ldloc.s  6
0x47df  ldloc.s  5
0x47e1  callvirt instance void System.Windows.Markup.XamlSetMarkupExtensionEventArgs::set_CurrentType(class System.Xaml.XamlType value)
0x47e6  ldloc.s  5
0x47e8  callvirt instance class [mscorlib]System.EventHandler`1<class System.Windows.Markup.XamlSetMarkupExtensionEventArgs> System.Xaml.XamlType::get_SetMarkupExtensionHandler()
0x47ed  ldloc.2
0x47ee  ldloc.s  6
0x47f0  callvirt instance void class [mscorlib]System.EventHandler`1<class System.Windows.Markup.XamlSetMarkupExtensionEventArgs>::Invoke(object, var<u1>)
0x47f5  ldloc.s  6
0x47f7  callvirt instance bool System.Windows.Markup.XamlSetValueEventArgs::get_Handled()
0x47fc  brfalse.s loc_4800
0x47fe  ldc.i4.1
0x47ff  ret
0x4800  ldloc.1
0x4801  stloc.s  4
0x4803  ldarg.1
0x4804  callvirt instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_LiveDepth()
0x4809  ldc.i4.1
0x480a  bne.un.s loc_4814
0x480c  ldarg.0
0x480d  ldfld    bool System.Xaml.XamlObjectWriter::_skipProvideValueOnRoot
0x4812  brtrue.s loc_4828
0x4814  ldarg.0
0x4815  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x481a  ldloc.1
0x481b  ldarg.1
0x481c  callvirt instance class MS.Internal.Xaml.ServiceProviderContext MS.Internal.Xaml.Context.ObjectWriterContext::get_ServiceProviderContext()
0x4821  callvirt instance object MS.Internal.Xaml.Runtime.XamlRuntime::CallProvideValue(class System.Windows.Markup.MarkupExtension me, class [mscorlib]System.IServiceProvider serviceProvider)
0x4826  stloc.s  4
0x4828  ldarg.1
0x4829  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentProperty()
0x482e  ldnull
0x482f  call     bool System.Xaml.XamlMember::op_Inequality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x4834  brfalse.s loc_4898
0x4836  ldloc.s  4
0x4838  brfalse.s loc_4858
0x483a  ldloc.s  4
0x483c  isinst   MS.Internal.Xaml.Context.NameFixupToken
0x4841  brtrue.s loc_488E
0x4843  ldarg.1
0x4844  ldarg.0
0x4845  ldloc.s  4
0x4847  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x484c  call     instance class System.Xaml.XamlType System.Xaml.XamlObjectWriter::GetXamlType(class [mscorlib]System.Type clrType)
0x4851  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentType(class System.Xaml.XamlType value)
0x4856  br.s     loc_488E
0x4858  ldarg.1
0x4859  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentProperty()
0x485e  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Items()
0x4863  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x4868  brfalse.s loc_487D
0x486a  ldarg.1
0x486b  ldarg.1
0x486c  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentType()
0x4871  callvirt instance class System.Xaml.XamlType System.Xaml.XamlType::get_ItemType()
0x4876  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentType(class System.Xaml.XamlType value)
0x487b  br.s     loc_488E
0x487d  ldarg.1
0x487e  ldarg.1
0x487f  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentProperty()
0x4884  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x4889  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentType(class System.Xaml.XamlType value)
0x488e  ldarg.1
0x488f  ldloc.s  4
0x4891  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentInstance(object value)
0x4896  br.s     loc_48A0
0x4898  ldarg.1
0x4899  ldloc.s  4
0x489b  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentInstance(object value)
0x48a0  ldc.i4.0
0x48a1  ret
```
