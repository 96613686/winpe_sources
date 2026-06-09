# Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::Downgrade

- ea: `0x16e40`
- end: `0x16e6c`
- name: `Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::Downgrade`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x16d00`
- `0x17660`

## callees

- `0x5950`
- `0x5fd0`
- `0x61d0`
- `0x16b70`
- `0x16e40`

## pseudocode

```c

```

## disassembly

```asm
0x16e40  ldarg.0
0x16e41  ldc.i4.1
0x16e42  stfld    bool Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::shouldDowngrade
0x16e47  ldarg.1
0x16e48  call     string Microsoft.VisualStudio.Setup.Extensions::GetManifestId(class Microsoft.VisualStudio.Setup.IPackage package)
0x16e4d  stloc.0
0x16e4e  ldloc.0
0x16e4f  call     bool Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string source)
0x16e54  brtrue.s loc_16E6B
0x16e56  ldarg.1
0x16e57  call     bool Microsoft.VisualStudio.Setup.Extensions::IsExternal(class Microsoft.VisualStudio.Setup.IPackage package)
0x16e5c  brfalse.s loc_16E6B
0x16e5e  ldarg.0
0x16e5f  call     instance class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::get_CatalogsToUninstall()
0x16e64  ldloc.0
0x16e65  callvirt instance bool class [System]System.Collections.Generic.ISet`1<string>::Add(var<u1>)
0x16e6a  pop
0x16e6b  ret
```
