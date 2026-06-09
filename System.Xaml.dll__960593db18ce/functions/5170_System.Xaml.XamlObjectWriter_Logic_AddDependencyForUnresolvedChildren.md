# System.Xaml.XamlObjectWriter::Logic_AddDependencyForUnresolvedChildren

- ea: `0x5170`
- end: `0x523d`
- name: `System.Xaml.XamlObjectWriter::Logic_AddDependencyForUnresolvedChildren`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: ``

## callers

- `0x2ca0`
- `0x4410`

## callees

- `0x48b0`
- `0x5170`
- `0x5240`
- `0x8590`
- `0x8b40`
- `0xa6e0`
- `0xb2f0`
- `0x11f50`
- `0x20590`
- `0x20a50`
- `0x20a90`
- `0x20b50`
- `0x20c70`
- `0x21200`
- `0x21610`
- `0x21690`
- `0x216d0`
- `0x21710`
- `0x21830`

## pseudocode

```c

```

## disassembly

```asm
0x5170  ldarg.1
0x5171  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x5176  stloc.0
0x5177  ldarg.1
0x5178  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentProperty()
0x517d  stloc.1
0x517e  ldloc.1
0x517f  ldnull
0x5180  call     bool System.Xaml.XamlMember::op_Inequality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x5185  brfalse.s loc_51F7
0x5187  ldloc.1
0x5188  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0x518d  brfalse.s loc_51F7
0x518f  ldarg.1
0x5190  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentInstance()
0x5195  brtrue.s loc_51F7
0x5197  ldloc.1
0x5198  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Key()
0x519d  call     bool System.Xaml.XamlMember::op_Inequality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x51a2  brfalse.s loc_51F7
0x51a4  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x51a9  stloc.3
0x51aa  ldarg.0
0x51ab  ldfld    class MS.Internal.Xaml.Context.NameFixupGraph System.Xaml.XamlObjectWriter::_nameFixupGraph
0x51b0  ldloc.0
0x51b1  ldloc.3
0x51b2  callvirt instance void MS.Internal.Xaml.Context.NameFixupGraph::GetDependentNames(object instance, class [mscorlib]System.Collections.Generic.List`1<string> result)
0x51b7  ldstr    asc_3787C// ", "
0x51bc  ldloc.3
0x51bd  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x51c2  call     string [mscorlib]System.String::Join(string, string[])
0x51c7  stloc.s  4
0x51c9  ldarg.1
0x51ca  ldstr    aTransitiveforw// "TransitiveForwardRefDirectives"
0x51cf  ldc.i4.3
0x51d0  newarr   [mscorlib]System.Object
0x51d5  dup
0x51d6  ldc.i4.0
0x51d7  ldloc.0
0x51d8  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x51dd  stelem.ref
0x51de  dup
0x51df  ldc.i4.1
0x51e0  ldloc.1
0x51e1  stelem.ref
0x51e2  dup
0x51e3  ldc.i4.2
0x51e4  ldloc.s  4
0x51e6  stelem.ref
0x51e7  call     string System.Xaml.SR::Get(string id, object[] args)
0x51ec  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x51f1  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x51f6  throw
0x51f7  ldarg.0
0x51f8  ldloc.0
0x51f9  ldloc.1
0x51fa  ldarg.2
0x51fb  call     instance class MS.Internal.Xaml.Context.NameFixupToken System.Xaml.XamlObjectWriter::GetTokenForUnresolvedChildren(object childThatHasUnresolvedChildren, class System.Xaml.XamlMember property, class System.Xaml.XamlSavedContext deferredMarkupExtensionContext)
0x5200  stloc.2
0x5201  ldloc.2
0x5202  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x5207  ldarg.1
0x5208  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentInstance()
0x520d  callvirt instance void MS.Internal.Xaml.Context.FixupTarget::set_Instance(object value)
0x5212  ldloc.2
0x5213  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x5218  ldarg.1
0x5219  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentType()
0x521e  callvirt instance void MS.Internal.Xaml.Context.FixupTarget::set_InstanceType(class System.Xaml.XamlType value)
0x5223  ldloc.2
0x5224  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x5229  ldarg.1
0x522a  callvirt instance bool MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentIsObjectFromMember()
0x522f  callvirt instance void MS.Internal.Xaml.Context.FixupTarget::set_InstanceWasGotten(bool value)
0x5234  ldarg.0
0x5235  ldarg.1
0x5236  ldloc.2
0x5237  call     instance void System.Xaml.XamlObjectWriter::Logic_PendCurrentFixupToken_SetValue(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, class MS.Internal.Xaml.Context.NameFixupToken token)
0x523c  ret
```
