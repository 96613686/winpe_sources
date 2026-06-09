# System.Xaml.XamlObjectWriter::WriteEndMember

- ea: `0x33d0`
- end: `0x3690`
- name: `System.Xaml.XamlObjectWriter::WriteEndMember`
- size: `704`
- prototype: ``
- caller_count: `0`
- callee_count: `42`
- tags: ``

## callees

- `0x19c0`
- `0x33d0`
- `0x3a60`
- `0x3b70`
- `0x3e90`
- `0x3fe0`
- `0x4110`
- `0x42a0`
- `0x4740`
- `0x4c50`
- `0x5080`
- `0x8590`
- `0x89b0`
- `0x8aa0`
- `0x8ac0`
- `0x8b20`
- `0x8b30`
- `0x8b40`
- `0x8b80`
- `0xa590`
- `0xa6e0`
- `0xb280`
- `0xd150`
- `0xd600`
- `0xef20`
- `0xefa0`
- `0xf380`
- `0x11f20`
- `0x11f50`
- `0x21200`
- `0x21590`
- `0x215d0`
- `0x21650`
- `0x21670`
- `0x21690`
- `0x216d0`
- `0x216f0`
- `0x21750`
- `0x21770`
- `0x21870`
- `0x21b90`
- `0x21c70`

## pseudocode

```c

```

## disassembly

```asm
0x33d0  ldarg.0
0x33d1  call     instance void System.Xaml.XamlObjectWriter::ThrowIfDisposed()
0x33d6  ldarg.0
0x33d7  ldfld    class System.Xaml.DeferringWriter System.Xaml.XamlObjectWriter::_deferringWriter
0x33dc  callvirt instance void System.Xaml.XamlWriter::WriteEndMember()
0x33e1  ldarg.0
0x33e2  ldfld    class System.Xaml.DeferringWriter System.Xaml.XamlObjectWriter::_deferringWriter
0x33e7  callvirt instance bool System.Xaml.DeferringWriter::get_Handled()
0x33ec  brfalse.s loc_33EF
0x33ee  ret
0x33ef  ldarg.0
0x33f0  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x33f5  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x33fa  ldnull
0x33fb  call     bool System.Xaml.XamlType::op_Equality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x3400  brfalse.s loc_3410
0x3402  ldarg.0
0x3403  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3408  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentProperty()
0x340d  stloc.0
0x340e  br.s     loc_341C
0x3410  ldarg.0
0x3411  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3416  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentProperty()
0x341b  stloc.0
0x341c  ldloc.0
0x341d  ldnull
0x341e  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x3423  brfalse.s loc_347A
0x3425  ldarg.0
0x3426  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x342b  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x3430  ldnull
0x3431  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x3436  brtrue.s loc_3444
0x3438  ldstr    aNopropertyincu_2// "NoPropertyInCurrentFrame_EM_noType"
0x343d  call     string System.Xaml.SR::Get(string id)
0x3442  br.s     loc_3467
0x3444  ldstr    aNopropertyincu_3// "NoPropertyInCurrentFrame_EM"
0x3449  ldc.i4.1
0x344a  newarr   [mscorlib]System.Object
0x344f  dup
0x3450  ldc.i4.0
0x3451  ldarg.0
0x3452  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3457  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x345c  callvirt instance string [mscorlib]System.Object::ToString()
0x3461  stelem.ref
0x3462  call     string System.Xaml.SR::Get(string id, object[] args)
0x3467  stloc.1
0x3468  ldarg.0
0x3469  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x346e  ldloc.1
0x346f  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x3474  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x3479  throw
0x347a  ldarg.0
0x347b  ldc.i4.0
0x347c  stfld    bool System.Xaml.XamlObjectWriter::_nextNodeMustBeEndMember
0x3481  ldarg.0
0x3482  ldnull
0x3483  stfld    object System.Xaml.XamlObjectWriter::_lastInstance
0x3488  ldloc.0
0x3489  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Arguments()
0x348e  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x3493  brfalse.s loc_34BA
0x3495  ldarg.0
0x3496  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x349b  ldarg.0
0x349c  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x34a1  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentCollection()
0x34a6  castclass class [mscorlib]System.Collections.Generic.List`1<object>
0x34ab  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<object>::ToArray()
0x34b0  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentCtorArgs(object[] value)
0x34b5  br       loc_3677
0x34ba  ldloc.0
0x34bb  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Initialization()
0x34c0  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x34c5  brfalse.s loc_34D8
0x34c7  ldarg.0
0x34c8  ldarg.0
0x34c9  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x34ce  call     instance void System.Xaml.XamlObjectWriter::Logic_CreateFromInitializationValue(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x34d3  br       loc_3677
0x34d8  ldloc.0
0x34d9  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Items()
0x34de  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x34e3  brfalse.s loc_34F6
0x34e5  ldarg.0
0x34e6  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x34eb  ldnull
0x34ec  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentCollection(object value)
0x34f1  br       loc_3677
0x34f6  ldloc.0
0x34f7  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_PositionalParameters()
0x34fc  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x3501  brfalse.s loc_3514
0x3503  ldarg.0
0x3504  ldarg.0
0x3505  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x350a  call     instance void System.Xaml.XamlObjectWriter::Logic_ConvertPositionalParamsToArgs(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x350f  br       loc_3677
0x3514  ldloc.0
0x3515  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Class()
0x351a  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x351f  brfalse.s loc_355F
0x3521  ldnull
0x3522  stloc.2
0x3523  ldarg.0
0x3524  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3529  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x352e  ldnull
0x352f  call     bool System.Xaml.XamlType::op_Equality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x3534  brfalse.s loc_354D
0x3536  ldarg.0
0x3537  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x353c  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x3541  stloc.2
0x3542  ldarg.0
0x3543  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3548  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::PopScope()
0x354d  ldarg.0
0x354e  ldarg.0
0x354f  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3554  ldloc.2
0x3555  call     instance void System.Xaml.XamlObjectWriter::Logic_ValidateXClass(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, object value)
0x355a  br       loc_3677
0x355f  ldarg.0
0x3560  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3565  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x356a  ldnull
0x356b  call     bool System.Xaml.XamlType::op_Equality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x3570  brfalse  loc_3677
0x3575  ldarg.0
0x3576  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x357b  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x3580  stloc.3
0x3581  ldc.i4.1
0x3582  stloc.s  4
0x3584  ldloc.3
0x3585  brfalse  loc_364B
0x358a  ldloc.3
0x358b  isinst   System.Windows.Markup.MarkupExtension
0x3590  stloc.s  5
0x3592  ldloc.s  5
0x3594  brfalse.s loc_35DE
0x3596  ldarg.0
0x3597  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x359c  ldloc.s  5
0x359e  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentInstance(object value)
0x35a3  ldarg.0
0x35a4  ldloc.3
0x35a5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x35aa  call     instance class System.Xaml.XamlType System.Xaml.XamlObjectWriter::GetXamlType(class [mscorlib]System.Type clrType)
0x35af  stloc.s  6
0x35b1  ldloc.0
0x35b2  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x35b7  callvirt instance bool System.Xaml.XamlType::get_IsMarkupExtension()
0x35bc  brfalse.s loc_35CD
0x35be  ldloc.s  6
0x35c0  ldloc.0
0x35c1  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x35c6  callvirt instance bool System.Xaml.XamlType::CanAssignTo(class System.Xaml.XamlType xamlType)
0x35cb  brtrue.s loc_364B
0x35cd  ldarg.0
0x35ce  ldarg.0
0x35cf  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x35d4  call     instance void System.Xaml.XamlObjectWriter::Logic_AssignProvidedValue(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x35d9  ldc.i4.0
0x35da  stloc.s  4
0x35dc  br.s     loc_364B
0x35de  ldarg.0
0x35df  ldloc.3
0x35e0  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x35e5  call     instance class System.Xaml.XamlType System.Xaml.XamlObjectWriter::GetXamlType(class [mscorlib]System.Type clrType)
0x35ea  stloc.s  7
0x35ec  ldloc.s  7
0x35ee  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_String()
0x35f3  call     bool System.Xaml.XamlType::op_Equality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x35f8  brtrue.s loc_3609
0x35fa  ldloc.s  7
0x35fc  ldloc.0
0x35fd  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x3602  callvirt instance bool System.Xaml.XamlType::CanAssignTo(class System.Xaml.XamlType xamlType)
0x3607  brtrue.s loc_364B
0x3609  ldloc.0
0x360a  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0x360f  brfalse.s loc_363D
0x3611  ldloc.0
0x3612  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Key()
0x3617  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x361c  brfalse.s loc_363D
0x361e  ldarg.0
0x361f  ldarg.0
0x3620  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3625  call     instance bool System.Xaml.XamlObjectWriter::Logic_ShouldConvertKey(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x362a  brtrue.s loc_363D
0x362c  ldc.i4.1
0x362d  stloc.s  4
0x362f  ldarg.0
0x3630  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3635  ldc.i4.1
0x3636  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_ParentKeyIsUnconverted(bool value)
0x363b  br.s     loc_364B
0x363d  ldarg.0
0x363e  ldarg.0
0x363f  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3644  call     instance bool System.Xaml.XamlObjectWriter::Logic_CreatePropertyValueFromValue(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x3649  stloc.s  4
0x364b  ldarg.0
0x364c  ldarg.0
0x364d  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3652  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x3657  stfld    object System.Xaml.XamlObjectWriter::_lastInstance
0x365c  ldloc.s  4
0x365e  brfalse.s loc_366C
0x3660  ldarg.0
0x3661  ldarg.0
0x3662  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3667  call     instance void System.Xaml.XamlObjectWriter::Logic_DoAssignmentToParentProperty(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x366c  ldarg.0
0x366d  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3672  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::PopScope()
0x3677  ldarg.0
0x3678  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x367d  ldnull
0x367e  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentProperty(class System.Xaml.XamlMember value)
0x3683  ldarg.0
0x3684  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3689  ldc.i4.0
0x368a  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentIsPropertyValueSet(bool value)
0x368f  ret
```
