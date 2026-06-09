# Microsoft.VisualStudio.Setup.PackageIdentityComparer::GetHashCode

- ea: `0xa800`
- end: `0xa91d`
- name: `Microsoft.VisualStudio.Setup.PackageIdentityComparer::GetHashCode`
- size: `285`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0xa980`
- `0x16320`

## callees

- `0x81e0`
- `0x81f0`
- `0x8200`
- `0x8210`
- `0x8220`
- `0x8230`
- `0x8240`
- `0x8250`
- `0xa800`
- `0xc170`
- `0x10900`

## pseudocode

```c

```

## disassembly

```asm
0xa800  ldarg.1
0xa801  brtrue.s loc_A805
0xa803  ldc.i4.0
0xa804  ret
0xa805  ldc.i4.0
0xa806  stloc.0
0xa807  ldarg.1
0xa808  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0xa80d  brfalse.s loc_A823
0xa80f  ldloc.0
0xa810  ldarg.0
0xa811  ldfld    class [mscorlib]System.StringComparer Microsoft.VisualStudio.Setup.PackageIdentityComparer::comparer
0xa816  ldarg.1
0xa817  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0xa81c  callvirt instance int32 [mscorlib]System.StringComparer::GetHashCode(string)
0xa821  xor
0xa822  stloc.0
0xa823  ldarg.1
0xa824  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Chip()
0xa829  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xa82e  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0xa833  brfalse.s loc_A849
0xa835  ldloc.0
0xa836  ldarg.0
0xa837  ldfld    class [mscorlib]System.StringComparer Microsoft.VisualStudio.Setup.PackageIdentityComparer::comparer
0xa83c  ldarg.1
0xa83d  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Chip()
0xa842  callvirt instance int32 [mscorlib]System.StringComparer::GetHashCode(string)
0xa847  xor
0xa848  stloc.0
0xa849  ldarg.1
0xa84a  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Language()
0xa84f  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xa854  brfalse.s loc_A86A
0xa856  ldloc.0
0xa857  ldarg.0
0xa858  ldfld    class [mscorlib]System.StringComparer Microsoft.VisualStudio.Setup.PackageIdentityComparer::comparer
0xa85d  ldarg.1
0xa85e  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Language()
0xa863  callvirt instance int32 [mscorlib]System.StringComparer::GetHashCode(string)
0xa868  xor
0xa869  stloc.0
0xa86a  ldarg.0
0xa86b  ldfld    bool Microsoft.VisualStudio.Setup.PackageIdentityComparer::excludeBranch
0xa870  brtrue.s loc_A893
0xa872  ldarg.1
0xa873  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Branch()
0xa878  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xa87d  brfalse.s loc_A893
0xa87f  ldloc.0
0xa880  ldarg.0
0xa881  ldfld    class [mscorlib]System.StringComparer Microsoft.VisualStudio.Setup.PackageIdentityComparer::comparer
0xa886  ldarg.1
0xa887  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Branch()
0xa88c  callvirt instance int32 [mscorlib]System.StringComparer::GetHashCode(string)
0xa891  xor
0xa892  stloc.0
0xa893  ldarg.0
0xa894  ldfld    bool Microsoft.VisualStudio.Setup.PackageIdentityComparer::excludeVersion
0xa899  brtrue.s loc_A8B7
0xa89b  ldarg.1
0xa89c  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.IPackageIdentity::get_Version()
0xa8a1  ldnull
0xa8a2  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xa8a7  brfalse.s loc_A8B7
0xa8a9  ldloc.0
0xa8aa  ldarg.1
0xa8ab  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.IPackageIdentity::get_Version()
0xa8b0  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0xa8b5  xor
0xa8b6  stloc.0
0xa8b7  ldarg.1
0xa8b8  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_ProductArch()
0xa8bd  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xa8c2  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0xa8c7  stloc.1
0xa8c8  ldloc.1
0xa8c9  brfalse.s loc_A8DA
0xa8cb  ldloc.0
0xa8cc  ldarg.0
0xa8cd  ldfld    class [mscorlib]System.StringComparer Microsoft.VisualStudio.Setup.PackageIdentityComparer::comparer
0xa8d2  ldloc.1
0xa8d3  callvirt instance int32 [mscorlib]System.StringComparer::GetHashCode(string)
0xa8d8  xor
0xa8d9  stloc.0
0xa8da  ldarg.1
0xa8db  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_MachineArch()
0xa8e0  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xa8e5  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0xa8ea  stloc.2
0xa8eb  ldloc.2
0xa8ec  brfalse.s loc_A8FD
0xa8ee  ldloc.0
0xa8ef  ldarg.0
0xa8f0  ldfld    class [mscorlib]System.StringComparer Microsoft.VisualStudio.Setup.PackageIdentityComparer::comparer
0xa8f5  ldloc.2
0xa8f6  callvirt instance int32 [mscorlib]System.StringComparer::GetHashCode(string)
0xa8fb  xor
0xa8fc  stloc.0
0xa8fd  ldarg.1
0xa8fe  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_TargetSDK()
0xa903  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xa908  stloc.3
0xa909  ldloc.3
0xa90a  brfalse.s loc_A91B
0xa90c  ldloc.0
0xa90d  ldarg.0
0xa90e  ldfld    class [mscorlib]System.StringComparer Microsoft.VisualStudio.Setup.PackageIdentityComparer::comparer
0xa913  ldloc.3
0xa914  callvirt instance int32 [mscorlib]System.StringComparer::GetHashCode(string)
0xa919  xor
0xa91a  stloc.0
0xa91b  ldloc.0
0xa91c  ret
```
