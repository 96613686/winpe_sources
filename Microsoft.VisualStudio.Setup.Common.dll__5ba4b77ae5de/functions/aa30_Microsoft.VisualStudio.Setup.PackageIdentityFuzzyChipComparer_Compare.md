# Microsoft.VisualStudio.Setup.PackageIdentityFuzzyChipComparer::Compare

- ea: `0xaa30`
- end: `0xabef`
- name: `Microsoft.VisualStudio.Setup.PackageIdentityFuzzyChipComparer::Compare`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0xa970`

## callees

- `0x81e0`
- `0x8200`
- `0x8210`
- `0x8230`
- `0x8240`
- `0xa740`
- `0xaa30`
- `0xac00`
- `0xac10`

## pseudocode

```c

```

## disassembly

```asm
0xaa30  ldarg.0
0xaa31  ldfld    class Microsoft.VisualStudio.Setup.PackageIdentityComparer Microsoft.VisualStudio.Setup.PackageIdentityFuzzyChipComparer::identityComparerImpl
0xaa36  ldarg.1
0xaa37  ldarg.2
0xaa38  callvirt instance int32 Microsoft.VisualStudio.Setup.PackageIdentityComparer::Compare(class Microsoft.VisualStudio.Setup.IPackageIdentity x, class Microsoft.VisualStudio.Setup.IPackageIdentity y)
0xaa3d  stloc.1
0xaa3e  ldloc.1
0xaa3f  brtrue.s loc_AA43
0xaa41  ldloc.1
0xaa42  ret
0xaa43  ldloca.s 0
0xaa45  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xaa4a  stfld    class [mscorlib]System.StringComparer <>c__DisplayClass5_0::comparer
0xaa4f  ldarg.1
0xaa50  brtrue.s loc_AA54
0xaa52  ldc.i4.m1
0xaa53  ret
0xaa54  ldarg.2
0xaa55  brtrue.s loc_AA59
0xaa57  ldc.i4.1
0xaa58  ret
0xaa59  ldloc.0
0xaa5a  ldfld    class [mscorlib]System.StringComparer <>c__DisplayClass5_0::comparer
0xaa5f  ldarg.1
0xaa60  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0xaa65  ldarg.2
0xaa66  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0xaa6b  callvirt instance int32 [mscorlib]System.StringComparer::Compare(string, string)
0xaa70  stloc.1
0xaa71  ldloc.1
0xaa72  brfalse.s loc_AA76
0xaa74  ldloc.1
0xaa75  ret
0xaa76  ldarg.1
0xaa77  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Language()
0xaa7c  call     string Microsoft.VisualStudio.Setup.PackageIdentityFuzzyChipComparer::<Compare>g__normalize|5_0(string attr)
0xaa81  stloc.2
0xaa82  ldarg.2
0xaa83  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Language()
0xaa88  call     string Microsoft.VisualStudio.Setup.PackageIdentityFuzzyChipComparer::<Compare>g__normalize|5_0(string attr)
0xaa8d  stloc.3
0xaa8e  ldloc.0
0xaa8f  ldfld    class [mscorlib]System.StringComparer <>c__DisplayClass5_0::comparer
0xaa94  ldloc.2
0xaa95  ldloc.3
0xaa96  callvirt instance int32 [mscorlib]System.StringComparer::Compare(string, string)
0xaa9b  stloc.1
0xaa9c  ldloc.1
0xaa9d  brfalse.s loc_AAA1
0xaa9f  ldloc.1
0xaaa0  ret
0xaaa1  ldarg.1
0xaaa2  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_ProductArch()
0xaaa7  call     string Microsoft.VisualStudio.Setup.PackageIdentityFuzzyChipComparer::<Compare>g__normalize|5_0(string attr)
0xaaac  stloc.s  4
0xaaae  ldarg.2
0xaaaf  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_ProductArch()
0xaab4  call     string Microsoft.VisualStudio.Setup.PackageIdentityFuzzyChipComparer::<Compare>g__normalize|5_0(string attr)
0xaab9  stloc.s  5
0xaabb  ldloc.0
0xaabc  ldfld    class [mscorlib]System.StringComparer <>c__DisplayClass5_0::comparer
0xaac1  ldloc.s  4
0xaac3  ldloc.s  5
0xaac5  callvirt instance int32 [mscorlib]System.StringComparer::Compare(string, string)
0xaaca  stloc.1
0xaacb  ldloc.1
0xaacc  brfalse.s loc_AAD8
0xaace  ldloc.s  4
0xaad0  brfalse.s loc_AAD8
0xaad2  ldloc.s  5
0xaad4  brfalse.s loc_AAD8
0xaad6  ldloc.1
0xaad7  ret
0xaad8  ldarg.1
0xaad9  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Chip()
0xaade  call     string Microsoft.VisualStudio.Setup.PackageIdentityFuzzyChipComparer::<Compare>g__normalize|5_0(string attr)
0xaae3  stloc.s  6
0xaae5  ldarg.2
0xaae6  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Chip()
0xaaeb  call     string Microsoft.VisualStudio.Setup.PackageIdentityFuzzyChipComparer::<Compare>g__normalize|5_0(string attr)
0xaaf0  stloc.s  7
0xaaf2  ldarg.1
0xaaf3  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_MachineArch()
0xaaf8  call     string Microsoft.VisualStudio.Setup.PackageIdentityFuzzyChipComparer::<Compare>g__normalize|5_0(string attr)
0xaafd  stloc.s  8
0xaaff  ldarg.2
0xab00  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_MachineArch()
0xab05  call     string Microsoft.VisualStudio.Setup.PackageIdentityFuzzyChipComparer::<Compare>g__normalize|5_0(string attr)
0xab0a  stloc.s  9
0xab0c  ldloc.s  6
0xab0e  brfalse.s loc_AB1E
0xab10  ldloc.s  7
0xab12  brfalse.s loc_AB1E
0xab14  ldloc.s  8
0xab16  brfalse.s loc_AB1E
0xab18  ldloc.s  9
0xab1a  brfalse.s loc_AB1E
0xab1c  ldc.i4.m1
0xab1d  ret
0xab1e  ldloc.s  6
0xab20  brfalse.s loc_AB3B
0xab22  ldloc.s  8
0xab24  brfalse.s loc_AB3B
0xab26  ldloc.s  6
0xab28  ldloc.s  7
0xab2a  ldloc.s  8
0xab2c  ldloc.s  9
0xab2e  ldloca.s 0
0xab30  call     bool Microsoft.VisualStudio.Setup.PackageIdentityFuzzyChipComparer::<Compare>g__compareChipsAndMachineArchs|5_1(string chip1, string chip2, string mArch1, string mArch2, valuetype <>c__DisplayClass5_0& value)
0xab35  brtrue.s loc_AB39
0xab37  ldc.i4.m1
0xab38  ret
0xab39  ldc.i4.0
0xab3a  ret
0xab3b  ldloc.s  7
0xab3d  brfalse.s loc_AB58
0xab3f  ldloc.s  9
0xab41  brfalse.s loc_AB58
0xab43  ldloc.s  7
0xab45  ldloc.s  6
0xab47  ldloc.s  9
0xab49  ldloc.s  8
0xab4b  ldloca.s 0
0xab4d  call     bool Microsoft.VisualStudio.Setup.PackageIdentityFuzzyChipComparer::<Compare>g__compareChipsAndMachineArchs|5_1(string chip1, string chip2, string mArch1, string mArch2, valuetype <>c__DisplayClass5_0& value)
0xab52  brtrue.s loc_AB56
0xab54  ldc.i4.m1
0xab55  ret
0xab56  ldc.i4.0
0xab57  ret
0xab58  ldloc.s  6
0xab5a  brfalse.s loc_AB70
0xab5c  ldloc.s  7
0xab5e  brfalse.s loc_AB70
0xab60  ldloc.0
0xab61  ldfld    class [mscorlib]System.StringComparer <>c__DisplayClass5_0::comparer
0xab66  ldloc.s  6
0xab68  ldloc.s  7
0xab6a  callvirt instance int32 [mscorlib]System.StringComparer::Compare(string, string)
0xab6f  ret
0xab70  ldloc.s  8
0xab72  brfalse.s loc_AB88
0xab74  ldloc.s  9
0xab76  brfalse.s loc_AB88
0xab78  ldloc.0
0xab79  ldfld    class [mscorlib]System.StringComparer <>c__DisplayClass5_0::comparer
0xab7e  ldloc.s  8
0xab80  ldloc.s  9
0xab82  callvirt instance int32 [mscorlib]System.StringComparer::Compare(string, string)
0xab87  ret
0xab88  ldloc.s  6
0xab8a  brfalse.s loc_ABA0
0xab8c  ldloc.s  9
0xab8e  brfalse.s loc_ABA0
0xab90  ldloc.0
0xab91  ldfld    class [mscorlib]System.StringComparer <>c__DisplayClass5_0::comparer
0xab96  ldloc.s  6
0xab98  ldloc.s  9
0xab9a  callvirt instance int32 [mscorlib]System.StringComparer::Compare(string, string)
0xab9f  ret
0xaba0  ldloc.s  8
0xaba2  brfalse.s loc_ABB8
0xaba4  ldloc.s  7
0xaba6  brfalse.s loc_ABB8
0xaba8  ldloc.0
0xaba9  ldfld    class [mscorlib]System.StringComparer <>c__DisplayClass5_0::comparer
0xabae  ldloc.s  8
0xabb0  ldloc.s  7
0xabb2  callvirt instance int32 [mscorlib]System.StringComparer::Compare(string, string)
0xabb7  ret
0xabb8  ldloc.s  6
0xabba  brtrue.s loc_ABCB
0xabbc  ldloc.s  8
0xabbe  brtrue.s loc_ABCB
0xabc0  ldloc.s  7
0xabc2  brtrue.s loc_ABCB
0xabc4  ldloc.s  9
0xabc6  ldnull
0xabc7  cgt.un
0xabc9  br.s     loc_ABCC
0xabcb  ldc.i4.1
0xabcc  brfalse.s loc_ABD0
0xabce  ldc.i4.0
0xabcf  ret
0xabd0  ldloc.s  4
0xabd2  brfalse.s loc_ABED
0xabd4  ldloc.s  5
0xabd6  brfalse.s loc_ABED
0xabd8  ldloc.s  4
0xabda  brfalse.s loc_ABEB
0xabdc  ldloc.s  5
0xabde  brfalse.s loc_ABEB
0xabe0  ldloc.s  4
0xabe2  ldloc.s  5
0xabe4  callvirt instance bool [mscorlib]System.String::Equals(string)
0xabe9  brtrue.s loc_ABED
0xabeb  ldc.i4.m1
0xabec  ret
0xabed  ldc.i4.0
0xabee  ret
```
