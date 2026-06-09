# Microsoft.VisualStudio.Setup.Cache.PackageReference::InitializePackageReference

- ea: `0x1b920`
- end: `0x1b9b1`
- name: `Microsoft.VisualStudio.Setup.Cache.PackageReference::InitializePackageReference`
- size: `145`
- prototype: ``
- caller_count: `4`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x195b0`
- `0x1b900`
- `0x1bca0`
- `0x1bea0`

## callees

- `0x6b40`
- `0x7ee0`
- `0x81e0`
- `0x81f0`
- `0x8200`
- `0x8210`
- `0x8220`
- `0x8230`
- `0x8240`
- `0x8250`
- `0x1b920`
- `0x1b9d0`
- `0x1b9f0`
- `0x1ba10`
- `0x1ba30`
- `0x1ba50`
- `0x1ba70`
- `0x1ba90`
- `0x1bab0`
- `0x1bad0`
- `0x1baf0`

## pseudocode

```c

```

## disassembly

```asm
0x1b920  ldarg.0
0x1b921  ldarg.1
0x1b922  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x1b927  callvirt instance void Microsoft.VisualStudio.Setup.Cache.PackageReference::set_Id(string value)
0x1b92c  ldarg.0
0x1b92d  ldarg.1
0x1b92e  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.IPackageIdentity::get_Version()
0x1b933  callvirt instance void Microsoft.VisualStudio.Setup.Cache.PackageReference::set_Version(class [mscorlib]System.Version value)
0x1b938  ldarg.0
0x1b939  ldarg.1
0x1b93a  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Chip()
0x1b93f  callvirt instance void Microsoft.VisualStudio.Setup.Cache.PackageReference::set_Chip(string value)
0x1b944  ldarg.0
0x1b945  ldarg.1
0x1b946  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Language()
0x1b94b  callvirt instance void Microsoft.VisualStudio.Setup.Cache.PackageReference::set_Language(string value)
0x1b950  ldarg.0
0x1b951  ldarg.1
0x1b952  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Branch()
0x1b957  callvirt instance void Microsoft.VisualStudio.Setup.Cache.PackageReference::set_Branch(string value)
0x1b95c  ldarg.0
0x1b95d  ldarg.1
0x1b95e  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_ProductArch()
0x1b963  callvirt instance void Microsoft.VisualStudio.Setup.Cache.PackageReference::set_ProductArch(string value)
0x1b968  ldarg.0
0x1b969  ldarg.1
0x1b96a  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_MachineArch()
0x1b96f  callvirt instance void Microsoft.VisualStudio.Setup.Cache.PackageReference::set_MachineArch(string value)
0x1b974  ldarg.0
0x1b975  ldarg.1
0x1b976  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_TargetSDK()
0x1b97b  callvirt instance void Microsoft.VisualStudio.Setup.Cache.PackageReference::set_TargetSDK(string value)
0x1b980  ldarg.0
0x1b981  ldarg.1
0x1b982  isinst   Microsoft.VisualStudio.Setup.IPackage
0x1b987  dup
0x1b988  brtrue.s loc_1B98E
0x1b98a  pop
0x1b98b  ldc.i4.0
0x1b98c  br.s     loc_1B993
0x1b98e  callvirt instance valuetype Microsoft.VisualStudio.Setup.PackageType Microsoft.VisualStudio.Setup.IPackage::get_Type()
0x1b993  callvirt instance void Microsoft.VisualStudio.Setup.Cache.PackageReference::set_Type(valuetype Microsoft.VisualStudio.Setup.PackageType value)
0x1b998  ldarg.0
0x1b999  ldarg.1
0x1b99a  isinst   Microsoft.VisualStudio.Setup.IExtensionPackage
0x1b99f  dup
0x1b9a0  brtrue.s loc_1B9A6
0x1b9a2  pop
0x1b9a3  ldc.i4.0
0x1b9a4  br.s     loc_1B9AB
0x1b9a6  callvirt instance bool Microsoft.VisualStudio.Setup.IExtensionPackage::get_IsExtension()
0x1b9ab  callvirt instance void Microsoft.VisualStudio.Setup.Cache.PackageReference::set_IsExtension(bool value)
0x1b9b0  ret
```
