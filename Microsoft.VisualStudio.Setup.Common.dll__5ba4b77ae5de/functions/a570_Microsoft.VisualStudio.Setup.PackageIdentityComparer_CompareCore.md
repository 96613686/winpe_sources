# Microsoft.VisualStudio.Setup.PackageIdentityComparer::CompareCore

- ea: `0xa570`
- end: `0xa733`
- name: `Microsoft.VisualStudio.Setup.PackageIdentityComparer::CompareCore`
- size: `451`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x81e0`
- `0x81f0`
- `0x8200`
- `0x8210`
- `0x8220`
- `0x8230`
- `0x8240`
- `0x8250`
- `0xa570`
- `0xc170`
- `0x10900`

## pseudocode

```c

```

## disassembly

```asm
0xa570  ldarg.1
0xa571  ldarg.2
0xa572  bne.un.s loc_A577
0xa574  ldarg.s  6
0xa576  ret
0xa577  ldarg.1
0xa578  brtrue.s loc_A57D
0xa57a  ldarg.s  7
0xa57c  ret
0xa57d  ldarg.2
0xa57e  brtrue.s loc_A583
0xa580  ldarg.s  8
0xa582  ret
0xa583  ldarg.3
0xa584  ldarg.1
0xa585  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0xa58a  ldarg.2
0xa58b  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0xa590  ldarg.0
0xa591  ldfld    valuetype [mscorlib]System.StringComparison Microsoft.VisualStudio.Setup.PackageIdentityComparer::comparisonType
0xa596  callvirt instance var<u1> class [mscorlib]System.Func`4<string, string, valuetype [mscorlib]System.StringComparison, mvar<u1>>::Invoke(char, var<u1>, !!T0)
0xa59b  stloc.0
0xa59c  ldarg.s  5
0xa59e  ldloc.0
0xa59f  callvirt instance var<u1> class [mscorlib]System.Func`2<mvar<u1>, !!T0>::Invoke(void)
0xa5a4  brtrue.s loc_A5A8
0xa5a6  ldloc.0
0xa5a7  ret
0xa5a8  ldarg.1
0xa5a9  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Chip()
0xa5ae  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xa5b3  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0xa5b8  stloc.1
0xa5b9  ldarg.2
0xa5ba  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Chip()
0xa5bf  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xa5c4  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0xa5c9  stloc.2
0xa5ca  ldarg.3
0xa5cb  ldloc.1
0xa5cc  ldloc.2
0xa5cd  ldarg.0
0xa5ce  ldfld    valuetype [mscorlib]System.StringComparison Microsoft.VisualStudio.Setup.PackageIdentityComparer::comparisonType
0xa5d3  callvirt instance var<u1> class [mscorlib]System.Func`4<string, string, valuetype [mscorlib]System.StringComparison, mvar<u1>>::Invoke(char, var<u1>, !!T0)
0xa5d8  stloc.0
0xa5d9  ldarg.s  5
0xa5db  ldloc.0
0xa5dc  callvirt instance var<u1> class [mscorlib]System.Func`2<mvar<u1>, !!T0>::Invoke(void)
0xa5e1  brtrue.s loc_A5E5
0xa5e3  ldloc.0
0xa5e4  ret
0xa5e5  ldarg.1
0xa5e6  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Language()
0xa5eb  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xa5f0  stloc.3
0xa5f1  ldarg.2
0xa5f2  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Language()
0xa5f7  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xa5fc  stloc.s  4
0xa5fe  ldarg.3
0xa5ff  ldloc.3
0xa600  ldloc.s  4
0xa602  ldarg.0
0xa603  ldfld    valuetype [mscorlib]System.StringComparison Microsoft.VisualStudio.Setup.PackageIdentityComparer::comparisonType
0xa608  callvirt instance var<u1> class [mscorlib]System.Func`4<string, string, valuetype [mscorlib]System.StringComparison, mvar<u1>>::Invoke(char, var<u1>, !!T0)
0xa60d  stloc.0
0xa60e  ldarg.s  5
0xa610  ldloc.0
0xa611  callvirt instance var<u1> class [mscorlib]System.Func`2<mvar<u1>, !!T0>::Invoke(void)
0xa616  brtrue.s loc_A61A
0xa618  ldloc.0
0xa619  ret
0xa61a  ldarg.0
0xa61b  ldfld    bool Microsoft.VisualStudio.Setup.PackageIdentityComparer::excludeBranch
0xa620  brtrue.s loc_A659
0xa622  ldarg.1
0xa623  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Branch()
0xa628  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xa62d  stloc.s  0xB
0xa62f  ldarg.2
0xa630  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Branch()
0xa635  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xa63a  stloc.s  0xC
0xa63c  ldarg.3
0xa63d  ldloc.s  0xB
0xa63f  ldloc.s  0xC
0xa641  ldarg.0
0xa642  ldfld    valuetype [mscorlib]System.StringComparison Microsoft.VisualStudio.Setup.PackageIdentityComparer::comparisonType
0xa647  callvirt instance var<u1> class [mscorlib]System.Func`4<string, string, valuetype [mscorlib]System.StringComparison, mvar<u1>>::Invoke(char, var<u1>, !!T0)
0xa64c  stloc.0
0xa64d  ldarg.s  5
0xa64f  ldloc.0
0xa650  callvirt instance var<u1> class [mscorlib]System.Func`2<mvar<u1>, !!T0>::Invoke(void)
0xa655  brtrue.s loc_A659
0xa657  ldloc.0
0xa658  ret
0xa659  ldarg.0
0xa65a  ldfld    bool Microsoft.VisualStudio.Setup.PackageIdentityComparer::excludeVersion
0xa65f  brtrue.s loc_A684
0xa661  ldarg.s  4
0xa663  ldarg.1
0xa664  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.IPackageIdentity::get_Version()
0xa669  ldarg.2
0xa66a  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.IPackageIdentity::get_Version()
0xa66f  callvirt instance var<u1> class [mscorlib]System.Func`3<class [mscorlib]System.Version, class [mscorlib]System.Version, mvar<u1>>::Invoke(bool, var<u1>)
0xa674  stloc.s  0xD
0xa676  ldarg.s  5
0xa678  ldloc.s  0xD
0xa67a  callvirt instance var<u1> class [mscorlib]System.Func`2<mvar<u1>, !!T0>::Invoke(void)
0xa67f  brtrue.s loc_A684
0xa681  ldloc.s  0xD
0xa683  ret
0xa684  ldarg.1
0xa685  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_MachineArch()
0xa68a  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xa68f  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0xa694  stloc.s  5
0xa696  ldarg.2
0xa697  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_MachineArch()
0xa69c  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xa6a1  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0xa6a6  stloc.s  6
0xa6a8  ldarg.3
0xa6a9  ldloc.s  5
0xa6ab  ldloc.s  6
0xa6ad  ldarg.0
0xa6ae  ldfld    valuetype [mscorlib]System.StringComparison Microsoft.VisualStudio.Setup.PackageIdentityComparer::comparisonType
0xa6b3  callvirt instance var<u1> class [mscorlib]System.Func`4<string, string, valuetype [mscorlib]System.StringComparison, mvar<u1>>::Invoke(char, var<u1>, !!T0)
0xa6b8  stloc.0
0xa6b9  ldarg.s  5
0xa6bb  ldloc.0
0xa6bc  callvirt instance var<u1> class [mscorlib]System.Func`2<mvar<u1>, !!T0>::Invoke(void)
0xa6c1  brtrue.s loc_A6C5
0xa6c3  ldloc.0
0xa6c4  ret
0xa6c5  ldarg.1
0xa6c6  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_ProductArch()
0xa6cb  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xa6d0  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0xa6d5  stloc.s  7
0xa6d7  ldarg.2
0xa6d8  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_ProductArch()
0xa6dd  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xa6e2  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0xa6e7  stloc.s  8
0xa6e9  ldarg.3
0xa6ea  ldloc.s  7
0xa6ec  ldloc.s  8
0xa6ee  ldarg.0
0xa6ef  ldfld    valuetype [mscorlib]System.StringComparison Microsoft.VisualStudio.Setup.PackageIdentityComparer::comparisonType
0xa6f4  callvirt instance var<u1> class [mscorlib]System.Func`4<string, string, valuetype [mscorlib]System.StringComparison, mvar<u1>>::Invoke(char, var<u1>, !!T0)
0xa6f9  stloc.0
0xa6fa  ldarg.s  5
0xa6fc  ldloc.0
0xa6fd  callvirt instance var<u1> class [mscorlib]System.Func`2<mvar<u1>, !!T0>::Invoke(void)
0xa702  brtrue.s loc_A706
0xa704  ldloc.0
0xa705  ret
0xa706  ldarg.1
0xa707  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_TargetSDK()
0xa70c  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xa711  stloc.s  9
0xa713  ldarg.2
0xa714  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_TargetSDK()
0xa719  call     string Microsoft.VisualStudio.Setup.Utilities::NormalizeIdentityToken(string token)
0xa71e  stloc.s  0xA
0xa720  ldarg.3
0xa721  ldloc.s  9
0xa723  ldloc.s  0xA
0xa725  ldarg.0
0xa726  ldfld    valuetype [mscorlib]System.StringComparison Microsoft.VisualStudio.Setup.PackageIdentityComparer::comparisonType
0xa72b  callvirt instance var<u1> class [mscorlib]System.Func`4<string, string, valuetype [mscorlib]System.StringComparison, mvar<u1>>::Invoke(char, var<u1>, !!T0)
0xa730  stloc.0
0xa731  ldloc.0
0xa732  ret
```
