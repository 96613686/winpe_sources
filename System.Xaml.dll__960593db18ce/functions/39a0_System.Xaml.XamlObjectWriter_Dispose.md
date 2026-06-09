# System.Xaml.XamlObjectWriter::Dispose

- ea: `0x39a0`
- end: `0x3a54`
- name: `System.Xaml.XamlObjectWriter::Dispose`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x39a0`
- `0xb2f0`
- `0xefa0`
- `0xf360`
- `0xf380`
- `0xf460`
- `0xf490`
- `0xf4a0`
- `0x215c0`
- `0x215d0`
- `0x21650`

## pseudocode

```c

```

## disassembly

```asm
0x39a0  ldarg.0
0x39a1  ldc.i4.1
0x39a2  stfld    bool System.Xaml.XamlObjectWriter::_inDispose
0x39a7  ldarg.1
0x39a8  brfalse  loc_3A42
0x39ad  ldarg.0
0x39ae  call     instance bool System.Xaml.XamlWriter::get_IsDisposed()
0x39b3  brtrue   loc_3A42
0x39b8  ldarg.0
0x39b9  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x39be  callvirt instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_LiveDepth()
0x39c3  ldc.i4.1
0x39c4  bgt.s    loc_39D9
0x39c6  ldarg.0
0x39c7  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x39cc  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x39d1  ldnull
0x39d2  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x39d7  br.s     loc_39DA
0x39d9  ldc.i4.1
0x39da  stloc.0
0x39db  ldloc.0
0x39dc  brfalse.s loc_3A0D
0x39de  br.s     loc_39FF
0x39e0  ldarg.0
0x39e1  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x39e6  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentProperty()
0x39eb  ldnull
0x39ec  call     bool System.Xaml.XamlMember::op_Inequality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x39f1  brfalse.s loc_39F9
0x39f3  ldarg.0
0x39f4  callvirt instance void System.Xaml.XamlWriter::WriteEndMember()
0x39f9  ldarg.0
0x39fa  callvirt instance void System.Xaml.XamlWriter::WriteEndObject()
0x39ff  ldarg.0
0x3a00  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3a05  callvirt instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_LiveDepth()
0x3a0a  ldc.i4.0
0x3a0b  bgt.s    loc_39E0
0x3a0d  ldarg.0
0x3a0e  ldfld    class System.Xaml.DeferringWriter System.Xaml.XamlObjectWriter::_deferringWriter
0x3a13  callvirt instance void System.Xaml.XamlWriter::Close()
0x3a18  ldarg.0
0x3a19  ldnull
0x3a1a  stfld    class System.Xaml.DeferringWriter System.Xaml.XamlObjectWriter::_deferringWriter
0x3a1f  ldarg.0
0x3a20  ldnull
0x3a21  stfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3a26  ldarg.0
0x3a27  ldnull
0x3a28  stfld    class [mscorlib]System.EventHandler`1<class System.Xaml.XamlObjectEventArgs> System.Xaml.XamlObjectWriter::_afterBeginInitHandler
0x3a2d  ldarg.0
0x3a2e  ldnull
0x3a2f  stfld    class [mscorlib]System.EventHandler`1<class System.Xaml.XamlObjectEventArgs> System.Xaml.XamlObjectWriter::_beforePropertiesHandler
0x3a34  ldarg.0
0x3a35  ldnull
0x3a36  stfld    class [mscorlib]System.EventHandler`1<class System.Xaml.XamlObjectEventArgs> System.Xaml.XamlObjectWriter::_afterPropertiesHandler
0x3a3b  ldarg.0
0x3a3c  ldnull
0x3a3d  stfld    class [mscorlib]System.EventHandler`1<class System.Xaml.XamlObjectEventArgs> System.Xaml.XamlObjectWriter::_afterEndInitHandler
0x3a42  leave.s  loc_3A53
0x3a44  ldarg.0
0x3a45  ldarg.1
0x3a46  call     instance void System.Xaml.XamlWriter::Dispose(bool disposing)
0x3a4b  ldarg.0
0x3a4c  ldc.i4.0
0x3a4d  stfld    bool System.Xaml.XamlObjectWriter::_inDispose
0x3a52  endfinally
0x3a53  ret
```
