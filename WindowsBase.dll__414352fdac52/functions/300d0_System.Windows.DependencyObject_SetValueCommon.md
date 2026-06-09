# System.Windows.DependencyObject::SetValueCommon

- ea: `0x300d0`
- end: `0x3037b`
- name: `System.Windows.DependencyObject::SetValueCommon`
- size: `683`
- prototype: ``
- caller_count: `8`
- callee_count: `38`
- tags: `broker_com_uri`

## callers

- `0x2ff20`
- `0x2ff40`
- `0x2ff80`
- `0x2ffa0`
- `0x2ffc0`
- `0x2ffe0`
- `0x30000`
- `0x30030`

## callees

- `0x2c100`
- `0x2c130`
- `0x2fa30`
- `0x2fb80`
- `0x2fbf0`
- `0x300d0`
- `0x304c0`
- `0x30760`
- `0x30db0`
- `0x315e0`
- `0x316f0`
- `0x31cd0`
- `0x31d20`
- `0x32020`
- `0x321b0`
- `0x32290`
- `0x32df0`
- `0x32e40`
- `0x32e50`
- `0x32ee0`
- `0x32f50`
- `0x34230`
- `0x34270`
- `0x34510`
- `0x345a0`
- `0x34620`
- `0x34630`
- `0x34840`
- `0x34aa0`
- `0x34ab0`
- `0x34b90`
- `0x34bb0`
- `0x34bc0`
- `0x34bd0`
- `0x34c60`
- `0x34cd0`
- `0x34ce0`
- `0x384e0`

## string_xrefs

- `0x300d8`: `SetOnReadOnlyObjectNotAllowed`

## pseudocode

```c

```

## disassembly

```asm
0x300d0  ldarg.0
0x300d1  call     instance bool System.Windows.DependencyObject::get_IsSealed()
0x300d6  brfalse.s loc_300F2
0x300d8  ldstr    aSetonreadonlyo// "SetOnReadOnlyObjectNotAllowed"
0x300dd  ldc.i4.1
0x300de  newarr   [mscorlib]System.Object
0x300e3  dup
0x300e4  ldc.i4.0
0x300e5  ldarg.0
0x300e6  stelem.ref
0x300e7  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x300ec  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x300f1  throw
0x300f2  ldnull
0x300f3  stloc.0
0x300f4  ldnull
0x300f5  stloc.1
0x300f6  ldarg.0
0x300f7  ldarg.1
0x300f8  callvirt instance int32 System.Windows.DependencyProperty::get_GlobalIndex()
0x300fd  call     instance valuetype System.Windows.EntryIndex System.Windows.DependencyObject::LookupEntry(int32 targetIndex)
0x30102  stloc.2
0x30103  ldarg.2
0x30104  ldsfld   object System.Windows.DependencyProperty::UnsetValue
0x30109  bne.un.s loc_30115
0x3010b  ldarg.0
0x3010c  ldloc.2
0x3010d  ldarg.1
0x3010e  ldarg.3
0x3010f  call     instance void System.Windows.DependencyObject::ClearValueCommon(valuetype System.Windows.EntryIndex entryIndex, class System.Windows.DependencyProperty dp, class System.Windows.PropertyMetadata metadata)
0x30114  ret
0x30115  ldc.i4.0
0x30116  stloc.3
0x30117  ldarg.2
0x30118  ldsfld   object System.Windows.DependencyObject::ExpressionInAlternativeStore
0x3011d  ceq
0x3011f  stloc.s  4
0x30121  ldloc.s  4
0x30123  brtrue   loc_301B1
0x30128  ldarg.s  7
0x3012a  brtrue.s loc_30135
0x3012c  ldarg.1
0x3012d  ldarg.2
0x3012e  callvirt instance bool System.Windows.DependencyProperty::IsValidValue(object value)
0x30133  br.s     loc_3013C
0x30135  ldarg.1
0x30136  ldarg.2
0x30137  callvirt instance bool System.Windows.DependencyProperty::IsValidValueInternal(object value)
0x3013c  stloc.s  9
0x3013e  ldloc.s  9
0x30140  brfalse.s loc_3014A
0x30142  ldarg.1
0x30143  callvirt instance bool System.Windows.DependencyProperty::get_IsObjectType()
0x30148  brfalse.s loc_301B1
0x3014a  ldarg.2
0x3014b  isinst   System.Windows.Expression
0x30150  stloc.0
0x30151  ldloc.0
0x30152  brfalse.s loc_3017D
0x30154  ldloc.0
0x30155  callvirt instance bool System.Windows.Expression::get_Attachable()
0x3015a  brtrue.s loc_3016C
0x3015c  ldstr    aSharingnonshar// "SharingNonSharableExpression"
0x30161  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x30166  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3016b  throw
0x3016c  ldloc.0
0x3016d  callvirt instance class System.Windows.DependencySource[] System.Windows.Expression::GetSources()
0x30172  stloc.1
0x30173  ldarg.0
0x30174  ldloc.1
0x30175  ldloc.0
0x30176  call     void System.Windows.DependencyObject::ValidateSources(class System.Windows.DependencyObject d, class System.Windows.DependencySource[] newSources, class System.Windows.Expression expr)
0x3017b  br.s     loc_301B1
0x3017d  ldarg.2
0x3017e  isinst   System.Windows.DeferredReference
0x30183  ldnull
0x30184  cgt.un
0x30186  stloc.3
0x30187  ldloc.3
0x30188  brtrue.s loc_301B1
0x3018a  ldloc.s  9
0x3018c  brtrue.s loc_301B1
0x3018e  ldstr    aInvalidpropert_0// "InvalidPropertyValue"
0x30193  ldc.i4.2
0x30194  newarr   [mscorlib]System.Object
0x30199  dup
0x3019a  ldc.i4.0
0x3019b  ldarg.2
0x3019c  stelem.ref
0x3019d  dup
0x3019e  ldc.i4.1
0x3019f  ldarg.1
0x301a0  callvirt instance string System.Windows.DependencyProperty::get_Name()
0x301a5  stelem.ref
0x301a6  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x301ab  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x301b0  throw
0x301b1  ldarg.s  6
0x301b3  ldc.i4.4
0x301b4  bne.un.s loc_301C9
0x301b6  ldloca.s 5
0x301b8  ldarg.1
0x301b9  ldc.i4.1
0x301ba  call     instance void System.Windows.EffectiveValueEntry::.ctor(class System.Windows.DependencyProperty dp, valuetype System.Windows.BaseValueSourceInternal valueSource)
0x301bf  ldloca.s 5
0x301c1  ldarg.2
0x301c2  call     instance void System.Windows.EffectiveValueEntry::set_Value(object value)
0x301c7  br.s     loc_301D6
0x301c9  ldarg.0
0x301ca  ldloc.2
0x301cb  ldarg.1
0x301cc  ldarg.3
0x301cd  ldc.i4.s 0x10
0x301cf  call     instance valuetype System.Windows.EffectiveValueEntry System.Windows.DependencyObject::GetValueEntry(valuetype System.Windows.EntryIndex entryIndex, class System.Windows.DependencyProperty dp, class System.Windows.PropertyMetadata metadata, valuetype System.Windows.RequestFlags requests)
0x301d4  stloc.s  5
0x301d6  ldloca.s 5
0x301d8  call     instance bool System.Windows.EffectiveValueEntry::get_HasExpressionMarker()
0x301dd  brtrue.s loc_301F9
0x301df  ldloca.s 5
0x301e1  call     instance bool System.Windows.EffectiveValueEntry::get_IsExpression()
0x301e6  brtrue.s loc_301EB
0x301e8  ldnull
0x301e9  br.s     loc_30206
0x301eb  ldloca.s 5
0x301ed  call     instance object System.Windows.EffectiveValueEntry::get_LocalValue()
0x301f2  isinst   System.Windows.Expression
0x301f7  br.s     loc_30206
0x301f9  ldsfld   class System.Windows.AlternativeExpressionStorageCallback System.Windows.DependencyObject::_getExpressionCore
0x301fe  ldarg.0
0x301ff  ldarg.1
0x30200  ldarg.3
0x30201  callvirt instance class System.Windows.Expression System.Windows.AlternativeExpressionStorageCallback::Invoke(class System.Windows.DependencyObject d, class System.Windows.DependencyProperty dp, class System.Windows.PropertyMetadata metadata)
0x30206  stloc.s  6
0x30208  ldc.i4.0
0x30209  stloc.s  7
0x3020b  ldloc.s  6
0x3020d  brfalse.s loc_3023E
0x3020f  ldloc.0
0x30210  brtrue.s loc_3023E
0x30212  ldloc.3
0x30213  brfalse.s loc_30224
0x30215  ldarg.2
0x30216  castclass System.Windows.DeferredReference
0x3021b  ldc.i4.s 0xB
0x3021d  callvirt instance object System.Windows.DeferredReference::GetValue(valuetype System.Windows.BaseValueSourceInternal valueSource)
0x30222  starg.s  2
0x30224  ldloc.s  6
0x30226  ldarg.0
0x30227  ldarg.1
0x30228  ldarg.2
0x30229  callvirt instance bool System.Windows.Expression::SetValue(class System.Windows.DependencyObject d, class System.Windows.DependencyProperty dp, object value)
0x3022e  stloc.s  7
0x30230  ldarg.0
0x30231  ldloc.2
0x30232  ldarg.1
0x30233  callvirt instance int32 System.Windows.DependencyProperty::get_GlobalIndex()
0x30238  call     instance valuetype System.Windows.EntryIndex System.Windows.DependencyObject::CheckEntryIndex(valuetype System.Windows.EntryIndex entryIndex, int32 targetIndex)
0x3023d  stloc.2
0x3023e  ldloc.s  7
0x30240  brfalse.s loc_30279
0x30242  ldloca.s 2
0x30244  call     instance bool System.Windows.EntryIndex::get_Found()
0x30249  brfalse.s loc_30261
0x3024b  ldarg.0
0x3024c  ldfld    valuetype System.Windows.EffectiveValueEntry[] System.Windows.DependencyObject::_effectiveValues
0x30251  ldloca.s 2
0x30253  call     instance unsigned int32 System.Windows.EntryIndex::get_Index()
0x30258  ldelem   System.Windows.EffectiveValueEntry
0x3025d  stloc.s  8
0x3025f  br.s     loc_30271
0x30261  ldarg.1
0x30262  ldarg.3
0x30263  ldarg.0
0x30264  ldarg.1
0x30265  callvirt instance object System.Windows.PropertyMetadata::GetDefaultValue(class System.Windows.DependencyObject owner, class System.Windows.DependencyProperty property)
0x3026a  call     valuetype System.Windows.EffectiveValueEntry System.Windows.EffectiveValueEntry::CreateDefaultValueEntry(class System.Windows.DependencyProperty dp, object value)
0x3026f  stloc.s  8
0x30271  ldc.i4.0
0x30272  starg.s  5
0x30274  br       loc_30366
0x30279  ldarg.s  5
0x3027b  brfalse.s loc_30284
0x3027d  ldloc.s  6
0x3027f  brfalse.s loc_30284
0x30281  ldnull
0x30282  stloc.s  6
0x30284  ldloca.s 8
0x30286  ldarg.1
0x30287  ldc.i4.s 0xB
0x30289  call     instance void System.Windows.EffectiveValueEntry::.ctor(class System.Windows.DependencyProperty dp, valuetype System.Windows.BaseValueSourceInternal valueSource)
0x3028e  ldloc.s  6
0x30290  brfalse.s loc_302C5
0x30292  ldloc.s  6
0x30294  callvirt instance class System.Windows.DependencySource[] System.Windows.Expression::GetSources()
0x30299  stloc.s  0xA
0x3029b  ldarg.0
0x3029c  ldarg.1
0x3029d  ldloc.s  0xA
0x3029f  ldloc.s  6
0x302a1  ldc.i4.0
0x302a2  call     void System.Windows.DependencyObject::UpdateSourceDependentLists(class System.Windows.DependencyObject d, class System.Windows.DependencyProperty dp, class System.Windows.DependencySource[] sources, class System.Windows.Expression expr, bool add)
0x302a7  ldloc.s  6
0x302a9  ldarg.0
0x302aa  ldarg.1
0x302ab  callvirt instance void System.Windows.Expression::OnDetach(class System.Windows.DependencyObject d, class System.Windows.DependencyProperty dp)
0x302b0  ldloc.s  6
0x302b2  callvirt instance void System.Windows.Expression::MarkDetached()
0x302b7  ldarg.0
0x302b8  ldloc.2
0x302b9  ldarg.1
0x302ba  callvirt instance int32 System.Windows.DependencyProperty::get_GlobalIndex()
0x302bf  call     instance valuetype System.Windows.EntryIndex System.Windows.DependencyObject::CheckEntryIndex(valuetype System.Windows.EntryIndex entryIndex, int32 targetIndex)
0x302c4  stloc.2
0x302c5  ldloc.0
0x302c6  brtrue.s loc_302DE
0x302c8  ldloca.s 8
0x302ca  ldloc.s  4
0x302cc  call     instance void System.Windows.EffectiveValueEntry::set_HasExpressionMarker(bool value)
0x302d1  ldloca.s 8
0x302d3  ldarg.2
0x302d4  call     instance void System.Windows.EffectiveValueEntry::set_Value(object value)
0x302d9  br       loc_30366
0x302de  ldarg.0
0x302df  ldloc.2
0x302e0  ldarg.1
0x302e1  ldarg.1
0x302e2  callvirt instance int32 System.Windows.DependencyProperty::get_GlobalIndex()
0x302e7  ldarg.3
0x302e8  ldloc.0
0x302e9  ldc.i4.s 0xB
0x302eb  call     instance void System.Windows.DependencyObject::SetEffectiveValue(valuetype System.Windows.EntryIndex entryIndex, class System.Windows.DependencyProperty dp, int32 targetIndex, class System.Windows.PropertyMetadata metadata, object value, valuetype System.Windows.BaseValueSourceInternal valueSource)
0x302f0  ldarg.3
0x302f1  ldarg.0
0x302f2  ldarg.1
0x302f3  callvirt instance object System.Windows.PropertyMetadata::GetDefaultValue(class System.Windows.DependencyObject owner, class System.Windows.DependencyProperty property)
0x302f8  stloc.s  0xB
0x302fa  ldarg.0
0x302fb  ldloc.2
0x302fc  ldarg.1
0x302fd  callvirt instance int32 System.Windows.DependencyProperty::get_GlobalIndex()
0x30302  call     instance valuetype System.Windows.EntryIndex System.Windows.DependencyObject::CheckEntryIndex(valuetype System.Windows.EntryIndex entryIndex, int32 targetIndex)
0x30307  stloc.2
0x30308  ldarg.0
0x30309  ldloc.2
0x3030a  ldloc.s  0xB
0x3030c  ldloc.0
0x3030d  call     instance void System.Windows.DependencyObject::SetExpressionValue(valuetype System.Windows.EntryIndex entryIndex, object value, object baseValue)
0x30312  ldarg.0
0x30313  ldarg.1
0x30314  ldloc.1
0x30315  ldloc.0
0x30316  ldc.i4.1
0x30317  call     void System.Windows.DependencyObject::UpdateSourceDependentLists(class System.Windows.DependencyObject d, class System.Windows.DependencyProperty dp, class System.Windows.DependencySource[] sources, class System.Windows.Expression expr, bool add)
0x3031c  ldloc.0
0x3031d  callvirt instance void System.Windows.Expression::MarkAttached()
0x30322  ldloc.0
0x30323  ldarg.0
0x30324  ldarg.1
0x30325  callvirt instance void System.Windows.Expression::OnAttach(class System.Windows.DependencyObject d, class System.Windows.DependencyProperty dp)
0x3032a  ldarg.0
0x3032b  ldloc.2
0x3032c  ldarg.1
0x3032d  callvirt instance int32 System.Windows.DependencyProperty::get_GlobalIndex()
0x30332  call     instance valuetype System.Windows.EntryIndex System.Windows.DependencyObject::CheckEntryIndex(valuetype System.Windows.EntryIndex entryIndex, int32 targetIndex)
0x30337  stloc.2
0x30338  ldarg.0
0x30339  ldloc.2
0x3033a  ldarg.1
0x3033b  ldloc.0
0x3033c  ldarg.3
0x3033d  ldloc.s  5
0x3033f  ldarg.0
0x30340  ldfld    valuetype System.Windows.EffectiveValueEntry[] System.Windows.DependencyObject::_effectiveValues
0x30345  ldloca.s 2
0x30347  call     instance unsigned int32 System.Windows.EntryIndex::get_Index()
0x3034c  ldelem   System.Windows.EffectiveValueEntry
0x30351  call     instance valuetype System.Windows.EffectiveValueEntry System.Windows.DependencyObject::EvaluateExpression(valuetype System.Windows.EntryIndex entryIndex, class System.Windows.DependencyProperty dp, class System.Windows.Expression expr, class System.Windows.PropertyMetadata metadata, valuetype System.Windows.EffectiveValueEntry oldEntry, valuetype System.Windows.EffectiveValueEntry newEntry)
0x30356  stloc.s  8
0x30358  ldarg.0
0x30359  ldloc.2
0x3035a  ldarg.1
0x3035b  callvirt instance int32 System.Windows.DependencyProperty::get_GlobalIndex()
0x30360  call     instance valuetype System.Windows.EntryIndex System.Windows.DependencyObject::CheckEntryIndex(valuetype System.Windows.EntryIndex entryIndex, int32 targetIndex)
0x30365  stloc.2
0x30366  ldarg.0
0x30367  ldloc.2
0x30368  ldarg.1
0x30369  ldarg.3
0x3036a  ldloc.s  5
0x3036c  ldloca.s 8
0x3036e  ldarg.s  4
0x30370  ldarg.s  5
0x30372  ldarg.s  6
0x30374  call     instance valuetype System.Windows.UpdateResult System.Windows.DependencyObject::UpdateEffectiveValue(valuetype System.Windows.EntryIndex entryIndex, class System.Windows.DependencyProperty dp, class System.Windows.PropertyMetadata metadata, valuetype System.Windows.EffectiveValueEntry oldEntry, valuetype System.Windows.EffectiveValueEntry& newEntry, bool coerceWithDeferredReference, bool coerceWithCurrentValue, valuetype System.Windows.OperationType operationType)
0x30379  pop
0x3037a  ret
```
