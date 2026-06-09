# Microsoft.VisualStudio.Setup.Extensions::IsVitalToInstallOperation

- ea: `0x5d90`
- end: `0x5dea`
- name: `Microsoft.VisualStudio.Setup.Extensions::IsVitalToInstallOperation`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x5d90`

## callees

- `0x5d90`
- `0x7ee0`
- `0x8010`
- `0x8020`
- `0xc1a0`

## pseudocode

```c

```

## disassembly

```asm
0x5d90  ldarg.0
0x5d91  ldstr    aPackage// "package"
0x5d96  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x5d9b  ldarg.0
0x5d9c  callvirt instance valuetype Microsoft.VisualStudio.Setup.PackageType Microsoft.VisualStudio.Setup.IPackage::get_Type()
0x5da1  ldc.i4.6
0x5da2  bne.un.s loc_5DA6
0x5da4  ldc.i4.1
0x5da5  ret
0x5da6  ldc.i4.0
0x5da7  stloc.0
0x5da8  ldarg.0
0x5da9  callvirt instance class [System]System.Collections.Generic.ISet`1<class Microsoft.VisualStudio.Setup.IPackage> Microsoft.VisualStudio.Setup.IPackage::get_SelectedParents()
0x5dae  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.IPackage>::GetEnumerator()
0x5db3  stloc.1
0x5db4  br.s     loc_5DD4
0x5db6  ldloc.1
0x5db7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.IPackage>::get_Current()
0x5dbc  stloc.2
0x5dbd  ldloc.2
0x5dbe  callvirt instance class [System]System.Collections.Generic.ISet`1<class Microsoft.VisualStudio.Setup.IPackage> Microsoft.VisualStudio.Setup.IPackage::get_SelectedRequiredChildren()
0x5dc3  ldarg.0
0x5dc4  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.VisualStudio.Setup.IPackage>::Contains(var<u1>)
0x5dc9  brfalse.s loc_5DD4
0x5dcb  ldloc.0
0x5dcc  ldloc.2
0x5dcd  call     bool Microsoft.VisualStudio.Setup.Extensions::IsVitalToInstallOperation(class Microsoft.VisualStudio.Setup.IPackage package)
0x5dd2  or
0x5dd3  stloc.0
0x5dd4  ldloc.1
0x5dd5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5dda  brtrue.s loc_5DB6
0x5ddc  leave.s  loc_5DE8
0x5dde  ldloc.1
0x5ddf  brfalse.s loc_5DE7
0x5de1  ldloc.1
0x5de2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5de7  endfinally
0x5de8  ldloc.0
0x5de9  ret
```
