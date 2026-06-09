# PackageVersionSorter::Compare

- ea: `0x1d4a0`
- end: `0x1d4e9`
- name: `PackageVersionSorter::Compare`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x81e0`
- `0x81f0`
- `0xa740`
- `0x1d4a0`
- `0x1d4f0`
- `0x1d500`

## pseudocode

```c

```

## disassembly

```asm
0x1d4a0  ldarg.1
0x1d4a1  ldarg.2
0x1d4a2  bne.un.s loc_1D4A6
0x1d4a4  ldc.i4.0
0x1d4a5  ret
0x1d4a6  ldarg.1
0x1d4a7  brtrue.s loc_1D4AB
0x1d4a9  ldc.i4.m1
0x1d4aa  ret
0x1d4ab  ldarg.2
0x1d4ac  brtrue.s loc_1D4B0
0x1d4ae  ldc.i4.1
0x1d4af  ret
0x1d4b0  ldarg.1
0x1d4b1  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x1d4b6  ldarg.2
0x1d4b7  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x1d4bc  call     int32 PackageVersionSorter::CompareIds(string x, string y)
0x1d4c1  stloc.0
0x1d4c2  ldloc.0
0x1d4c3  brtrue.s loc_1D4D7
0x1d4c5  ldarg.1
0x1d4c6  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.IPackageIdentity::get_Version()
0x1d4cb  ldarg.2
0x1d4cc  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.IPackageIdentity::get_Version()
0x1d4d1  call     int32 PackageVersionSorter::CompareVersions(class [mscorlib]System.Version x, class [mscorlib]System.Version y)
0x1d4d6  stloc.0
0x1d4d7  ldloc.0
0x1d4d8  brtrue.s loc_1D4E7
0x1d4da  ldsfld   class Microsoft.VisualStudio.Setup.PackageIdentityComparer PackageVersionSorter::Comparer
0x1d4df  ldarg.1
0x1d4e0  ldarg.2
0x1d4e1  callvirt instance int32 Microsoft.VisualStudio.Setup.PackageIdentityComparer::Compare(class Microsoft.VisualStudio.Setup.IPackageIdentity x, class Microsoft.VisualStudio.Setup.IPackageIdentity y)
0x1d4e6  stloc.0
0x1d4e7  ldloc.0
0x1d4e8  ret
```
