# System.IO.Packaging.Package::AddIfNoPrefixCollisionDetected

- ea: `0x49470`
- end: `0x49566`
- name: `System.IO.Packaging.Package::AddIfNoPrefixCollisionDetected`
- size: `246`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x48c20`
- `0x48dc0`
- `0x49810`

## callees

- `0xd6a0`
- `0x2c100`
- `0x49470`
- `0x5a8d0`

## string_xrefs

- `0x49491`: `Given uri must be present in the dictionary`

## pseudocode

```c

```

## disassembly

```asm
0x49470  ldarg.0
0x49471  ldfld    class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart> System.IO.Packaging.Package::_partList
0x49476  ldarg.1
0x49477  ldarg.2
0x49478  callvirt instance void class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart>::Add(var<u1>, !!T0)
0x4947d  ldarg.0
0x4947e  ldfld    class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart> System.IO.Packaging.Package::_partList
0x49483  ldarg.1
0x49484  callvirt instance int32 class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart>::IndexOfKey(var<u1>)
0x49489  stloc.0
0x4948a  ldloc.0
0x4948b  ldc.i4.0
0x4948c  clt
0x4948e  ldc.i4.0
0x4948f  ceq
0x49491  ldstr    aGivenUriMustBe// "Given uri must be present in the dictio"...
0x49496  call     void MS.Internal.Invariant::Assert(bool condition, string invariantMessage)
0x4949b  ldarg.1
0x4949c  callvirt instance string ValidatedPartUri::get_NormalizedPartUriString()
0x494a1  stloc.1
0x494a2  ldnull
0x494a3  stloc.2
0x494a4  ldnull
0x494a5  stloc.3
0x494a6  ldloc.0
0x494a7  ldc.i4.0
0x494a8  ble.s    loc_494C3
0x494aa  ldarg.0
0x494ab  ldfld    class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart> System.IO.Packaging.Package::_partList
0x494b0  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart>::get_Keys()
0x494b5  ldloc.0
0x494b6  ldc.i4.1
0x494b7  sub
0x494b8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class ValidatedPartUri>::get_Item(!!T0)
0x494bd  callvirt instance string ValidatedPartUri::get_NormalizedPartUriString()
0x494c2  stloc.2
0x494c3  ldloc.0
0x494c4  ldarg.0
0x494c5  ldfld    class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart> System.IO.Packaging.Package::_partList
0x494ca  callvirt instance int32 class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart>::get_Count()
0x494cf  ldc.i4.1
0x494d0  sub
0x494d1  bge.s    loc_494EC
0x494d3  ldarg.0
0x494d4  ldfld    class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart> System.IO.Packaging.Package::_partList
0x494d9  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart>::get_Keys()
0x494de  ldloc.0
0x494df  ldc.i4.1
0x494e0  add
0x494e1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class ValidatedPartUri>::get_Item(!!T0)
0x494e6  callvirt instance string ValidatedPartUri::get_NormalizedPartUriString()
0x494eb  stloc.3
0x494ec  ldloc.2
0x494ed  brfalse.s loc_4951A
0x494ef  ldloc.1
0x494f0  ldloc.2
0x494f1  ldc.i4.4
0x494f2  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x494f7  brfalse.s loc_4951A
0x494f9  ldloc.1
0x494fa  callvirt instance int32 [mscorlib]System.String::get_Length()
0x494ff  ldloc.2
0x49500  callvirt instance int32 [mscorlib]System.String::get_Length()
0x49505  ble.s    loc_4951A
0x49507  ldloc.1
0x49508  ldloc.2
0x49509  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4950e  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x49513  ldsfld   char System.IO.Packaging.PackUriHelper::ForwardSlashChar
0x49518  beq.s    loc_49548
0x4951a  ldloc.3
0x4951b  brfalse.s loc_49565
0x4951d  ldloc.3
0x4951e  ldloc.1
0x4951f  ldc.i4.4
0x49520  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x49525  brfalse.s loc_49565
0x49527  ldloc.3
0x49528  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4952d  ldloc.1
0x4952e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x49533  ble.s    loc_49565
0x49535  ldloc.3
0x49536  ldloc.1
0x49537  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4953c  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x49541  ldsfld   char System.IO.Packaging.PackUriHelper::ForwardSlashChar
0x49546  bne.un.s loc_49565
0x49548  ldarg.0
0x49549  ldfld    class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart> System.IO.Packaging.Package::_partList
0x4954e  ldarg.1
0x4954f  callvirt instance bool class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart>::Remove(var<u1>)
0x49554  pop
0x49555  ldstr    aPartnameprefix// "PartNamePrefixExists"
0x4955a  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4955f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x49564  throw
0x49565  ret
```
