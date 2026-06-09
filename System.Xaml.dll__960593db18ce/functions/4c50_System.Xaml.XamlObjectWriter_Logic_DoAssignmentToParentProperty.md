# System.Xaml.XamlObjectWriter::Logic_DoAssignmentToParentProperty

- ea: `0x4c50`
- end: `0x4edd`
- name: `System.Xaml.XamlObjectWriter::Logic_DoAssignmentToParentProperty`
- size: `653`
- prototype: ``
- caller_count: `5`
- callee_count: `40`
- tags: ``

## callers

- `0x2ca0`
- `0x33d0`
- `0x4740`
- `0x48f0`
- `0x5790`

## callees

- `0x45b0`
- `0x4710`
- `0x48b0`
- `0x4940`
- `0x4c50`
- `0x4ee0`
- `0x4f90`
- `0x8590`
- `0x8620`
- `0x8750`
- `0x8b20`
- `0x8b40`
- `0x8b70`
- `0x8b80`
- `0x8bf0`
- `0x8c50`
- `0xa590`
- `0xa6e0`
- `0xb280`
- `0xb2f0`
- `0xd110`
- `0xd130`
- `0xd500`
- `0x11f20`
- `0x11f50`
- `0x12dc0`
- `0x20d10`
- `0x21200`
- `0x215f0`
- `0x21610`
- `0x21690`
- `0x216d0`
- `0x216f0`
- `0x21710`
- `0x217f0`
- `0x21890`
- `0x218b0`
- `0x21950`
- `0x21a40`
- `0x21c10`

## string_xrefs

- `0x4ecc`: `BadStateObjectWriter`

## pseudocode

```c

```

## disassembly

```asm
0x4c50  ldarg.1
0x4c51  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentProperty()
0x4c56  stloc.0
0x4c57  ldarg.1
0x4c58  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x4c5d  stloc.1
0x4c5e  ldloc.0
0x4c5f  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x4c64  stloc.2
0x4c65  ldloc.0
0x4c66  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0x4c6b  brfalse  loc_4D08
0x4c70  ldloc.2
0x4c71  callvirt instance bool System.Xaml.XamlType::get_IsCollection()
0x4c76  brtrue.s loc_4C83
0x4c78  ldloc.2
0x4c79  callvirt instance bool System.Xaml.XamlType::get_IsDictionary()
0x4c7e  brfalse  loc_4D08
0x4c83  ldloc.1
0x4c84  isinst   MS.Internal.Xaml.Context.NameFixupToken
0x4c89  brfalse.s loc_4CDB
0x4c8b  ldloc.0
0x4c8c  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Items()
0x4c91  call     bool System.Xaml.XamlMember::op_Inequality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x4c96  brfalse.s loc_4CDB
0x4c98  ldloc.1
0x4c99  isinst   MS.Internal.Xaml.Context.NameFixupToken
0x4c9e  stloc.3
0x4c9f  ldstr    asc_37CD8// ","
0x4ca4  ldloc.3
0x4ca5  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> MS.Internal.Xaml.Context.NameFixupToken::get_NeededNames()
0x4caa  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x4caf  call     string [mscorlib]System.String::Join(string, string[])
0x4cb4  stloc.s  4
0x4cb6  ldstr    aForwardrefdire// "ForwardRefDirectives"
0x4cbb  ldc.i4.1
0x4cbc  newarr   [mscorlib]System.Object
0x4cc1  dup
0x4cc2  ldc.i4.0
0x4cc3  ldloc.s  4
0x4cc5  stelem.ref
0x4cc6  call     string System.Xaml.SR::Get(string id, object[] args)
0x4ccb  stloc.s  5
0x4ccd  ldarg.1
0x4cce  ldloc.s  5
0x4cd0  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x4cd5  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x4cda  throw
0x4cdb  ldloc.0
0x4cdc  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_PositionalParameters()
0x4ce1  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x4ce6  brfalse.s loc_4D00
0x4ce8  ldarg.1
0x4ce9  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_PositionalParameterDescriptor()
0x4cee  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentType(class System.Xaml.XamlType value)
0x4cf3  ldarg.1
0x4cf4  ldloc.1
0x4cf5  ldc.i4.0
0x4cf6  newobj   instance void System.Xaml.MS.Impl.PositionalParameterDescriptor::.ctor(object value, bool wasText)
0x4cfb  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentInstance(object value)
0x4d00  ldarg.0
0x4d01  ldarg.1
0x4d02  call     instance void System.Xaml.XamlObjectWriter::Logic_DoAssignmentToParentCollection(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x4d07  ret
0x4d08  ldarg.1
0x4d09  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentInstance()
0x4d0e  stloc.s  6
0x4d10  ldloc.s  6
0x4d12  brfalse  loc_4E0A
0x4d17  ldarg.1
0x4d18  callvirt instance bool MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentIsPropertyValueSet()
0x4d1d  brfalse.s loc_4D37
0x4d1f  ldarg.1
0x4d20  ldarg.1
0x4d21  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentProperty()
0x4d26  ldarg.1
0x4d27  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentType()
0x4d2c  newobj   instance void System.Xaml.XamlDuplicateMemberException::.ctor(class System.Xaml.XamlMember member, class System.Xaml.XamlType type)
0x4d31  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x4d36  throw
0x4d37  ldarg.1
0x4d38  ldc.i4.1
0x4d39  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_ParentIsPropertyValueSet(bool value)
0x4d3e  ldloc.1
0x4d3f  isinst   MS.Internal.Xaml.Context.NameFixupToken
0x4d44  brfalse.s loc_4DB4
0x4d46  ldloc.1
0x4d47  castclass MS.Internal.Xaml.Context.NameFixupToken
0x4d4c  stloc.s  7
0x4d4e  ldloc.0
0x4d4f  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0x4d54  brfalse.s loc_4DAA
0x4d56  ldloc.0
0x4d57  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Key()
0x4d5c  call     bool System.Xaml.XamlMember::op_Inequality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x4d61  brfalse.s loc_4DA0
0x4d63  ldstr    asc_37CD8// ","
0x4d68  ldloc.s  7
0x4d6a  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> MS.Internal.Xaml.Context.NameFixupToken::get_NeededNames()
0x4d6f  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x4d74  call     string [mscorlib]System.String::Join(string, string[])
0x4d79  stloc.s  8
0x4d7b  ldstr    aForwardrefdire// "ForwardRefDirectives"
0x4d80  ldc.i4.1
0x4d81  newarr   [mscorlib]System.Object
0x4d86  dup
0x4d87  ldc.i4.0
0x4d88  ldloc.s  8
0x4d8a  stelem.ref
0x4d8b  call     string System.Xaml.SR::Get(string id, object[] args)
0x4d90  stloc.s  9
0x4d92  ldarg.1
0x4d93  ldloc.s  9
0x4d95  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x4d9a  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x4d9f  throw
0x4da0  ldarg.0
0x4da1  ldarg.1
0x4da2  ldloc.s  7
0x4da4  call     instance void System.Xaml.XamlObjectWriter::Logic_PendKeyFixupToken(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, class MS.Internal.Xaml.Context.NameFixupToken token)
0x4da9  ret
0x4daa  ldarg.0
0x4dab  ldarg.1
0x4dac  ldloc.s  7
0x4dae  call     instance void System.Xaml.XamlObjectWriter::Logic_PendCurrentFixupToken_SetValue(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, class MS.Internal.Xaml.Context.NameFixupToken token)
0x4db3  ret
0x4db4  ldarg.1
0x4db5  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentType()
0x4dba  stloc.s  0xA
0x4dbc  ldarg.1
0x4dbd  callvirt instance bool MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentIsObjectFromMember()
0x4dc2  brtrue   loc_4EDC
0x4dc7  ldarg.0
0x4dc8  ldarg.1
0x4dc9  ldloc.0
0x4dca  ldloc.1
0x4dcb  ldc.i4.1
0x4dcc  call     instance void System.Xaml.XamlObjectWriter::Logic_ApplyPropertyValue(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, class System.Xaml.XamlMember prop, object value, bool onParent)
0x4dd1  ldloc.0
0x4dd2  ldloc.s  0xA
0x4dd4  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Name()
0x4dd9  callvirt instance class System.Xaml.XamlMember System.Xaml.XamlType::GetAliasedProperty(class System.Xaml.XamlDirective directive)
0x4dde  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x4de3  brfalse.s loc_4DF2
0x4de5  ldarg.0
0x4de6  ldarg.1
0x4de7  ldloc.1
0x4de8  castclass [mscorlib]System.String
0x4ded  call     instance void System.Xaml.XamlObjectWriter::Logic_RegisterName_OnParent(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, string name)
0x4df2  ldloc.0
0x4df3  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Key()
0x4df8  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x4dfd  brfalse  loc_4EDC
0x4e02  ldarg.1
0x4e03  ldloc.1
0x4e04  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_ParentKey(object value)
0x4e09  ret
0x4e0a  ldloc.0
0x4e0b  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0x4e10  brfalse  loc_4ECC
0x4e15  ldloc.0
0x4e16  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Base()
0x4e1b  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x4e20  brfalse.s loc_4E41
0x4e22  ldarg.0
0x4e23  ldarg.1
0x4e24  ldloc.1
0x4e25  castclass [mscorlib]System.String
0x4e2a  call     instance void System.Xaml.XamlObjectWriter::Logic_CheckBaseUri(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, string value)
0x4e2f  ldarg.1
0x4e30  ldloc.1
0x4e31  castclass [mscorlib]System.String
0x4e36  newobj   instance void [System]System.Uri::.ctor(string)
0x4e3b  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_BaseUri(class [System]System.Uri value)
0x4e40  ret
0x4e41  ldloc.1
0x4e42  isinst   MS.Internal.Xaml.Context.NameFixupToken
0x4e47  brfalse.s loc_4EA9
0x4e49  ldloc.0
0x4e4a  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Key()
0x4e4f  call     bool System.Xaml.XamlMember::op_Inequality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x4e54  brfalse.s loc_4E9B
0x4e56  ldloc.1
0x4e57  castclass MS.Internal.Xaml.Context.NameFixupToken
0x4e5c  stloc.s  0xB
0x4e5e  ldstr    asc_37CD8// ","
0x4e63  ldloc.s  0xB
0x4e65  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> MS.Internal.Xaml.Context.NameFixupToken::get_NeededNames()
0x4e6a  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x4e6f  call     string [mscorlib]System.String::Join(string, string[])
0x4e74  stloc.s  0xC
0x4e76  ldstr    aForwardrefdire// "ForwardRefDirectives"
0x4e7b  ldc.i4.1
0x4e7c  newarr   [mscorlib]System.Object
0x4e81  dup
0x4e82  ldc.i4.0
0x4e83  ldloc.s  0xC
0x4e85  stelem.ref
0x4e86  call     string System.Xaml.SR::Get(string id, object[] args)
0x4e8b  stloc.s  0xD
0x4e8d  ldarg.1
0x4e8e  ldloc.s  0xD
0x4e90  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x4e95  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x4e9a  throw
0x4e9b  ldarg.0
0x4e9c  ldarg.1
0x4e9d  ldloc.1
0x4e9e  castclass MS.Internal.Xaml.Context.NameFixupToken
0x4ea3  call     instance void System.Xaml.XamlObjectWriter::Logic_PendKeyFixupToken(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, class MS.Internal.Xaml.Context.NameFixupToken token)
0x4ea8  ret
0x4ea9  ldloc.0
0x4eaa  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Key()
0x4eaf  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x4eb4  brfalse.s loc_4EBE
0x4eb6  ldarg.1
0x4eb7  ldloc.1
0x4eb8  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_ParentKey(object value)
0x4ebd  ret
0x4ebe  ldarg.1
0x4ebf  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xaml.XamlMember, object> MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentPreconstructionPropertyValues()
0x4ec4  ldloc.0
0x4ec5  ldloc.1
0x4ec6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xaml.XamlMember, object>::Add(var<u1>, !!T0)
0x4ecb  ret
0x4ecc  ldstr    aBadstateobject// "BadStateObjectWriter"
0x4ed1  call     string System.Xaml.SR::Get(string id)
0x4ed6  newobj   instance void System.Xaml.XamlInternalException::.ctor(string message)
0x4edb  throw
0x4edc  ret
```
