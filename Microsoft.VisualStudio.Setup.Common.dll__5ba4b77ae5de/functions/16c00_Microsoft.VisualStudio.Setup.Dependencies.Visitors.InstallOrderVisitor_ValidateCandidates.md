# Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::ValidateCandidates

- ea: `0x16c00`
- end: `0x16cfd`
- name: `Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::ValidateCandidates`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x16d00`

## callees

- `0x5950`
- `0x5fd0`
- `0x6040`
- `0x61d0`
- `0x7f20`
- `0x81e0`
- `0x15650`
- `0x163a0`
- `0x16690`
- `0x166a0`
- `0x16b70`
- `0x16c00`

## string_xrefs

- `0x16c7c`: `OlderExtensionPackages_Args1`

## pseudocode

```c

```

## disassembly

```asm
0x16c00  ldarg.1
0x16c01  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<class Microsoft.VisualStudio.Setup.IPackage> Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_CandidatePackageIds()
0x16c06  callvirt instance int32 class [mscorlib]System.Collections.Generic.IReadOnlyCollection`1<class Microsoft.VisualStudio.Setup.IPackage>::get_Count()
0x16c0b  ldc.i4.1
0x16c0c  ble      loc_16CFC
0x16c11  ldarg.1
0x16c12  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x16c17  stloc.0
0x16c18  ldloc.0
0x16c19  call     string Microsoft.VisualStudio.Setup.Extensions::GetManifestName(class Microsoft.VisualStudio.Setup.IPackage package)
0x16c1e  stloc.1
0x16c1f  ldarg.1
0x16c20  ldnull
0x16c21  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.IPackage> Microsoft.VisualStudio.Setup.Dependencies.Extensions::GetCandidates(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node, [opt] class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.IPackage, bool> predicate)
0x16c26  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.IPackage>::GetEnumerator()
0x16c2b  stloc.2
0x16c2c  br       loc_16CE5
0x16c31  ldloc.2
0x16c32  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.IPackage>::get_Current()
0x16c37  stloc.3
0x16c38  ldloc.3
0x16c39  call     string Microsoft.VisualStudio.Setup.Extensions::GetManifestName(class Microsoft.VisualStudio.Setup.IPackage package)
0x16c3e  stloc.s  4
0x16c40  ldloc.s  4
0x16c42  call     bool Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string source)
0x16c47  brtrue   loc_16CE5
0x16c4c  ldloc.3
0x16c4d  call     bool Microsoft.VisualStudio.Setup.Extensions::IsExternal(class Microsoft.VisualStudio.Setup.IPackage package)
0x16c52  brfalse  loc_16CE5
0x16c57  ldloc.1
0x16c58  call     bool Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string source)
0x16c5d  brtrue.s loc_16C67
0x16c5f  ldloc.0
0x16c60  call     bool Microsoft.VisualStudio.Setup.Extensions::IsExternal(class Microsoft.VisualStudio.Setup.IPackage package)
0x16c65  brtrue.s loc_16CA2
0x16c67  ldloc.3
0x16c68  call     string Microsoft.VisualStudio.Setup.Extensions::GetManifestId(class Microsoft.VisualStudio.Setup.IPackage package)
0x16c6d  stloc.s  5
0x16c6f  ldloc.s  5
0x16c71  brfalse.s loc_16CE5
0x16c73  ldloc.0
0x16c74  callvirt instance valuetype Microsoft.VisualStudio.Setup.CurrentState Microsoft.VisualStudio.Setup.IPackage::get_CurrentState()
0x16c79  ldc.i4.3
0x16c7a  bne.un.s loc_16C92
0x16c7c  ldstr    aOlderextension// "OlderExtensionPackages_Args1"
0x16c81  ldc.i4.1
0x16c82  newarr   [mscorlib]System.Object
0x16c87  dup
0x16c88  ldc.i4.0
0x16c89  ldloc.s  5
0x16c8b  stelem.ref
0x16c8c  newobj   instance void Microsoft.VisualStudio.Setup.Dependencies.DependencyGraphConstructionException::.ctor(string resourceId, object[] args)
0x16c91  throw
0x16c92  ldarg.0
0x16c93  call     instance class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::get_CatalogsToUninstall()
0x16c98  ldloc.s  5
0x16c9a  callvirt instance bool class [System]System.Collections.Generic.ISet`1<string>::Add(var<u1>)
0x16c9f  pop
0x16ca0  leave.s  loc_16CFC
0x16ca2  ldsfld   class [mscorlib]System.StringComparer Microsoft.VisualStudio.Setup.ManifestIdentityComparer::StringComparer
0x16ca7  ldloc.1
0x16ca8  ldloc.s  4
0x16caa  callvirt instance bool [mscorlib]System.StringComparer::Equals(string, string)
0x16caf  brtrue.s loc_16CE5
0x16cb1  ldloc.0
0x16cb2  call     string Microsoft.VisualStudio.Setup.Extensions::GetManifestId(class Microsoft.VisualStudio.Setup.IPackage package)
0x16cb7  stloc.s  6
0x16cb9  ldloc.3
0x16cba  call     string Microsoft.VisualStudio.Setup.Extensions::GetManifestId(class Microsoft.VisualStudio.Setup.IPackage package)
0x16cbf  stloc.s  7
0x16cc1  ldstr    aOverlappingexp// "OverlappingExperimentError_Args3"
0x16cc6  ldc.i4.3
0x16cc7  newarr   [mscorlib]System.Object
0x16ccc  dup
0x16ccd  ldc.i4.0
0x16cce  ldloc.s  6
0x16cd0  stelem.ref
0x16cd1  dup
0x16cd2  ldc.i4.1
0x16cd3  ldloc.s  7
0x16cd5  stelem.ref
0x16cd6  dup
0x16cd7  ldc.i4.2
0x16cd8  ldloc.0
0x16cd9  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x16cde  stelem.ref
0x16cdf  newobj   instance void Microsoft.VisualStudio.Setup.Dependencies.DependencyGraphConstructionException::.ctor(string resourceId, object[] args)
0x16ce4  throw
0x16ce5  ldloc.2
0x16ce6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x16ceb  brtrue   loc_16C31
0x16cf0  leave.s  loc_16CFC
0x16cf2  ldloc.2
0x16cf3  brfalse.s loc_16CFB
0x16cf5  ldloc.2
0x16cf6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16cfb  endfinally
0x16cfc  ret
```
