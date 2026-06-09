# System.Xaml.XamlObjectWriter::WriteStartObject

- ea: `0x2a90`
- end: `0x2c9b`
- name: `System.Xaml.XamlObjectWriter::WriteStartObject`
- size: `523`
- prototype: ``
- caller_count: `0`
- callee_count: `30`
- tags: ``

## callees

- `0x19c0`
- `0x2a90`
- `0x3a60`
- `0x3b70`
- `0x4380`
- `0x8540`
- `0x8590`
- `0xb280`
- `0xd050`
- `0xd110`
- `0xd130`
- `0xd600`
- `0xd8d0`
- `0xef20`
- `0xefa0`
- `0xf350`
- `0x11f20`
- `0x11f50`
- `0x21200`
- `0x21540`
- `0x215c0`
- `0x215d0`
- `0x215f0`
- `0x21650`
- `0x216f0`
- `0x21770`
- `0x21a50`
- `0x21a70`
- `0x21ac0`
- `0x21ae0`

## string_xrefs

- `0x2b1d`: `CantCreateUnknownType`

## pseudocode

```c

```

## disassembly

```asm
0x2a90  ldarg.0
0x2a91  call     instance void System.Xaml.XamlObjectWriter::ThrowIfDisposed()
0x2a96  ldarg.1
0x2a97  ldnull
0x2a98  call     bool System.Xaml.XamlType::op_Equality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x2a9d  brfalse.s loc_2AAA
0x2a9f  ldstr    aXamltype// "xamlType"
0x2aa4  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2aa9  throw
0x2aaa  ldarg.0
0x2aab  ldfld    class System.Xaml.DeferringWriter System.Xaml.XamlObjectWriter::_deferringWriter
0x2ab0  ldarg.1
0x2ab1  callvirt instance void System.Xaml.XamlWriter::WriteStartObject(class System.Xaml.XamlType type)
0x2ab6  ldarg.0
0x2ab7  ldfld    class System.Xaml.DeferringWriter System.Xaml.XamlObjectWriter::_deferringWriter
0x2abc  callvirt instance bool System.Xaml.DeferringWriter::get_Handled()
0x2ac1  brfalse.s loc_2AC4
0x2ac3  ret
0x2ac4  ldarg.0
0x2ac5  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2aca  ldarg.0
0x2acb  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2ad0  callvirt instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_LineNumber()
0x2ad5  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_LineNumber_StartObject(int32 value)
0x2ada  ldarg.0
0x2adb  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2ae0  ldarg.0
0x2ae1  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2ae6  callvirt instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_LinePosition()
0x2aeb  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_LinePosition_StartObject(int32 value)
0x2af0  ldarg.0
0x2af1  ldfld    bool System.Xaml.XamlObjectWriter::_nextNodeMustBeEndMember
0x2af6  brfalse.s loc_2B15
0x2af8  ldstr    aValuemustbefol// "ValueMustBeFollowedByEndMember"
0x2afd  call     string System.Xaml.SR::Get(string id)
0x2b02  stloc.0
0x2b03  ldarg.0
0x2b04  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2b09  ldloc.0
0x2b0a  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x2b0f  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x2b14  throw
0x2b15  ldarg.1
0x2b16  callvirt instance bool System.Xaml.XamlType::get_IsUnknown()
0x2b1b  brfalse.s loc_2B49
0x2b1d  ldstr    aCantcreateunkn// "CantCreateUnknownType"
0x2b22  ldc.i4.1
0x2b23  newarr   [mscorlib]System.Object
0x2b28  dup
0x2b29  ldc.i4.0
0x2b2a  ldarg.1
0x2b2b  callvirt instance string System.Xaml.XamlType::GetQualifiedName()
0x2b30  stelem.ref
0x2b31  call     string System.Xaml.SR::Get(string id, object[] args)
0x2b36  stloc.1
0x2b37  ldarg.0
0x2b38  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2b3d  ldloc.1
0x2b3e  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x2b43  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x2b48  throw
0x2b49  ldarg.0
0x2b4a  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2b4f  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x2b54  ldnull
0x2b55  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x2b5a  brfalse.s loc_2BAE
0x2b5c  ldarg.0
0x2b5d  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2b62  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentProperty()
0x2b67  ldnull
0x2b68  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x2b6d  brfalse.s loc_2BAE
0x2b6f  ldstr    aNopropertyincu_1// "NoPropertyInCurrentFrame_SO"
0x2b74  ldc.i4.2
0x2b75  newarr   [mscorlib]System.Object
0x2b7a  dup
0x2b7b  ldc.i4.0
0x2b7c  ldarg.1
0x2b7d  callvirt instance string [mscorlib]System.Object::ToString()
0x2b82  stelem.ref
0x2b83  dup
0x2b84  ldc.i4.1
0x2b85  ldarg.0
0x2b86  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2b8b  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x2b90  callvirt instance string [mscorlib]System.Object::ToString()
0x2b95  stelem.ref
0x2b96  call     string System.Xaml.SR::Get(string id, object[] args)
0x2b9b  stloc.2
0x2b9c  ldarg.0
0x2b9d  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2ba2  ldloc.2
0x2ba3  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x2ba8  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x2bad  throw
0x2bae  ldarg.0
0x2baf  ldnull
0x2bb0  stfld    object System.Xaml.XamlObjectWriter::_lastInstance
0x2bb5  ldarg.0
0x2bb6  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2bbb  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x2bc0  ldnull
0x2bc1  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x2bc6  brfalse.s loc_2BD3
0x2bc8  ldarg.0
0x2bc9  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2bce  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::PushScope()
0x2bd3  ldarg.0
0x2bd4  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2bd9  ldarg.1
0x2bda  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentType(class System.Xaml.XamlType value)
0x2bdf  ldarg.0
0x2be0  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2be5  callvirt instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_LiveDepth()
0x2bea  ldc.i4.1
0x2beb  bne.un   loc_2C9A
0x2bf0  ldarg.0
0x2bf1  ldfld    object System.Xaml.XamlObjectWriter::_rootObjectInstance
0x2bf6  brfalse  loc_2C9A
0x2bfb  ldarg.0
0x2bfc  ldarg.0
0x2bfd  ldfld    object System.Xaml.XamlObjectWriter::_rootObjectInstance
0x2c02  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2c07  call     instance class System.Xaml.XamlType System.Xaml.XamlObjectWriter::GetXamlType(class [mscorlib]System.Type clrType)
0x2c0c  stloc.3
0x2c0d  ldloc.3
0x2c0e  ldarg.0
0x2c0f  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2c14  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x2c19  callvirt instance bool System.Xaml.XamlType::CanAssignTo(class System.Xaml.XamlType xamlType)
0x2c1e  brtrue.s loc_2C48
0x2c20  ldstr    aCantassignroot// "CantAssignRootInstance"
0x2c25  ldc.i4.2
0x2c26  newarr   [mscorlib]System.Object
0x2c2b  dup
0x2c2c  ldc.i4.0
0x2c2d  ldloc.3
0x2c2e  callvirt instance string System.Xaml.XamlType::GetQualifiedName()
0x2c33  stelem.ref
0x2c34  dup
0x2c35  ldc.i4.1
0x2c36  ldarg.1
0x2c37  callvirt instance string System.Xaml.XamlType::GetQualifiedName()
0x2c3c  stelem.ref
0x2c3d  call     string System.Xaml.SR::Get(string id, object[] args)
0x2c42  newobj   instance void System.Xaml.XamlParseException::.ctor(string message)
0x2c47  throw
0x2c48  ldarg.0
0x2c49  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2c4e  ldarg.0
0x2c4f  ldfld    object System.Xaml.XamlObjectWriter::_rootObjectInstance
0x2c54  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentInstance(object value)
0x2c59  ldarg.0
0x2c5a  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2c5f  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x2c64  callvirt instance bool System.Xaml.XamlType::get_IsCollection()
0x2c69  brtrue.s loc_2C7D
0x2c6b  ldarg.0
0x2c6c  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2c71  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x2c76  callvirt instance bool System.Xaml.XamlType::get_IsDictionary()
0x2c7b  brfalse.s loc_2C8E
0x2c7d  ldarg.0
0x2c7e  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2c83  ldarg.0
0x2c84  ldfld    object System.Xaml.XamlObjectWriter::_rootObjectInstance
0x2c89  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentCollection(object value)
0x2c8e  ldarg.0
0x2c8f  ldarg.0
0x2c90  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2c95  call     instance void System.Xaml.XamlObjectWriter::Logic_BeginInit(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x2c9a  ret
```
