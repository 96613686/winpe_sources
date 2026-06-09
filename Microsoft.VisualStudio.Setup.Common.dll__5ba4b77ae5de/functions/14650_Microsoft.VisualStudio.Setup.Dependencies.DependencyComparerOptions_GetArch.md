# Microsoft.VisualStudio.Setup.Dependencies.DependencyComparerOptions::GetArch

- ea: `0x14650`
- end: `0x14689`
- name: `Microsoft.VisualStudio.Setup.Dependencies.DependencyComparerOptions::GetArch`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14620`

## callees

- `0x7ee0`
- `0x8200`
- `0x8230`
- `0x10900`
- `0x14650`

## pseudocode

```c

```

## disassembly

```asm
0x14650  ldarg.0
0x14651  brtrue.s loc_14655
0x14653  ldnull
0x14654  ret
0x14655  ldarg.0
0x14656  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_ProductArch()
0x1465b  stloc.0
0x1465c  ldarg.0
0x1465d  callvirt instance valuetype Microsoft.VisualStudio.Setup.PackageType Microsoft.VisualStudio.Setup.IPackage::get_Type()
0x14662  ldc.i4.6
0x14663  bne.un.s loc_14682
0x14665  ldloc.0
0x14666  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1466b  brfalse.s loc_14674
0x1466d  ldarg.0
0x1466e  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Chip()
0x14673  stloc.0
0x14674  ldloc.0
0x14675  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0x1467a  brtrue.s loc_14682
0x1467c  ldstr    aX86// "x86"
0x14681  stloc.0
0x14682  ldloc.0
0x14683  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0x14688  ret
```
