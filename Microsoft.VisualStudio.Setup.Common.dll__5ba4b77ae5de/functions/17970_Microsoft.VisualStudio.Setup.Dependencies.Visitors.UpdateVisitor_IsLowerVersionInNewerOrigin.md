# Microsoft.VisualStudio.Setup.Dependencies.Visitors.UpdateVisitor::IsLowerVersionInNewerOrigin

- ea: `0x17970`
- end: `0x179ce`
- name: `Microsoft.VisualStudio.Setup.Dependencies.Visitors.UpdateVisitor::IsLowerVersionInNewerOrigin`
- size: `94`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x17660`
- `0x17890`

## callees

- `0x5950`
- `0x80d0`
- `0x9910`
- `0x17970`

## pseudocode

```c

```

## disassembly

```asm
0x17970  ldarg.2
0x17971  callvirt instance class Microsoft.VisualStudio.Setup.OriginInfo Microsoft.VisualStudio.Setup.IPackage::get_Origin()
0x17976  dup
0x17977  brtrue.s loc_1797D
0x17979  pop
0x1797a  ldnull
0x1797b  br.s     loc_17982
0x1797d  call     instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.OriginInfo::get_ManifestBuildVersion()
0x17982  stloc.0
0x17983  ldarg.1
0x17984  callvirt instance class Microsoft.VisualStudio.Setup.OriginInfo Microsoft.VisualStudio.Setup.IPackage::get_Origin()
0x17989  dup
0x1798a  brtrue.s loc_17990
0x1798c  pop
0x1798d  ldnull
0x1798e  br.s     loc_17995
0x17990  call     instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.OriginInfo::get_ManifestBuildVersion()
0x17995  stloc.1
0x17996  ldarg.1
0x17997  call     bool Microsoft.VisualStudio.Setup.Extensions::IsExternal(class Microsoft.VisualStudio.Setup.IPackage package)
0x1799c  brfalse.s loc_179A0
0x1799e  ldc.i4.0
0x1799f  ret
0x179a0  ldloc.0
0x179a1  brfalse.s loc_179A6
0x179a3  ldloc.1
0x179a4  brtrue.s loc_179A8
0x179a6  ldc.i4.0
0x179a7  ret
0x179a8  ldloc.0
0x179a9  ldarg.0
0x179aa  ldfld    class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Dependencies.Visitors.UpdateVisitor::defaultVersion
0x179af  call     bool [mscorlib]System.Version::op_LessThanOrEqual(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x179b4  brtrue.s loc_179C4
0x179b6  ldloc.1
0x179b7  ldarg.0
0x179b8  ldfld    class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Dependencies.Visitors.UpdateVisitor::defaultVersion
0x179bd  call     bool [mscorlib]System.Version::op_LessThanOrEqual(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x179c2  brfalse.s loc_179C6
0x179c4  ldc.i4.0
0x179c5  ret
0x179c6  ldloc.0
0x179c7  ldloc.1
0x179c8  call     bool [mscorlib]System.Version::op_GreaterThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x179cd  ret
```
