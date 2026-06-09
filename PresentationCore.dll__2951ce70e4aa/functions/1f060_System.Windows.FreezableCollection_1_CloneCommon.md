# System.Windows.FreezableCollection`1::CloneCommon

- ea: `0x1f060`
- end: `0x1f162`
- name: `System.Windows.FreezableCollection`1::CloneCommon`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1f060`
- `0x146e70`

## string_xrefs

- `0x1f103`: `Invalid CloneCommonType encountered.`

## pseudocode

```c

```

## disassembly

```asm
0x1f060  ldarg.1
0x1f061  ldfld    class [mscorlib]System.Collections.Generic.List`1<var<u1>> class System.Windows.FreezableCollection`1<var<u1>>::_collection
0x1f066  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<var<u1>>::get_Count()
0x1f06b  stloc.3
0x1f06c  ldarg.0
0x1f06d  ldloc.3
0x1f06e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<var<u1>>::.ctor(int32)
0x1f073  stfld    class [mscorlib]System.Collections.Generic.List`1<var<u1>> class System.Windows.FreezableCollection`1<var<u1>>::_collection
0x1f078  ldc.i4.0
0x1f079  stloc.2
0x1f07a  br       loc_1F15A
0x1f07f  ldarg.1
0x1f080  ldfld    class [mscorlib]System.Collections.Generic.List`1<var<u1>> class System.Windows.FreezableCollection`1<var<u1>>::_collection
0x1f085  ldloc.2
0x1f086  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<var<u1>>::get_Item(!!T0)
0x1f08b  stloc.0
0x1f08c  ldloc.0
0x1f08d  box      var<u1>
0x1f092  isinst   [WindowsBase]System.Windows.Freezable
0x1f097  stloc.1
0x1f098  ldloc.1
0x1f099  brfalse  loc_1F13D
0x1f09e  ldarg.2
0x1f09f  switch   loc_1F0B6, loc_1F0C9, loc_1F0DC, loc_1F0EF
0x1f0b4  br.s     loc_1F102
0x1f0b6  ldloc.1
0x1f0b7  callvirt instance class [WindowsBase]System.Windows.Freezable [WindowsBase]System.Windows.Freezable::Clone()
0x1f0bc  isinst   var<u1>
0x1f0c1  unbox.any var<u1>
0x1f0c6  stloc.0
0x1f0c7  br.s     loc_1F10D
0x1f0c9  ldloc.1
0x1f0ca  callvirt instance class [WindowsBase]System.Windows.Freezable [WindowsBase]System.Windows.Freezable::CloneCurrentValue()
0x1f0cf  isinst   var<u1>
0x1f0d4  unbox.any var<u1>
0x1f0d9  stloc.0
0x1f0da  br.s     loc_1F10D
0x1f0dc  ldloc.1
0x1f0dd  callvirt instance class [WindowsBase]System.Windows.Freezable [WindowsBase]System.Windows.Freezable::GetAsFrozen()
0x1f0e2  isinst   var<u1>
0x1f0e7  unbox.any var<u1>
0x1f0ec  stloc.0
0x1f0ed  br.s     loc_1F10D
0x1f0ef  ldloc.1
0x1f0f0  callvirt instance class [WindowsBase]System.Windows.Freezable [WindowsBase]System.Windows.Freezable::GetCurrentValueAsFrozen()
0x1f0f5  isinst   var<u1>
0x1f0fa  unbox.any var<u1>
0x1f0ff  stloc.0
0x1f100  br.s     loc_1F10D
0x1f102  ldc.i4.0
0x1f103  ldstr    aInvalidCloneco// "Invalid CloneCommonType encountered."
0x1f108  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x1f10d  ldloc.0
0x1f10e  box      var<u1>
0x1f113  brtrue.s loc_1F13D
0x1f115  ldstr    aFreezableClone// "Freezable_CloneInvalidType"
0x1f11a  ldc.i4.1
0x1f11b  newarr   [mscorlib]System.Object
0x1f120  dup
0x1f121  ldc.i4.0
0x1f122  ldtoken  var<u1>
0x1f127  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f12c  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1f131  stelem.ref
0x1f132  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x1f137  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1f13c  throw
0x1f13d  ldarg.0
0x1f13e  ldnull
0x1f13f  ldloc.0
0x1f140  box      var<u1>
0x1f145  call     instance void [WindowsBase]System.Windows.Freezable::OnFreezablePropertyChanged(class [WindowsBase]System.Windows.DependencyObject, class [WindowsBase]System.Windows.DependencyObject)
0x1f14a  ldarg.0
0x1f14b  ldfld    class [mscorlib]System.Collections.Generic.List`1<var<u1>> class System.Windows.FreezableCollection`1<var<u1>>::_collection
0x1f150  ldloc.0
0x1f151  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<var<u1>>::Add(var<u1>)
0x1f156  ldloc.2
0x1f157  ldc.i4.1
0x1f158  add
0x1f159  stloc.2
0x1f15a  ldloc.2
0x1f15b  ldloc.3
0x1f15c  blt      loc_1F07F
0x1f161  ret
```
