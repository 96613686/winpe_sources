# System.AccessibilityImprovements::ValidateLevels

- ea: `0xa90`
- end: `0xc1e`
- name: `System.AccessibilityImprovements::ValidateLevels`
- size: `398`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x970`
- `0x9a0`
- `0x9d0`
- `0xa00`
- `0xa30`
- `0xa60`

## callees

- `0xa90`
- `0xfb0`
- `0x23020`

## string_xrefs

- `0xaa0`: `Switch.UseLegacyAccessibilityFeatures`
- `0xacc`: `Switch.UseLegacyAccessibilityFeatures.2`
- `0xaf8`: `Switch.UseLegacyAccessibilityFeatures.3`
- `0xb24`: `Switch.UseLegacyAccessibilityFeatures.4`
- `0xb50`: `Switch.UseLegacyAccessibilityFeatures.5`
- `0xbdd`: `CombinationOfAccessibilitySwitchesNotSupported`
- `0xc07`: `KeyboardToolTipDisplayBehaviorRequiresAccessibilityImprovementsLevel3`

## pseudocode

```c

```

## disassembly

```asm
0xa90  ldsfld   bool System.AccessibilityImprovements::levelsValidated
0xa95  brfalse.s loc_A98
0xa97  ret
0xa98  ldc.i4.5
0xa99  newarr   class [mscorlib]System.Tuple`2<string, class [mscorlib]System.Action`1<int32>>
0xa9e  dup
0xa9f  ldc.i4.0
0xaa0  ldstr    aSwitchUselegac// "Switch.UseLegacyAccessibilityFeatures"
0xaa5  ldsfld   class [mscorlib]System.Action`1<int32> <>c::<>9__25_0
0xaaa  dup
0xaab  brtrue.s loc_AC4
0xaad  pop
0xaae  ldsfld   class <>c <>c::<>9
0xab3  ldftn    instance void <>c::<ValidateLevels>b__25_0(int32 switchValue)
0xab9  newobj   instance void class [mscorlib]System.Action`1<int32>::.ctor(object, native int)
0xabe  dup
0xabf  stsfld   class [mscorlib]System.Action`1<int32> <>c::<>9__25_0
0xac4  call     T0x2B000001
0xac9  stelem.ref
0xaca  dup
0xacb  ldc.i4.1
0xacc  ldstr    aSwitchUselegac_0// "Switch.UseLegacyAccessibilityFeatures.2"
0xad1  ldsfld   class [mscorlib]System.Action`1<int32> <>c::<>9__25_1
0xad6  dup
0xad7  brtrue.s loc_AF0
0xad9  pop
0xada  ldsfld   class <>c <>c::<>9
0xadf  ldftn    instance void <>c::<ValidateLevels>b__25_1(int32 switchValue)
0xae5  newobj   instance void class [mscorlib]System.Action`1<int32>::.ctor(object, native int)
0xaea  dup
0xaeb  stsfld   class [mscorlib]System.Action`1<int32> <>c::<>9__25_1
0xaf0  call     T0x2B000001
0xaf5  stelem.ref
0xaf6  dup
0xaf7  ldc.i4.2
0xaf8  ldstr    aSwitchUselegac_1// "Switch.UseLegacyAccessibilityFeatures.3"
0xafd  ldsfld   class [mscorlib]System.Action`1<int32> <>c::<>9__25_2
0xb02  dup
0xb03  brtrue.s loc_B1C
0xb05  pop
0xb06  ldsfld   class <>c <>c::<>9
0xb0b  ldftn    instance void <>c::<ValidateLevels>b__25_2(int32 switchValue)
0xb11  newobj   instance void class [mscorlib]System.Action`1<int32>::.ctor(object, native int)
0xb16  dup
0xb17  stsfld   class [mscorlib]System.Action`1<int32> <>c::<>9__25_2
0xb1c  call     T0x2B000001
0xb21  stelem.ref
0xb22  dup
0xb23  ldc.i4.3
0xb24  ldstr    aSwitchUselegac_2// "Switch.UseLegacyAccessibilityFeatures.4"
0xb29  ldsfld   class [mscorlib]System.Action`1<int32> <>c::<>9__25_3
0xb2e  dup
0xb2f  brtrue.s loc_B48
0xb31  pop
0xb32  ldsfld   class <>c <>c::<>9
0xb37  ldftn    instance void <>c::<ValidateLevels>b__25_3(int32 switchValue)
0xb3d  newobj   instance void class [mscorlib]System.Action`1<int32>::.ctor(object, native int)
0xb42  dup
0xb43  stsfld   class [mscorlib]System.Action`1<int32> <>c::<>9__25_3
0xb48  call     T0x2B000001
0xb4d  stelem.ref
0xb4e  dup
0xb4f  ldc.i4.4
0xb50  ldstr    aSwitchUselegac_3// "Switch.UseLegacyAccessibilityFeatures.5"
0xb55  ldsfld   class [mscorlib]System.Action`1<int32> <>c::<>9__25_4
0xb5a  dup
0xb5b  brtrue.s loc_B74
0xb5d  pop
0xb5e  ldsfld   class <>c <>c::<>9
0xb63  ldftn    instance void <>c::<ValidateLevels>b__25_4(int32 switchValue)
0xb69  newobj   instance void class [mscorlib]System.Action`1<int32>::.ctor(object, native int)
0xb6e  dup
0xb6f  stsfld   class [mscorlib]System.Action`1<int32> <>c::<>9__25_4
0xb74  call     T0x2B000001
0xb79  stelem.ref
0xb7a  stloc.0
0xb7b  ldc.i4.0
0xb7c  stloc.1
0xb7d  ldc.i4.0
0xb7e  stloc.2
0xb7f  ldloc.0
0xb80  ldlen
0xb81  conv.i4
0xb82  newarr   [mscorlib]System.Boolean
0xb87  stloc.3
0xb88  ldc.i4.0
0xb89  stloc.s  5
0xb8b  br.s     loc_BD3
0xb8d  ldloc.0
0xb8e  ldloc.s  5
0xb90  ldelem.ref
0xb91  callvirt instance var<u1> class [mscorlib]System.Tuple`2<string, class [mscorlib]System.Action`1<int32>>::get_Item1()
0xb96  stloc.s  6
0xb98  ldloc.0
0xb99  ldloc.s  5
0xb9b  ldelem.ref
0xb9c  callvirt instance var<u1> class [mscorlib]System.Tuple`2<string, class [mscorlib]System.Action`1<int32>>::get_Item2()
0xba1  stloc.s  7
0xba3  ldc.i4.0
0xba4  stloc.s  8
0xba6  ldloc.s  6
0xba8  ldloca.s 8
0xbaa  call     bool System.LocalAppContext::GetCachedSwitchValue(string switchName, int32& switchValue)
0xbaf  stloc.s  9
0xbb1  ldloc.s  9
0xbb3  brfalse.s loc_BB9
0xbb5  ldc.i4.1
0xbb6  stloc.1
0xbb7  br.s     loc_BBE
0xbb9  ldloc.1
0xbba  brfalse.s loc_BBE
0xbbc  ldc.i4.1
0xbbd  stloc.2
0xbbe  ldloc.s  7
0xbc0  ldloc.s  8
0xbc2  callvirt instance void class [mscorlib]System.Action`1<int32>::Invoke(var<u1>)
0xbc7  ldloc.3
0xbc8  ldloc.s  5
0xbca  ldloc.s  9
0xbcc  stelem.i1
0xbcd  ldloc.s  5
0xbcf  ldc.i4.1
0xbd0  add
0xbd1  stloc.s  5
0xbd3  ldloc.s  5
0xbd5  ldloc.0
0xbd6  ldlen
0xbd7  conv.i4
0xbd8  blt.s    loc_B8D
0xbda  ldloc.2
0xbdb  brfalse.s loc_BED
0xbdd  ldstr    aCombinationofa// "CombinationOfAccessibilitySwitchesNotSu"...
0xbe2  call     string System.Deployment.Application.Resources::GetString(string s)
0xbe7  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xbec  throw
0xbed  ldstr    aSwitchSystemWi// "Switch.System.Windows.Forms.UseLegacyTo"...
0xbf2  ldsflda  int32 System.AccessibilityImprovements::useLegacyToolTipDisplayBehavior
0xbf7  call     bool System.LocalAppContext::GetCachedSwitchValue(string switchName, int32& switchValue)
0xbfc  stloc.s  4
0xbfe  ldloc.s  4
0xc00  brtrue.s loc_C17
0xc02  ldloc.3
0xc03  ldc.i4.2
0xc04  ldelem.u1
0xc05  brfalse.s loc_C17
0xc07  ldstr    aKeyboardtoolti// "KeyboardToolTipDisplayBehaviorRequiresA"...
0xc0c  call     string System.Deployment.Application.Resources::GetString(string s)
0xc11  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xc16  throw
0xc17  ldc.i4.1
0xc18  stsfld   bool System.AccessibilityImprovements::levelsValidated
0xc1d  ret
```
