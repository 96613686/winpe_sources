# Microsoft.VisualStudio.Setup.Cache.FailedPackageReference::AddAffectedPackages

- ea: `0x196f0`
- end: `0x19735`
- name: `Microsoft.VisualStudio.Setup.Cache.FailedPackageReference::AddAffectedPackages`
- size: `69`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x195b0`
- `0x196f0`

## callees

- `0x8010`
- `0x196c0`
- `0x196f0`
- `0x1b900`

## pseudocode

```c

```

## disassembly

```asm
0x196f0  ldarg.1
0x196f1  callvirt instance class [System]System.Collections.Generic.ISet`1<class Microsoft.VisualStudio.Setup.IPackage> Microsoft.VisualStudio.Setup.IPackage::get_SelectedParents()
0x196f6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.IPackage>::GetEnumerator()
0x196fb  stloc.0
0x196fc  br.s     loc_19720
0x196fe  ldloc.0
0x196ff  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.IPackage>::get_Current()
0x19704  stloc.1
0x19705  ldloc.1
0x19706  call     class Microsoft.VisualStudio.Setup.Cache.PackageReference Microsoft.VisualStudio.Setup.Cache.PackageReference::FromIdentity(class Microsoft.VisualStudio.Setup.IPackageIdentity identity)
0x1970b  stloc.2
0x1970c  ldarg.0
0x1970d  call     instance class Microsoft.VisualStudio.Setup.Cache.PackageReferenceCollection Microsoft.VisualStudio.Setup.Cache.FailedPackageReference::get_AffectedPackages()
0x19712  ldloc.2
0x19713  callvirt instance bool class Microsoft.VisualStudio.Setup.Cache.IndexedCollection`1<class Microsoft.VisualStudio.Setup.Cache.PackageReference>::Add(var<u1>)
0x19718  pop
0x19719  ldarg.0
0x1971a  ldloc.1
0x1971b  call     instance void Microsoft.VisualStudio.Setup.Cache.FailedPackageReference::AddAffectedPackages(class Microsoft.VisualStudio.Setup.IPackage package)
0x19720  ldloc.0
0x19721  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19726  brtrue.s loc_196FE
0x19728  leave.s  loc_19734
0x1972a  ldloc.0
0x1972b  brfalse.s loc_19733
0x1972d  ldloc.0
0x1972e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19733  endfinally
0x19734  ret
```
