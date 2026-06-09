# System.Xaml.XamlObjectWriter::WriteStartMember

- ea: `0x30c0`
- end: `0x33d0`
- name: `System.Xaml.XamlObjectWriter::WriteStartMember`
- size: `784`
- prototype: ``
- caller_count: `0`
- callee_count: `35`
- tags: ``

## callees

- `0x19c0`
- `0x2870`
- `0x30c0`
- `0x3a60`
- `0x3bb0`
- `0x3c00`
- `0x3c40`
- `0x3c80`
- `0x4470`
- `0x8590`
- `0x8b20`
- `0x8b80`
- `0x8be0`
- `0xa440`
- `0xa4c0`
- `0xa590`
- `0xa6c0`
- `0xa6e0`
- `0xb280`
- `0xb2f0`
- `0xd110`
- `0xd130`
- `0xef20`
- `0xf370`
- `0x11f20`
- `0x11f50`
- `0x20200`
- `0x20d10`
- `0x21200`
- `0x215d0`
- `0x21650`
- `0x21670`
- `0x216d0`
- `0x21770`
- `0x218d0`

## string_xrefs

- `0x3179`: `OpenPropertyInCurrentFrame_SM`

## pseudocode

```c

```

## disassembly

```asm
0x30c0  ldarg.0
0x30c1  call     instance void System.Xaml.XamlObjectWriter::ThrowIfDisposed()
0x30c6  ldarg.1
0x30c7  ldnull
0x30c8  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x30cd  brfalse.s loc_30DA
0x30cf  ldstr    aProperty// "property"
0x30d4  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x30d9  throw
0x30da  ldarg.0
0x30db  ldfld    class System.Xaml.DeferringWriter System.Xaml.XamlObjectWriter::_deferringWriter
0x30e0  ldarg.1
0x30e1  callvirt instance void System.Xaml.XamlWriter::WriteStartMember(class System.Xaml.XamlMember xamlMember)
0x30e6  ldarg.0
0x30e7  ldfld    class System.Xaml.DeferringWriter System.Xaml.XamlObjectWriter::_deferringWriter
0x30ec  callvirt instance bool System.Xaml.DeferringWriter::get_Handled()
0x30f1  brfalse.s loc_30F4
0x30f3  ret
0x30f4  ldnull
0x30f5  stloc.0
0x30f6  ldarg.0
0x30f7  ldfld    bool System.Xaml.XamlObjectWriter::_nextNodeMustBeEndMember
0x30fc  brfalse.s loc_310E
0x30fe  ldstr    aValuemustbefol// "ValueMustBeFollowedByEndMember"
0x3103  call     string System.Xaml.SR::Get(string id)
0x3108  stloc.0
0x3109  br       loc_31E8
0x310e  ldarg.1
0x310f  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_UnknownContent()
0x3114  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x3119  brfalse.s loc_313F
0x311b  ldstr    aTypehasnoconte// "TypeHasNoContentProperty"
0x3120  ldc.i4.1
0x3121  newarr   [mscorlib]System.Object
0x3126  dup
0x3127  ldc.i4.0
0x3128  ldarg.0
0x3129  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x312e  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x3133  stelem.ref
0x3134  call     string System.Xaml.SR::Get(string id, object[] args)
0x3139  stloc.0
0x313a  br       loc_31E8
0x313f  ldarg.1
0x3140  callvirt instance bool System.Xaml.XamlMember::get_IsUnknown()
0x3145  brfalse.s loc_3166
0x3147  ldstr    aCantsetunknown// "CantSetUnknownProperty"
0x314c  ldc.i4.1
0x314d  newarr   [mscorlib]System.Object
0x3152  dup
0x3153  ldc.i4.0
0x3154  ldarg.1
0x3155  callvirt instance string [mscorlib]System.Object::ToString()
0x315a  stelem.ref
0x315b  call     string System.Xaml.SR::Get(string id, object[] args)
0x3160  stloc.0
0x3161  br       loc_31E8
0x3166  ldarg.0
0x3167  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x316c  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentProperty()
0x3171  ldnull
0x3172  call     bool System.Xaml.XamlMember::op_Inequality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x3177  brfalse.s loc_31BB
0x3179  ldstr    aOpenpropertyin_0// "OpenPropertyInCurrentFrame_SM"
0x317e  ldc.i4.3
0x317f  newarr   [mscorlib]System.Object
0x3184  dup
0x3185  ldc.i4.0
0x3186  ldarg.0
0x3187  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x318c  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x3191  callvirt instance string [mscorlib]System.Object::ToString()
0x3196  stelem.ref
0x3197  dup
0x3198  ldc.i4.1
0x3199  ldarg.0
0x319a  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x319f  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentProperty()
0x31a4  callvirt instance string [mscorlib]System.Object::ToString()
0x31a9  stelem.ref
0x31aa  dup
0x31ab  ldc.i4.2
0x31ac  ldarg.1
0x31ad  callvirt instance string [mscorlib]System.Object::ToString()
0x31b2  stelem.ref
0x31b3  call     string System.Xaml.SR::Get(string id, object[] args)
0x31b8  stloc.0
0x31b9  br.s     loc_31E8
0x31bb  ldarg.0
0x31bc  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x31c1  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x31c6  ldnull
0x31c7  call     bool System.Xaml.XamlType::op_Equality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x31cc  brfalse.s loc_31E8
0x31ce  ldstr    aNotypeincurren_0// "NoTypeInCurrentFrame_SM"
0x31d3  ldc.i4.1
0x31d4  newarr   [mscorlib]System.Object
0x31d9  dup
0x31da  ldc.i4.0
0x31db  ldarg.1
0x31dc  callvirt instance string [mscorlib]System.Object::ToString()
0x31e1  stelem.ref
0x31e2  call     string System.Xaml.SR::Get(string id, object[] args)
0x31e7  stloc.0
0x31e8  ldloc.0
0x31e9  brfalse.s loc_31FD
0x31eb  ldarg.0
0x31ec  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x31f1  ldloc.0
0x31f2  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x31f7  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x31fc  throw
0x31fd  ldarg.0
0x31fe  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3203  ldarg.1
0x3204  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentProperty(class System.Xaml.XamlMember value)
0x3209  ldarg.0
0x320a  ldarg.0
0x320b  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3210  ldarg.1
0x3211  ldc.i4.0
0x3212  call     instance void System.Xaml.XamlObjectWriter::Logic_DuplicatePropertyCheck(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, class System.Xaml.XamlMember property, bool onParent)
0x3217  ldarg.0
0x3218  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x321d  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x3222  brtrue.s loc_3286
0x3224  ldarg.0
0x3225  ldarg.0
0x3226  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x322b  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentProperty()
0x3230  call     instance bool System.Xaml.XamlObjectWriter::IsConstructionDirective(class System.Xaml.XamlMember xamlMember)
0x3235  brtrue.s loc_3261
0x3237  ldarg.0
0x3238  ldarg.0
0x3239  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x323e  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentProperty()
0x3243  ldarg.0
0x3244  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3249  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x324e  call     instance bool System.Xaml.XamlObjectWriter::IsDirectiveAllowedOnNullInstance(class System.Xaml.XamlMember xamlMember, class System.Xaml.XamlType xamlType)
0x3253  brtrue.s loc_3261
0x3255  ldarg.0
0x3256  ldarg.0
0x3257  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x325c  call     instance void System.Xaml.XamlObjectWriter::Logic_CreateAndAssignToParentStart(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x3261  ldarg.1
0x3262  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_PositionalParameters()
0x3267  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x326c  brfalse  loc_3379
0x3271  ldarg.0
0x3272  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3277  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xaml.MS.Impl.PositionalParameterDescriptor>::.ctor()
0x327c  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentCollection(object value)
0x3281  br       loc_3379
0x3286  ldarg.0
0x3287  ldarg.1
0x3288  call     instance bool System.Xaml.XamlObjectWriter::IsTextConstructionDirective(class System.Xaml.XamlMember xamlMember)
0x328d  brfalse.s loc_32B9
0x328f  ldarg.0
0x3290  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3295  ldstr    aLateconstructi// "LateConstructionDirective"
0x329a  ldc.i4.1
0x329b  newarr   [mscorlib]System.Object
0x32a0  dup
0x32a1  ldc.i4.0
0x32a2  ldarg.1
0x32a3  callvirt instance string System.Xaml.XamlMember::get_Name()
0x32a8  stelem.ref
0x32a9  call     string System.Xaml.SR::Get(string id, object[] args)
0x32ae  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x32b3  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x32b8  throw
0x32b9  ldarg.0
0x32ba  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x32bf  callvirt instance bool MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentIsTypeConvertedObject()
0x32c4  brfalse  loc_3379
0x32c9  ldarg.1
0x32ca  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0x32cf  brtrue.s loc_3303
0x32d1  ldarg.1
0x32d2  callvirt instance bool System.Xaml.XamlMember::get_IsAttachable()
0x32d7  brtrue.s loc_3303
0x32d9  ldarg.0
0x32da  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x32df  ldstr    aSettingpropert// "SettingPropertiesIsNotAllowed"
0x32e4  ldc.i4.1
0x32e5  newarr   [mscorlib]System.Object
0x32ea  dup
0x32eb  ldc.i4.0
0x32ec  ldarg.1
0x32ed  callvirt instance string System.Xaml.XamlMember::get_Name()
0x32f2  stelem.ref
0x32f3  call     string System.Xaml.SR::Get(string id, object[] args)
0x32f8  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x32fd  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x3302  throw
0x3303  ldarg.1
0x3304  callvirt instance bool System.Xaml.XamlMember::get_IsAttachable()
0x3309  brfalse.s loc_3379
0x330b  ldarg.0
0x330c  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3311  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x3316  isinst   MS.Internal.Xaml.Context.NameFixupToken
0x331b  brfalse.s loc_3379
0x331d  ldarg.0
0x331e  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3323  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x3328  castclass MS.Internal.Xaml.Context.NameFixupToken
0x332d  stloc.1
0x332e  ldarg.0
0x332f  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3334  ldstr    aAttachedpropon// "AttachedPropOnFwdRefTC"
0x3339  ldc.i4.3
0x333a  newarr   [mscorlib]System.Object
0x333f  dup
0x3340  ldc.i4.0
0x3341  ldarg.1
0x3342  stelem.ref
0x3343  dup
0x3344  ldc.i4.1
0x3345  ldarg.0
0x3346  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x334b  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x3350  stelem.ref
0x3351  dup
0x3352  ldc.i4.2
0x3353  ldstr    asc_3787C// ", "
0x3358  ldloc.1
0x3359  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> MS.Internal.Xaml.Context.NameFixupToken::get_NeededNames()
0x335e  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x3363  call     string [mscorlib]System.String::Join(string, string[])
0x3368  stelem.ref
0x3369  call     string System.Xaml.SR::Get(string id, object[] args)
0x336e  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x3373  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x3378  throw
0x3379  ldarg.1
0x337a  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0x337f  brfalse.s loc_33CF
0x3381  ldarg.1
0x3382  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Items()
0x3387  call     bool System.Xaml.XamlMember::op_Inequality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x338c  brfalse.s loc_33CF
0x338e  ldarg.1
0x338f  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_PositionalParameters()
0x3394  call     bool System.Xaml.XamlMember::op_Inequality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x3399  brfalse.s loc_33CF
0x339b  ldarg.1
0x339c  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x33a1  stloc.2
0x33a2  ldloc.2
0x33a3  callvirt instance bool System.Xaml.XamlType::get_IsCollection()
0x33a8  brtrue.s loc_33B2
0x33aa  ldloc.2
0x33ab  callvirt instance bool System.Xaml.XamlType::get_IsDictionary()
0x33b0  brfalse.s loc_33CF
0x33b2  ldarg.0
0x33b3  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x33b8  ldarg.0
0x33b9  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x33be  ldarg.1
0x33bf  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x33c4  ldnull
0x33c5  callvirt instance object MS.Internal.Xaml.Runtime.XamlRuntime::CreateInstance(class System.Xaml.XamlType xamlType, object[] args)
0x33ca  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentCollection(object value)
0x33cf  ret
```
