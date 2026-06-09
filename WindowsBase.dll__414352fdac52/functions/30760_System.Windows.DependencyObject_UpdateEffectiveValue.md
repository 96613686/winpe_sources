# System.Windows.DependencyObject::UpdateEffectiveValue

- ea: `0x30760`
- end: `0x30bb0`
- name: `System.Windows.DependencyObject::UpdateEffectiveValue`
- size: `1104`
- prototype: ``
- caller_count: `4`
- callee_count: `45`
- tags: `installer_update`

## callers

- `0x300d0`
- `0x304c0`
- `0x30630`
- `0x30700`

## callees

- `0x2fbf0`
- `0x30380`
- `0x303f0`
- `0x30760`
- `0x30bb0`
- `0x30cd0`
- `0x30e70`
- `0x31a20`
- `0x31b60`
- `0x31bb0`
- `0x31cd0`
- `0x31d20`
- `0x31f10`
- `0x32170`
- `0x321f0`
- `0x32e40`
- `0x33170`
- `0x333b0`
- `0x34230`
- `0x34270`
- `0x34290`
- `0x342b0`
- `0x342e0`
- `0x34500`
- `0x34510`
- `0x34530`
- `0x34540`
- `0x345a0`
- `0x345c0`
- `0x345e0`
- `0x34600`
- `0x34610`
- `0x34620`
- `0x34630`
- `0x34660`
- `0x34840`
- `0x34890`
- `0x34990`
- `0x349c0`
- `0x349e0`
- `0x34aa0`
- `0x34ab0`
- `0x384e0`
- `0x386d0`
- `0x38950`

## pseudocode

```c

```

## disassembly

```asm
0x30760  ldarg.2
0x30761  brtrue.s loc_3076E
0x30763  ldstr    aDp_0// "dp"
0x30768  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3076d  throw
0x3076e  ldarg.2
0x3076f  callvirt instance int32 System.Windows.DependencyProperty::get_GlobalIndex()
0x30774  stloc.0
0x30775  ldarga.s 4
0x30777  call     instance valuetype System.Windows.BaseValueSourceInternal System.Windows.EffectiveValueEntry::get_BaseValueSourceInternal()
0x3077c  brtrue.s loc_3078B
0x3077e  ldarg.0
0x3077f  ldarg.1
0x30780  ldarg.2
0x30781  ldarg.3
0x30782  ldc.i4.s 0x10
0x30784  call     instance valuetype System.Windows.EffectiveValueEntry System.Windows.DependencyObject::GetValueEntry(valuetype System.Windows.EntryIndex entryIndex, class System.Windows.DependencyProperty dp, class System.Windows.PropertyMetadata metadata, valuetype System.Windows.RequestFlags requests)
0x30789  starg.s  4
0x3078b  ldarga.s 4
0x3078d  ldc.i4.0
0x3078e  call     instance valuetype System.Windows.EffectiveValueEntry System.Windows.EffectiveValueEntry::GetFlattenedEntry(valuetype System.Windows.RequestFlags requests)
0x30793  stloc.s  0xA
0x30795  ldloca.s 0xA
0x30797  call     instance object System.Windows.EffectiveValueEntry::get_Value()
0x3079c  stloc.1
0x3079d  ldnull
0x3079e  stloc.2
0x3079f  ldarg.s  7
0x307a1  brfalse.s loc_307BA
0x307a3  ldarg.s  5
0x307a5  call     instance object System.Windows.EffectiveValueEntry::get_Value()
0x307aa  stloc.2
0x307ab  ldarg.s  5
0x307ad  ldarg.2
0x307ae  ldc.i4.s 0x40
0x307b0  newobj   instance void System.Windows.EffectiveValueEntry::.ctor(class System.Windows.DependencyProperty dp, valuetype System.Windows.FullValueSource fullValueSource)
0x307b5  stobj    System.Windows.EffectiveValueEntry
0x307ba  ldarg.s  5
0x307bc  call     instance valuetype System.Windows.BaseValueSourceInternal System.Windows.EffectiveValueEntry::get_BaseValueSourceInternal()
0x307c1  brfalse.s loc_307D5
0x307c3  ldarg.s  5
0x307c5  call     instance valuetype System.Windows.BaseValueSourceInternal System.Windows.EffectiveValueEntry::get_BaseValueSourceInternal()
0x307ca  ldarga.s 4
0x307cc  call     instance valuetype System.Windows.BaseValueSourceInternal System.Windows.EffectiveValueEntry::get_BaseValueSourceInternal()
0x307d1  bge.s    loc_307D5
0x307d3  ldc.i4.0
0x307d4  ret
0x307d5  ldc.i4.0
0x307d6  stloc.3
0x307d7  ldc.i4.0
0x307d8  stloc.s  4
0x307da  ldc.i4.0
0x307db  stloc.s  5
0x307dd  ldarg.s  5
0x307df  call     instance object System.Windows.EffectiveValueEntry::get_Value()
0x307e4  ldsfld   object System.Windows.DependencyProperty::UnsetValue
0x307e9  bne.un.s loc_3080C
0x307eb  ldarg.s  5
0x307ed  call     instance valuetype System.Windows.FullValueSource System.Windows.EffectiveValueEntry::get_FullValueSource()
0x307f2  stloc.s  0xB
0x307f4  ldloc.s  0xB
0x307f6  ldc.i4.s 0x40
0x307f8  ceq
0x307fa  stloc.s  4
0x307fc  ldc.i4.1
0x307fd  stloc.3
0x307fe  ldarg.s  5
0x30800  call     instance valuetype System.Windows.BaseValueSourceInternal System.Windows.EffectiveValueEntry::get_BaseValueSourceInternal()
0x30805  ldc.i4.s 0xB
0x30807  bne.un.s loc_3080C
0x30809  ldc.i4.1
0x3080a  stloc.s  5
0x3080c  ldloc.3
0x3080d  brtrue.s loc_30859
0x3080f  ldarg.s  5
0x30811  call     instance bool System.Windows.EffectiveValueEntry::get_IsAnimated()
0x30816  brtrue   loc_30997
0x3081b  ldarga.s 4
0x3081d  call     instance bool System.Windows.EffectiveValueEntry::get_IsAnimated()
0x30822  brtrue.s loc_30859
0x30824  ldarga.s 4
0x30826  call     instance bool System.Windows.EffectiveValueEntry::get_IsExpression()
0x3082b  brfalse  loc_30997
0x30830  ldarg.s  5
0x30832  call     instance bool System.Windows.EffectiveValueEntry::get_IsExpression()
0x30837  brfalse  loc_30997
0x3083c  ldarg.s  5
0x3083e  call     instance class System.Windows.ModifiedValue System.Windows.EffectiveValueEntry::get_ModifiedValue()
0x30843  callvirt instance object System.Windows.ModifiedValue::get_BaseValue()
0x30848  ldarga.s 4
0x3084a  call     instance class System.Windows.ModifiedValue System.Windows.EffectiveValueEntry::get_ModifiedValue()
0x3084f  callvirt instance object System.Windows.ModifiedValue::get_BaseValue()
0x30854  bne.un   loc_30997
0x30859  ldloc.s  4
0x3085b  brtrue   loc_30914
0x30860  ldarg.s  5
0x30862  ldarg.0
0x30863  ldarg.1
0x30864  ldarg.2
0x30865  ldarg.3
0x30866  ldarg.s  4
0x30868  ldarg.s  5
0x3086a  ldobj    System.Windows.EffectiveValueEntry
0x3086f  ldarg.s  8
0x30871  call     instance valuetype System.Windows.EffectiveValueEntry System.Windows.DependencyObject::EvaluateEffectiveValue(valuetype System.Windows.EntryIndex entryIndex, class System.Windows.DependencyProperty dp, class System.Windows.PropertyMetadata metadata, valuetype System.Windows.EffectiveValueEntry oldEntry, valuetype System.Windows.EffectiveValueEntry newEntry, valuetype System.Windows.OperationType operationType)
0x30876  stobj    System.Windows.EffectiveValueEntry
0x3087b  ldarg.0
0x3087c  ldarg.1
0x3087d  ldloc.0
0x3087e  call     instance valuetype System.Windows.EntryIndex System.Windows.DependencyObject::CheckEntryIndex(valuetype System.Windows.EntryIndex entryIndex, int32 targetIndex)
0x30883  starg.s  1
0x30885  ldarg.s  5
0x30887  call     instance object System.Windows.EffectiveValueEntry::get_Value()
0x3088c  ldsfld   object System.Windows.DependencyProperty::UnsetValue
0x30891  ceq
0x30893  ldc.i4.0
0x30894  ceq
0x30896  stloc.s  0xC
0x30898  ldloc.s  0xC
0x3089a  brtrue.s loc_308F3
0x3089c  ldarg.3
0x3089d  callvirt instance bool System.Windows.PropertyMetadata::get_IsInherited()
0x308a2  brfalse.s loc_308F3
0x308a4  ldarg.0
0x308a5  call     instance class System.Windows.DependencyObject System.Windows.DependencyObject::get_InheritanceParent()
0x308aa  stloc.s  0xD
0x308ac  ldloc.s  0xD
0x308ae  brfalse.s loc_308F3
0x308b0  ldloc.s  0xD
0x308b2  ldarg.2
0x308b3  callvirt instance int32 System.Windows.DependencyProperty::get_GlobalIndex()
0x308b8  callvirt instance valuetype System.Windows.EntryIndex System.Windows.DependencyObject::LookupEntry(int32 targetIndex)
0x308bd  stloc.s  0xE
0x308bf  ldloca.s 0xE
0x308c1  call     instance bool System.Windows.EntryIndex::get_Found()
0x308c6  brfalse.s loc_308F3
0x308c8  ldc.i4.1
0x308c9  stloc.s  0xC
0x308cb  ldarg.s  5
0x308cd  ldloc.s  0xD
0x308cf  ldfld    valuetype System.Windows.EffectiveValueEntry[] System.Windows.DependencyObject::_effectiveValues
0x308d4  ldloca.s 0xE
0x308d6  call     instance unsigned int32 System.Windows.EntryIndex::get_Index()
0x308db  ldelema  System.Windows.EffectiveValueEntry
0x308e0  ldc.i4.0
0x308e1  call     instance valuetype System.Windows.EffectiveValueEntry System.Windows.EffectiveValueEntry::GetFlattenedEntry(valuetype System.Windows.RequestFlags requests)
0x308e6  stobj    System.Windows.EffectiveValueEntry
0x308eb  ldarg.s  5
0x308ed  ldc.i4.2
0x308ee  call     instance void System.Windows.EffectiveValueEntry::set_BaseValueSourceInternal(valuetype System.Windows.BaseValueSourceInternal value)
0x308f3  ldloc.s  0xC
0x308f5  brtrue   loc_30997
0x308fa  ldarg.s  5
0x308fc  ldarg.2
0x308fd  ldarg.3
0x308fe  ldarg.0
0x308ff  ldarg.2
0x30900  callvirt instance object System.Windows.PropertyMetadata::GetDefaultValue(class System.Windows.DependencyObject owner, class System.Windows.DependencyProperty property)
0x30905  call     valuetype System.Windows.EffectiveValueEntry System.Windows.EffectiveValueEntry::CreateDefaultValueEntry(class System.Windows.DependencyProperty dp, object value)
0x3090a  stobj    System.Windows.EffectiveValueEntry
0x3090f  br       loc_30997
0x30914  ldarga.s 4
0x30916  call     instance bool System.Windows.EffectiveValueEntry::get_HasModifiers()
0x3091b  brtrue.s loc_30928
0x3091d  ldarg.s  5
0x3091f  ldarg.s  4
0x30921  stobj    System.Windows.EffectiveValueEntry
0x30926  br.s     loc_30997
0x30928  ldarg.s  5
0x3092a  ldarg.2
0x3092b  ldarga.s 4
0x3092d  call     instance valuetype System.Windows.BaseValueSourceInternal System.Windows.EffectiveValueEntry::get_BaseValueSourceInternal()
0x30932  newobj   instance void System.Windows.EffectiveValueEntry::.ctor(class System.Windows.DependencyProperty dp, valuetype System.Windows.BaseValueSourceInternal valueSource)
0x30937  stobj    System.Windows.EffectiveValueEntry
0x3093c  ldarga.s 4
0x3093e  call     instance class System.Windows.ModifiedValue System.Windows.EffectiveValueEntry::get_ModifiedValue()
0x30943  stloc.s  0xF
0x30945  ldloc.s  0xF
0x30947  callvirt instance object System.Windows.ModifiedValue::get_BaseValue()
0x3094c  stloc.s  0x10
0x3094e  ldarg.s  5
0x30950  ldloc.s  0x10
0x30952  call     instance void System.Windows.EffectiveValueEntry::set_Value(object value)
0x30957  ldarg.s  5
0x30959  ldarga.s 4
0x3095b  call     instance bool System.Windows.EffectiveValueEntry::get_HasExpressionMarker()
0x30960  call     instance void System.Windows.EffectiveValueEntry::set_HasExpressionMarker(bool value)
0x30965  ldarga.s 4
0x30967  call     instance bool System.Windows.EffectiveValueEntry::get_IsExpression()
0x3096c  brfalse.s loc_3097E
0x3096e  ldarg.s  5
0x30970  ldloc.s  0xF
0x30972  callvirt instance object System.Windows.ModifiedValue::get_ExpressionValue()
0x30977  ldloc.s  0x10
0x30979  call     instance void System.Windows.EffectiveValueEntry::SetExpressionValue(object value, object baseValue)
0x3097e  ldarga.s 4
0x30980  call     instance bool System.Windows.EffectiveValueEntry::get_IsAnimated()
0x30985  brfalse.s loc_30997
0x30987  ldarg.s  5
0x30989  ldloc.s  0xF
0x3098b  callvirt instance object System.Windows.ModifiedValue::get_AnimatedValue()
0x30990  ldloc.s  0x10
0x30992  call     instance void System.Windows.EffectiveValueEntry::SetAnimatedValue(object value, object baseValue)
0x30997  ldarg.s  7
0x30999  brfalse.s loc_309D3
0x3099b  ldarg.s  5
0x3099d  ldc.i4.2
0x3099e  call     instance valuetype System.Windows.EffectiveValueEntry System.Windows.EffectiveValueEntry::GetFlattenedEntry(valuetype System.Windows.RequestFlags requests)
0x309a3  stloc.s  0xA
0x309a5  ldloca.s 0xA
0x309a7  call     instance object System.Windows.EffectiveValueEntry::get_Value()
0x309ac  stloc.s  0x11
0x309ae  ldarg.0
0x309af  ldarg.2
0x309b0  ldarg.3
0x309b1  ldarga.s 1
0x309b3  ldloca.s 0
0x309b5  ldarg.s  5
0x309b7  ldarga.s 4
0x309b9  ldloca.s 1
0x309bb  ldloc.s  0x11
0x309bd  ldloc.2
0x309be  ldnull
0x309bf  ldarg.s  6
0x309c1  ldarg.s  7
0x309c3  ldc.i4.0
0x309c4  call     instance void System.Windows.DependencyObject::ProcessCoerceValue(class System.Windows.DependencyProperty dp, class System.Windows.PropertyMetadata metadata, valuetype System.Windows.EntryIndex& entryIndex, int32& targetIndex, valuetype System.Windows.EffectiveValueEntry& newEntry, valuetype System.Windows.EffectiveValueEntry& oldEntry, object& oldValue, object baseValue, object controlValue, class System.Windows.CoerceValueCallback coerceValueCallback, bool coerceWithDeferredReference, bool coerceWithCurrentValue, bool skipBaseValueChecks)
0x309c9  ldarg.0
0x309ca  ldarg.1
0x309cb  ldloc.0
0x309cc  call     instance valuetype System.Windows.EntryIndex System.Windows.DependencyObject::CheckEntryIndex(valuetype System.Windows.EntryIndex entryIndex, int32 targetIndex)
0x309d1  starg.s  1
0x309d3  ldarg.3
0x309d4  callvirt instance class System.Windows.CoerceValueCallback System.Windows.PropertyMetadata::get_CoerceValueCallback()
0x309d9  brfalse.s loc_30A25
0x309db  ldloc.s  5
0x309dd  brfalse.s loc_309E9
0x309df  ldarg.s  5
0x309e1  call     instance valuetype System.Windows.FullValueSource System.Windows.EffectiveValueEntry::get_FullValueSource()
0x309e6  ldc.i4.1
0x309e7  beq.s    loc_30A25
0x309e9  ldarg.s  5
0x309eb  ldc.i4.2
0x309ec  call     instance valuetype System.Windows.EffectiveValueEntry System.Windows.EffectiveValueEntry::GetFlattenedEntry(valuetype System.Windows.RequestFlags requests)
0x309f1  stloc.s  0xA
0x309f3  ldloca.s 0xA
0x309f5  call     instance object System.Windows.EffectiveValueEntry::get_Value()
0x309fa  stloc.s  0x12
0x309fc  ldarg.0
0x309fd  ldarg.2
0x309fe  ldarg.3
0x309ff  ldarga.s 1
0x30a01  ldloca.s 0
0x30a03  ldarg.s  5
0x30a05  ldarga.s 4
0x30a07  ldloca.s 1
0x30a09  ldloc.s  0x12
0x30a0b  ldnull
0x30a0c  ldarg.3
0x30a0d  callvirt instance class System.Windows.CoerceValueCallback System.Windows.PropertyMetadata::get_CoerceValueCallback()
0x30a12  ldarg.s  6
0x30a14  ldc.i4.0
0x30a15  ldc.i4.0
0x30a16  call     instance void System.Windows.DependencyObject::ProcessCoerceValue(class System.Windows.DependencyProperty dp, class System.Windows.PropertyMetadata metadata, valuetype System.Windows.EntryIndex& entryIndex, int32& targetIndex, valuetype System.Windows.EffectiveValueEntry& newEntry, valuetype System.Windows.EffectiveValueEntry& oldEntry, object& oldValue, object baseValue, object controlValue, class System.Windows.CoerceValueCallback coerceValueCallback, bool coerceWithDeferredReference, bool coerceWithCurrentValue, bool skipBaseValueChecks)
0x30a1b  ldarg.0
0x30a1c  ldarg.1
0x30a1d  ldloc.0
0x30a1e  call     instance valuetype System.Windows.EntryIndex System.Windows.DependencyObject::CheckEntryIndex(valuetype System.Windows.EntryIndex entryIndex, int32 targetIndex)
0x30a23  starg.s  1
0x30a25  ldarg.2
0x30a26  callvirt instance class System.Windows.CoerceValueCallback System.Windows.DependencyProperty::get_DesignerCoerceValueCallback()
0x30a2b  brfalse.s loc_30A64
0x30a2d  ldarg.0
0x30a2e  ldarg.2
0x30a2f  ldarg.3
0x30a30  ldarga.s 1
0x30a32  ldloca.s 0
0x30a34  ldarg.s  5
0x30a36  ldarga.s 4
0x30a38  ldloca.s 1
0x30a3a  ldarg.s  5
0x30a3c  ldc.i4.0
0x30a3d  call     instance valuetype System.Windows.EffectiveValueEntry System.Windows.EffectiveValueEntry::GetFlattenedEntry(valuetype System.Windows.RequestFlags requests)
0x30a42  stloc.s  0xA
0x30a44  ldloca.s 0xA
0x30a46  call     instance object System.Windows.EffectiveValueEntry::get_Value()
0x30a4b  ldnull
0x30a4c  ldarg.2
0x30a4d  callvirt instance class System.Windows.CoerceValueCallback System.Windows.DependencyProperty::get_DesignerCoerceValueCallback()
0x30a52  ldc.i4.0
0x30a53  ldc.i4.0
0x30a54  ldc.i4.1
0x30a55  call     instance void System.Windows.DependencyObject::ProcessCoerceValue(class System.Windows.DependencyProperty dp, class System.Windows.PropertyMetadata metadata, valuetype System.Windows.EntryIndex& entryIndex, int32& targetIndex, valuetype System.Windows.EffectiveValueEntry& newEntry, valuetype System.Windows.EffectiveValueEntry& oldEntry, object& oldValue, object baseValue, object controlValue, class System.Windows.CoerceValueCallback coerceValueCallback, bool coerceWithDeferredReference, bool coerceWithCurrentValue, bool skipBaseValueChecks)
0x30a5a  ldarg.0
0x30a5b  ldarg.1
0x30a5c  ldloc.0
0x30a5d  call     instance valuetype System.Windows.EntryIndex System.Windows.DependencyObject::CheckEntryIndex(valuetype System.Windows.EntryIndex entryIndex, int32 targetIndex)
0x30a62  starg.s  1
0x30a64  ldc.i4.0
0x30a65  stloc.s  6
  ... truncated ...
```
