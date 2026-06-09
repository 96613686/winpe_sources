# System.Xaml.XamlObjectWriter::WriteValue

- ea: `0x3690`
- end: `0x381e`
- name: `System.Xaml.XamlObjectWriter::WriteValue`
- size: `398`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: ``

## callees

- `0x19c0`
- `0x19d0`
- `0x19e0`
- `0x3690`
- `0x3a60`
- `0x4940`
- `0x7580`
- `0x8590`
- `0x8b80`
- `0x8c50`
- `0xa590`
- `0xa6e0`
- `0xb280`
- `0xd110`
- `0xd130`
- `0xefa0`
- `0xf390`
- `0x11f50`
- `0x12dc0`
- `0x21200`
- `0x21540`
- `0x21590`
- `0x215d0`
- `0x215f0`
- `0x21650`
- `0x216f0`

## pseudocode

```c

```

## disassembly

```asm
0x3690  ldarg.0
0x3691  call     instance void System.Xaml.XamlObjectWriter::ThrowIfDisposed()
0x3696  ldarg.0
0x3697  ldfld    class System.Xaml.DeferringWriter System.Xaml.XamlObjectWriter::_deferringWriter
0x369c  ldarg.1
0x369d  callvirt instance void System.Xaml.XamlWriter::WriteValue(object value)
0x36a2  ldarg.0
0x36a3  ldfld    class System.Xaml.DeferringWriter System.Xaml.XamlObjectWriter::_deferringWriter
0x36a8  callvirt instance bool System.Xaml.DeferringWriter::get_Handled()
0x36ad  brfalse.s loc_36E6
0x36af  ldarg.0
0x36b0  ldfld    class System.Xaml.DeferringWriter System.Xaml.XamlObjectWriter::_deferringWriter
0x36b5  callvirt instance valuetype System.Xaml.DeferringMode System.Xaml.DeferringWriter::get_Mode()
0x36ba  ldc.i4.3
0x36bb  bne.un.s loc_36E5
0x36bd  ldarg.0
0x36be  ldfld    class System.Xaml.DeferringWriter System.Xaml.XamlObjectWriter::_deferringWriter
0x36c3  callvirt instance class System.Xaml.XamlNodeList System.Xaml.DeferringWriter::CollectTemplateList()
0x36c8  stloc.2
0x36c9  ldarg.0
0x36ca  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x36cf  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::PushScope()
0x36d4  ldarg.0
0x36d5  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x36da  ldloc.2
0x36db  callvirt instance class System.Xaml.XamlReader System.Xaml.XamlNodeList::GetReader()
0x36e0  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentInstance(object value)
0x36e5  ret
0x36e6  ldarg.0
0x36e7  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x36ec  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentProperty()
0x36f1  stloc.0
0x36f2  ldloc.0
0x36f3  ldnull
0x36f4  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x36f9  brfalse.s loc_375E
0x36fb  ldarg.0
0x36fc  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3701  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x3706  ldnull
0x3707  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x370c  brtrue.s loc_3724
0x370e  ldstr    aNopropertyincu_4// "NoPropertyInCurrentFrame_V_noType"
0x3713  ldc.i4.1
0x3714  newarr   [mscorlib]System.Object
0x3719  dup
0x371a  ldc.i4.0
0x371b  ldarg.1
0x371c  stelem.ref
0x371d  call     string System.Xaml.SR::Get(string id, object[] args)
0x3722  br.s     loc_374B
0x3724  ldstr    aNopropertyincu_5// "NoPropertyInCurrentFrame_V"
0x3729  ldc.i4.2
0x372a  newarr   [mscorlib]System.Object
0x372f  dup
0x3730  ldc.i4.0
0x3731  ldarg.1
0x3732  stelem.ref
0x3733  dup
0x3734  ldc.i4.1
0x3735  ldarg.0
0x3736  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x373b  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x3740  callvirt instance string [mscorlib]System.Object::ToString()
0x3745  stelem.ref
0x3746  call     string System.Xaml.SR::Get(string id, object[] args)
0x374b  stloc.3
0x374c  ldarg.0
0x374d  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3752  ldloc.3
0x3753  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x3758  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x375d  throw
0x375e  ldarg.0
0x375f  ldnull
0x3760  stfld    object System.Xaml.XamlObjectWriter::_lastInstance
0x3765  ldarg.0
0x3766  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x376b  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::PushScope()
0x3770  ldarg.0
0x3771  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3776  ldarg.1
0x3777  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentInstance(object value)
0x377c  ldloc.0
0x377d  stloc.1
0x377e  ldnull
0x377f  stloc.0
0x3780  ldarg.0
0x3781  ldc.i4.1
0x3782  stfld    bool System.Xaml.XamlObjectWriter::_nextNodeMustBeEndMember
0x3787  ldloc.1
0x3788  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0x378d  brfalse  loc_381D
0x3792  ldloc.1
0x3793  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x3798  stloc.s  4
0x379a  ldloc.s  4
0x379c  callvirt instance bool System.Xaml.XamlType::get_IsCollection()
0x37a1  brtrue.s loc_37AC
0x37a3  ldloc.s  4
0x37a5  callvirt instance bool System.Xaml.XamlType::get_IsDictionary()
0x37aa  brfalse.s loc_381D
0x37ac  ldarg.0
0x37ad  ldc.i4.0
0x37ae  stfld    bool System.Xaml.XamlObjectWriter::_nextNodeMustBeEndMember
0x37b3  ldloc.1
0x37b4  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_PositionalParameters()
0x37b9  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x37be  brfalse.s loc_37FA
0x37c0  ldarg.0
0x37c1  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x37c6  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_PositionalParameterDescriptor()
0x37cb  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentType(class System.Xaml.XamlType value)
0x37d0  ldarg.0
0x37d1  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x37d6  ldarg.1
0x37d7  ldc.i4.1
0x37d8  newobj   instance void System.Xaml.MS.Impl.PositionalParameterDescriptor::.ctor(object value, bool wasText)
0x37dd  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentInstance(object value)
0x37e2  ldarg.0
0x37e3  ldarg.0
0x37e4  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x37e9  call     instance void System.Xaml.XamlObjectWriter::Logic_DoAssignmentToParentCollection(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x37ee  ldarg.0
0x37ef  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x37f4  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::PopScope()
0x37f9  ret
0x37fa  ldarg.0
0x37fb  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3800  ldarg.1
0x3801  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentInstance(object value)
0x3806  ldarg.0
0x3807  ldarg.0
0x3808  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x380d  call     instance void System.Xaml.XamlObjectWriter::Logic_DoAssignmentToParentCollection(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x3812  ldarg.0
0x3813  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3818  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::PopScope()
0x381d  ret
```
