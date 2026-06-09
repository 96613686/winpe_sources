# Microsoft.VisualStudio.Setup.Dependencies.DependencyNodeComparer::Equals

- ea: `0x162e0`
- end: `0x1631d`
- name: `Microsoft.VisualStudio.Setup.Dependencies.DependencyNodeComparer::Equals`
- size: `61`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x16280`
- `0x168a0`

## callees

- `0xa7a0`
- `0x162e0`
- `0x16680`
- `0x16690`

## pseudocode

```c

```

## disassembly

```asm
0x162e0  ldarg.1
0x162e1  brtrue.s loc_162E8
0x162e3  ldarg.2
0x162e4  brtrue.s loc_162E8
0x162e6  ldc.i4.1
0x162e7  ret
0x162e8  ldarg.1
0x162e9  brfalse.s loc_162EE
0x162eb  ldarg.2
0x162ec  brtrue.s loc_162F0
0x162ee  ldc.i4.0
0x162ef  ret
0x162f0  ldarg.1
0x162f1  callvirt instance string Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Id()
0x162f6  ldarg.2
0x162f7  callvirt instance string Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Id()
0x162fc  ldc.i4.5
0x162fd  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x16302  brfalse.s loc_1631B
0x16304  ldsfld   class Microsoft.VisualStudio.Setup.PackageIdentityComparer Microsoft.VisualStudio.Setup.Dependencies.DependencyNodeComparer::PackageComparer
0x16309  ldarg.1
0x1630a  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x1630f  ldarg.2
0x16310  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x16315  callvirt instance bool Microsoft.VisualStudio.Setup.PackageIdentityComparer::Equals(class Microsoft.VisualStudio.Setup.IPackageIdentity x, class Microsoft.VisualStudio.Setup.IPackageIdentity y)
0x1631a  ret
0x1631b  ldc.i4.0
0x1631c  ret
```
