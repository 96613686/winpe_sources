# Microsoft.VisualStudio.Setup.Extensions::FindResource

- ea: `0x55e0`
- end: `0x56ce`
- name: `Microsoft.VisualStudio.Setup.Extensions::FindResource`
- size: `238`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x56d0`
- `0x6490`
- `0x1af20`

## callees

- `0x55e0`
- `0xc1a0`
- `0x1c5f0`

## pseudocode

```c

```

## disassembly

```asm
0x55e0  newobj   instance void <>c__DisplayClass9_0::.ctor()
0x55e5  stloc.0
0x55e6  ldloc.0
0x55e7  ldarg.1
0x55e8  stfld    class [mscorlib]System.Globalization.CultureInfo <>c__DisplayClass9_0::culture
0x55ed  ldarg.0
0x55ee  ldstr    aSource// "source"
0x55f3  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x55f8  ldloc.0
0x55f9  ldfld    class [mscorlib]System.Globalization.CultureInfo <>c__DisplayClass9_0::culture
0x55fe  brtrue.s loc_560B
0x5600  ldloc.0
0x5601  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x5606  stfld    class [mscorlib]System.Globalization.CultureInfo <>c__DisplayClass9_0::culture
0x560b  ldarg.0
0x560c  ldloc.0
0x560d  ldftn    instance bool <>c__DisplayClass9_0::<FindResource>b__0(class Microsoft.VisualStudio.Setup.LocalizedResource x)
0x5613  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.LocalizedResource, bool>::.ctor(object, native int)
0x5618  call     T0x2B00001D
0x561d  stloc.1
0x561e  ldloc.1
0x561f  brfalse.s loc_5623
0x5621  ldloc.1
0x5622  ret
0x5623  ldarg.2
0x5624  ldc.i4.1
0x5625  and
0x5626  ldc.i4.1
0x5627  bne.un.s loc_564E
0x5629  ldloc.0
0x562a  ldfld    class [mscorlib]System.Globalization.CultureInfo <>c__DisplayClass9_0::culture
0x562f  callvirt instance bool [mscorlib]System.Globalization.CultureInfo::get_IsNeutralCulture()
0x5634  brtrue.s loc_564E
0x5636  ldarg.0
0x5637  ldloc.0
0x5638  ldftn    instance bool <>c__DisplayClass9_0::<FindResource>b__1(class Microsoft.VisualStudio.Setup.LocalizedResource x)
0x563e  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.LocalizedResource, bool>::.ctor(object, native int)
0x5643  call     T0x2B00001D
0x5648  stloc.1
0x5649  ldloc.1
0x564a  brfalse.s loc_564E
0x564c  ldloc.1
0x564d  ret
0x564e  ldarg.2
0x564f  ldc.i4.2
0x5650  and
0x5651  ldc.i4.2
0x5652  bne.un.s loc_56CC
0x5654  ldarg.0
0x5655  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.LocalizedResource, bool> <>c::<>9__9_2
0x565a  dup
0x565b  brtrue.s loc_5674
0x565d  pop
0x565e  ldsfld   class <>c <>c::<>9
0x5663  ldftn    instance bool <>c::<FindResource>b__9_2(class Microsoft.VisualStudio.Setup.LocalizedResource x)
0x5669  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.LocalizedResource, bool>::.ctor(object, native int)
0x566e  dup
0x566f  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.LocalizedResource, bool> <>c::<>9__9_2
0x5674  call     T0x2B00001D
0x5679  dup
0x567a  brtrue.s loc_56A2
0x567c  pop
0x567d  ldarg.0
0x567e  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.LocalizedResource, bool> <>c::<>9__9_3
0x5683  dup
0x5684  brtrue.s loc_569D
0x5686  pop
0x5687  ldsfld   class <>c <>c::<>9
0x568c  ldftn    instance bool <>c::<FindResource>b__9_3(class Microsoft.VisualStudio.Setup.LocalizedResource x)
0x5692  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.LocalizedResource, bool>::.ctor(object, native int)
0x5697  dup
0x5698  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.LocalizedResource, bool> <>c::<>9__9_3
0x569d  call     T0x2B00001D
0x56a2  stloc.1
0x56a3  ldloc.1
0x56a4  brtrue.s loc_56CC
0x56a6  ldarg.0
0x56a7  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.LocalizedResource, bool> <>c::<>9__9_4
0x56ac  dup
0x56ad  brtrue.s loc_56C6
0x56af  pop
0x56b0  ldsfld   class <>c <>c::<>9
0x56b5  ldftn    instance bool <>c::<FindResource>b__9_4(class Microsoft.VisualStudio.Setup.LocalizedResource x)
0x56bb  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.LocalizedResource, bool>::.ctor(object, native int)
0x56c0  dup
0x56c1  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.LocalizedResource, bool> <>c::<>9__9_4
0x56c6  call     T0x2B00001D
0x56cb  stloc.1
0x56cc  ldloc.1
0x56cd  ret
```
