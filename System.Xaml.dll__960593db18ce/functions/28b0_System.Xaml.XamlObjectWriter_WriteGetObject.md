# System.Xaml.XamlObjectWriter::WriteGetObject

- ea: `0x28b0`
- end: `0x2a8b`
- name: `System.Xaml.XamlObjectWriter::WriteGetObject`
- size: `475`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: ``

## callees

- `0x19c0`
- `0x2870`
- `0x2880`
- `0x28b0`
- `0x3a60`
- `0x8590`
- `0xa4c0`
- `0xa590`
- `0xb280`
- `0xd110`
- `0xd130`
- `0xef20`
- `0xefa0`
- `0xf340`
- `0x11f20`
- `0x11f50`
- `0x202a0`
- `0x21200`
- `0x21540`
- `0x215a0`
- `0x215d0`
- `0x215f0`
- `0x21610`
- `0x21650`
- `0x21690`
- `0x216f0`
- `0x21710`
- `0x21770`
- `0x21810`

## pseudocode

```c

```

## disassembly

```asm
0x28b0  ldarg.0
0x28b1  call     instance void System.Xaml.XamlObjectWriter::ThrowIfDisposed()
0x28b6  ldarg.0
0x28b7  ldfld    class System.Xaml.DeferringWriter System.Xaml.XamlObjectWriter::_deferringWriter
0x28bc  callvirt instance void System.Xaml.XamlWriter::WriteGetObject()
0x28c1  ldarg.0
0x28c2  ldfld    class System.Xaml.DeferringWriter System.Xaml.XamlObjectWriter::_deferringWriter
0x28c7  callvirt instance bool System.Xaml.DeferringWriter::get_Handled()
0x28cc  brfalse.s loc_28CF
0x28ce  ret
0x28cf  ldarg.0
0x28d0  ldfld    bool System.Xaml.XamlObjectWriter::_nextNodeMustBeEndMember
0x28d5  brfalse.s loc_28F4
0x28d7  ldstr    aValuemustbefol// "ValueMustBeFollowedByEndMember"
0x28dc  call     string System.Xaml.SR::Get(string id)
0x28e1  stloc.3
0x28e2  ldarg.0
0x28e3  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x28e8  ldloc.3
0x28e9  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x28ee  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x28f3  throw
0x28f4  ldarg.0
0x28f5  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x28fa  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x28ff  ldnull
0x2900  call     bool System.Xaml.XamlType::op_Equality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x2905  brfalse.s loc_2915
0x2907  ldarg.0
0x2908  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x290d  callvirt instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_Depth()
0x2912  ldc.i4.1
0x2913  bgt.s    loc_2922
0x2915  ldarg.0
0x2916  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x291b  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentProperty()
0x2920  br.s     loc_292D
0x2922  ldarg.0
0x2923  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2928  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentProperty()
0x292d  stloc.0
0x292e  ldloc.0
0x292f  ldnull
0x2930  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x2935  brfalse  loc_29BA
0x293a  ldarg.0
0x293b  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2940  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x2945  ldnull
0x2946  call     bool System.Xaml.XamlType::op_Equality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x294b  brfalse.s loc_295B
0x294d  ldarg.0
0x294e  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2953  callvirt instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_Depth()
0x2958  ldc.i4.1
0x2959  bgt.s    loc_2968
0x295b  ldarg.0
0x295c  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2961  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x2966  br.s     loc_2973
0x2968  ldarg.0
0x2969  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x296e  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentType()
0x2973  stloc.s  4
0x2975  ldloc.s  4
0x2977  ldnull
0x2978  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x297d  brtrue.s loc_298B
0x297f  ldstr    aNopropertyincu// "NoPropertyInCurrentFrame_GO_noType"
0x2984  call     string System.Xaml.SR::Get(string id)
0x2989  br.s     loc_29A5
0x298b  ldstr    aNopropertyincu_0// "NoPropertyInCurrentFrame_GO"
0x2990  ldc.i4.1
0x2991  newarr   [mscorlib]System.Object
0x2996  dup
0x2997  ldc.i4.0
0x2998  ldloc.s  4
0x299a  callvirt instance string [mscorlib]System.Object::ToString()
0x299f  stelem.ref
0x29a0  call     string System.Xaml.SR::Get(string id, object[] args)
0x29a5  stloc.s  5
0x29a7  ldarg.0
0x29a8  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x29ad  ldloc.s  5
0x29af  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x29b4  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x29b9  throw
0x29ba  ldarg.0
0x29bb  ldnull
0x29bc  stfld    object System.Xaml.XamlObjectWriter::_lastInstance
0x29c1  ldarg.0
0x29c2  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x29c7  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x29cc  ldnull
0x29cd  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x29d2  brfalse.s loc_29DF
0x29d4  ldarg.0
0x29d5  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x29da  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::PushScope()
0x29df  ldarg.0
0x29e0  ldarg.0
0x29e1  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x29e6  call     instance void System.Xaml.XamlObjectWriter::TryCreateParentInstance(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x29eb  ldarg.0
0x29ec  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x29f1  ldc.i4.1
0x29f2  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentIsObjectFromMember(bool value)
0x29f7  ldarg.0
0x29f8  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x29fd  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentInstance()
0x2a02  stloc.1
0x2a03  ldarg.0
0x2a04  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2a09  ldloc.0
0x2a0a  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x2a0f  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentType(class System.Xaml.XamlType value)
0x2a14  ldarg.0
0x2a15  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x2a1a  ldloc.1
0x2a1b  ldloc.0
0x2a1c  callvirt instance object MS.Internal.Xaml.Runtime.XamlRuntime::GetValue(object obj, class System.Xaml.XamlMember property)
0x2a21  stloc.2
0x2a22  ldloc.2
0x2a23  brtrue.s loc_2A58
0x2a25  ldarg.0
0x2a26  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2a2b  ldstr    aGetobjectnull// "GetObjectNull"
0x2a30  ldc.i4.2
0x2a31  newarr   [mscorlib]System.Object
0x2a36  dup
0x2a37  ldc.i4.0
0x2a38  ldloc.1
0x2a39  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2a3e  stelem.ref
0x2a3f  dup
0x2a40  ldc.i4.1
0x2a41  ldloc.0
0x2a42  callvirt instance string System.Xaml.XamlMember::get_Name()
0x2a47  stelem.ref
0x2a48  call     string System.Xaml.SR::Get(string id, object[] args)
0x2a4d  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x2a52  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x2a57  throw
0x2a58  ldarg.0
0x2a59  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2a5e  ldloc.2
0x2a5f  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentInstance(object value)
0x2a64  ldloc.0
0x2a65  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x2a6a  callvirt instance bool System.Xaml.XamlType::get_IsCollection()
0x2a6f  brtrue.s loc_2A7E
0x2a71  ldloc.0
0x2a72  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x2a77  callvirt instance bool System.Xaml.XamlType::get_IsDictionary()
0x2a7c  brfalse.s loc_2A8A
0x2a7e  ldarg.0
0x2a7f  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2a84  ldloc.2
0x2a85  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentCollection(object value)
0x2a8a  ret
```
