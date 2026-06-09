# Microsoft.VisualStudio.Setup.PackageIdentityFuzzyChipComparer::GetHashCode

- ea: `0xa980`
- end: `0xaa23`
- name: `Microsoft.VisualStudio.Setup.PackageIdentityFuzzyChipComparer::GetHashCode`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x8200`
- `0x8220`
- `0x8230`
- `0x8240`
- `0xa800`
- `0xa980`
- `0xc170`
- `0x10900`

## pseudocode

```c

```

## disassembly

```asm
0xa980  ldarg.0
0xa981  ldfld    class Microsoft.VisualStudio.Setup.PackageIdentityComparer Microsoft.VisualStudio.Setup.PackageIdentityFuzzyChipComparer::identityComparerImpl
0xa986  ldarg.1
0xa987  callvirt instance int32 Microsoft.VisualStudio.Setup.PackageIdentityComparer::GetHashCode(class Microsoft.VisualStudio.Setup.IPackageIdentity obj)
0xa98c  stloc.0
0xa98d  ldarg.1
0xa98e  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Branch()
0xa993  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xa998  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0xa99d  brfalse.s loc_A9B2
0xa99f  ldloc.0
0xa9a0  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xa9a5  ldarg.1
0xa9a6  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Branch()
0xa9ab  callvirt instance int32 [mscorlib]System.StringComparer::GetHashCode(string)
0xa9b0  xor
0xa9b1  stloc.0
0xa9b2  ldarg.1
0xa9b3  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Chip()
0xa9b8  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xa9bd  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0xa9c2  brfalse.s loc_A9D7
0xa9c4  ldloc.0
0xa9c5  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xa9ca  ldarg.1
0xa9cb  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Chip()
0xa9d0  callvirt instance int32 [mscorlib]System.StringComparer::GetHashCode(string)
0xa9d5  xor
0xa9d6  stloc.0
0xa9d7  ldarg.1
0xa9d8  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_ProductArch()
0xa9dd  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xa9e2  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0xa9e7  brfalse.s loc_A9FC
0xa9e9  ldloc.0
0xa9ea  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xa9ef  ldarg.1
0xa9f0  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_ProductArch()
0xa9f5  callvirt instance int32 [mscorlib]System.StringComparer::GetHashCode(string)
0xa9fa  xor
0xa9fb  stloc.0
0xa9fc  ldarg.1
0xa9fd  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_MachineArch()
0xaa02  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xaa07  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0xaa0c  brfalse.s loc_AA21
0xaa0e  ldloc.0
0xaa0f  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xaa14  ldarg.1
0xaa15  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_MachineArch()
0xaa1a  callvirt instance int32 [mscorlib]System.StringComparer::GetHashCode(string)
0xaa1f  xor
0xaa20  stloc.0
0xaa21  ldloc.0
0xaa22  ret
```
