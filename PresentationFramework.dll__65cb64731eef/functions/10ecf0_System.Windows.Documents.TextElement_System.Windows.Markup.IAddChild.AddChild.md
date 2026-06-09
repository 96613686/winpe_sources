# System.Windows.Documents.TextElement::System.Windows.Markup.IAddChild.AddChild

- ea: `0x10ecf0`
- end: `0x10ee7b`
- name: `System.Windows.Documents.TextElement::System.Windows.Markup.IAddChild.AddChild`
- size: `395`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x38c70`
- `0xcb8a0`
- `0xcb8c0`
- `0xe3820`
- `0xe3b60`
- `0xe3b80`
- `0x10ecf0`
- `0x10f8b0`
- `0x11f040`
- `0x11f0b0`

## string_xrefs

- `0x10ed32`: `TextSchema_ThisInlineUIContainerHasAChildUIElementAlready`
- `0x10ed99`: `TextSchema_ThisBlockUIContainerHasAChildUIElementAlready`

## pseudocode

```c

```

## disassembly

```asm
0x10ecf0  ldarg.1
0x10ecf1  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x10ecf6  stloc.0
0x10ecf7  ldarg.1
0x10ecf8  isinst   System.Windows.Documents.TextElement
0x10ecfd  stloc.1
0x10ecfe  ldloc.1
0x10ecff  brfalse.s loc_10ED13
0x10ed01  ldarg.0
0x10ed02  ldloc.1
0x10ed03  ldc.i4.1
0x10ed04  ldc.i4.1
0x10ed05  call     bool System.Windows.Documents.TextSchema::ValidateChild(class System.Windows.Documents.TextElement parent, class System.Windows.Documents.TextElement child, bool throwIfIllegalChild, bool throwIfIllegalHyperlinkDescendent)
0x10ed0a  pop
0x10ed0b  ldarg.0
0x10ed0c  ldloc.1
0x10ed0d  call     instance void System.Windows.Documents.TextElement::Append(class System.Windows.Documents.TextElement element)
0x10ed12  ret
0x10ed13  ldarg.1
0x10ed14  isinst   [PresentationCore]System.Windows.UIElement
0x10ed19  stloc.2
0x10ed1a  ldloc.2
0x10ed1b  brfalse  loc_10EE49
0x10ed20  ldarg.0
0x10ed21  isinst   System.Windows.Documents.InlineUIContainer
0x10ed26  stloc.3
0x10ed27  ldloc.3
0x10ed28  brfalse.s loc_10ED84
0x10ed2a  ldloc.3
0x10ed2b  callvirt instance class [PresentationCore]System.Windows.UIElement System.Windows.Documents.InlineUIContainer::get_Child()
0x10ed30  brfalse.s loc_10ED7C
0x10ed32  ldstr    aTextschemaThis// "TextSchema_ThisInlineUIContainerHasAChi"...
0x10ed37  ldc.i4.3
0x10ed38  newarr   [mscorlib]System.Object
0x10ed3d  dup
0x10ed3e  ldc.i4.0
0x10ed3f  ldarg.0
0x10ed40  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x10ed45  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x10ed4a  stelem.ref
0x10ed4b  dup
0x10ed4c  ldc.i4.1
0x10ed4d  ldarg.0
0x10ed4e  castclass System.Windows.Documents.InlineUIContainer
0x10ed53  call     instance class [PresentationCore]System.Windows.UIElement System.Windows.Documents.InlineUIContainer::get_Child()
0x10ed58  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x10ed5d  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x10ed62  stelem.ref
0x10ed63  dup
0x10ed64  ldc.i4.2
0x10ed65  ldarg.1
0x10ed66  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x10ed6b  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x10ed70  stelem.ref
0x10ed71  call     string System.Windows.SR::Get(string id, object[] args)
0x10ed76  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x10ed7b  throw
0x10ed7c  ldloc.3
0x10ed7d  ldloc.2
0x10ed7e  callvirt instance void System.Windows.Documents.InlineUIContainer::set_Child(class [PresentationCore]System.Windows.UIElement value)
0x10ed83  ret
0x10ed84  ldarg.0
0x10ed85  isinst   System.Windows.Documents.BlockUIContainer
0x10ed8a  stloc.s  4
0x10ed8c  ldloc.s  4
0x10ed8e  brfalse.s loc_10EDEC
0x10ed90  ldloc.s  4
0x10ed92  callvirt instance class [PresentationCore]System.Windows.UIElement System.Windows.Documents.BlockUIContainer::get_Child()
0x10ed97  brfalse.s loc_10EDE3
0x10ed99  ldstr    aTextschemaThis_0// "TextSchema_ThisBlockUIContainerHasAChil"...
0x10ed9e  ldc.i4.3
0x10ed9f  newarr   [mscorlib]System.Object
0x10eda4  dup
0x10eda5  ldc.i4.0
0x10eda6  ldarg.0
0x10eda7  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x10edac  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x10edb1  stelem.ref
0x10edb2  dup
0x10edb3  ldc.i4.1
0x10edb4  ldarg.0
0x10edb5  castclass System.Windows.Documents.BlockUIContainer
0x10edba  call     instance class [PresentationCore]System.Windows.UIElement System.Windows.Documents.BlockUIContainer::get_Child()
0x10edbf  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x10edc4  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x10edc9  stelem.ref
0x10edca  dup
0x10edcb  ldc.i4.2
0x10edcc  ldarg.1
0x10edcd  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x10edd2  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x10edd7  stelem.ref
0x10edd8  call     string System.Windows.SR::Get(string id, object[] args)
0x10eddd  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x10ede2  throw
0x10ede3  ldloc.s  4
0x10ede5  ldloc.2
0x10ede6  callvirt instance void System.Windows.Documents.BlockUIContainer::set_Child(class [PresentationCore]System.Windows.UIElement value)
0x10edeb  ret
0x10edec  ldarg.0
0x10eded  ldtoken  System.Windows.Documents.InlineUIContainer
0x10edf2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10edf7  call     bool System.Windows.Documents.TextSchema::IsValidChild(class System.Windows.Documents.TextElement parent, class [mscorlib]System.Type childType)
0x10edfc  brfalse.s loc_10EE17
0x10edfe  ldarg.0
0x10edff  call     class System.Windows.Documents.InlineUIContainer System.Windows.Documents.Inline::CreateImplicitInlineUIContainer(class [WindowsBase]System.Windows.DependencyObject parent)
0x10ee04  stloc.s  5
0x10ee06  ldarg.0
0x10ee07  ldloc.s  5
0x10ee09  call     instance void System.Windows.Documents.TextElement::Append(class System.Windows.Documents.TextElement element)
0x10ee0e  ldloc.s  5
0x10ee10  ldloc.2
0x10ee11  callvirt instance void System.Windows.Documents.InlineUIContainer::set_Child(class [PresentationCore]System.Windows.UIElement value)
0x10ee16  ret
0x10ee17  ldstr    aTextschemaChil// "TextSchema_ChildTypeIsInvalid"
0x10ee1c  ldc.i4.2
0x10ee1d  newarr   [mscorlib]System.Object
0x10ee22  dup
0x10ee23  ldc.i4.0
0x10ee24  ldarg.0
0x10ee25  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x10ee2a  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x10ee2f  stelem.ref
0x10ee30  dup
0x10ee31  ldc.i4.1
0x10ee32  ldarg.1
0x10ee33  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x10ee38  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x10ee3d  stelem.ref
0x10ee3e  call     string System.Windows.SR::Get(string id, object[] args)
0x10ee43  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x10ee48  throw
0x10ee49  ldstr    aTextschemaChil// "TextSchema_ChildTypeIsInvalid"
0x10ee4e  ldc.i4.2
0x10ee4f  newarr   [mscorlib]System.Object
0x10ee54  dup
0x10ee55  ldc.i4.0
0x10ee56  ldarg.0
0x10ee57  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x10ee5c  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x10ee61  stelem.ref
0x10ee62  dup
0x10ee63  ldc.i4.1
0x10ee64  ldarg.1
0x10ee65  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x10ee6a  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x10ee6f  stelem.ref
0x10ee70  call     string System.Windows.SR::Get(string id, object[] args)
0x10ee75  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x10ee7a  throw
```
