# System.Xaml.XamlObjectWriter::Logic_PendKeyFixupToken

- ea: `0x4ee0`
- end: `0x4f43`
- name: `System.Xaml.XamlObjectWriter::Logic_PendKeyFixupToken`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x4410`
- `0x4c50`

## callees

- `0x48b0`
- `0x4ee0`
- `0x209d0`
- `0x20a40`
- `0x20a50`
- `0x20a90`
- `0x20b10`
- `0x20b50`
- `0x20c70`
- `0x21630`
- `0x21730`
- `0x21850`
- `0x21c10`

## pseudocode

```c

```

## disassembly

```asm
0x4ee0  ldarg.2
0x4ee1  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x4ee6  ldarg.1
0x4ee7  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_GrandParentInstance()
0x4eec  callvirt instance void MS.Internal.Xaml.Context.FixupTarget::set_Instance(object value)
0x4ef1  ldarg.2
0x4ef2  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x4ef7  ldarg.1
0x4ef8  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_GrandParentType()
0x4efd  callvirt instance void MS.Internal.Xaml.Context.FixupTarget::set_InstanceType(class System.Xaml.XamlType value)
0x4f02  ldarg.2
0x4f03  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x4f08  ldarg.1
0x4f09  callvirt instance bool MS.Internal.Xaml.Context.ObjectWriterContext::get_GrandParentIsObjectFromMember()
0x4f0e  callvirt instance void MS.Internal.Xaml.Context.FixupTarget::set_InstanceWasGotten(bool value)
0x4f13  ldarg.2
0x4f14  newobj   instance void MS.Internal.Xaml.Context.FixupTargetKeyHolder::.ctor(object key)
0x4f19  stloc.0
0x4f1a  ldarg.2
0x4f1b  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x4f20  ldloc.0
0x4f21  callvirt instance void MS.Internal.Xaml.Context.FixupTarget::set_KeyHolder(class MS.Internal.Xaml.Context.FixupTargetKeyHolder value)
0x4f26  ldarg.1
0x4f27  ldloc.0
0x4f28  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_ParentKey(object value)
0x4f2d  ldarg.2
0x4f2e  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x4f33  callvirt instance object MS.Internal.Xaml.Context.FixupTarget::get_Instance()
0x4f38  brfalse.s loc_4F42
0x4f3a  ldarg.0
0x4f3b  ldarg.1
0x4f3c  ldarg.2
0x4f3d  call     instance void System.Xaml.XamlObjectWriter::Logic_PendCurrentFixupToken_SetValue(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, class MS.Internal.Xaml.Context.NameFixupToken token)
0x4f42  ret
```
