# Microsoft.VisualStudio.Setup.Dependencies.Visitors.UpdateVisitor::VersionCheck

- ea: `0x17890`
- end: `0x17968`
- name: `Microsoft.VisualStudio.Setup.Dependencies.Visitors.UpdateVisitor::VersionCheck`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x17660`

## callees

- `0x80d0`
- `0x81e0`
- `0x81f0`
- `0x98b0`
- `0x15650`
- `0x163a0`
- `0x16690`
- `0x17890`
- `0x17970`
- `0x1d7f0`

## pseudocode

```c

```

## disassembly

```asm
0x17890  newobj   instance void <>c__DisplayClass6_0::.ctor()
0x17895  stloc.0
0x17896  ldloc.0
0x17897  ldarg.1
0x17898  stfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass6_0::node
0x1789d  ldloc.0
0x1789e  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass6_0::node
0x178a3  ldloc.0
0x178a4  ldftn    instance bool <>c__DisplayClass6_0::<VersionCheck>b__0(class Microsoft.VisualStudio.Setup.IPackage c)
0x178aa  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.IPackage, bool>::.ctor(object, native int)
0x178af  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.IPackage> Microsoft.VisualStudio.Setup.Dependencies.Extensions::GetCandidates(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node, [opt] class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.IPackage, bool> predicate)
0x178b4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.IPackage>::GetEnumerator()
0x178b9  stloc.1
0x178ba  br       loc_17950
0x178bf  ldloc.1
0x178c0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.IPackage>::get_Current()
0x178c5  stloc.2
0x178c6  ldarg.0
0x178c7  ldloc.0
0x178c8  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass6_0::node
0x178cd  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x178d2  ldloc.2
0x178d3  call     instance bool Microsoft.VisualStudio.Setup.Dependencies.Visitors.UpdateVisitor::IsLowerVersionInNewerOrigin(class Microsoft.VisualStudio.Setup.IPackage newestPackage, class Microsoft.VisualStudio.Setup.IPackage olderPackage)
0x178d8  brfalse.s loc_17950
0x178da  ldstr    aLowerpackageer// "LowerPackageError_Args5"
0x178df  ldc.i4.5
0x178e0  newarr   [mscorlib]System.Object
0x178e5  dup
0x178e6  ldc.i4.0
0x178e7  ldloc.2
0x178e8  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x178ed  stelem.ref
0x178ee  dup
0x178ef  ldc.i4.1
0x178f0  ldloc.2
0x178f1  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.IPackageIdentity::get_Version()
0x178f6  stelem.ref
0x178f7  dup
0x178f8  ldc.i4.2
0x178f9  ldloc.2
0x178fa  callvirt instance class Microsoft.VisualStudio.Setup.OriginInfo Microsoft.VisualStudio.Setup.IPackage::get_Origin()
0x178ff  dup
0x17900  brtrue.s loc_17906
0x17902  pop
0x17903  ldnull
0x17904  br.s     loc_1790B
0x17906  call     instance string Microsoft.VisualStudio.Setup.OriginInfo::get_ManifestId()
0x1790b  stelem.ref
0x1790c  dup
0x1790d  ldc.i4.3
0x1790e  ldloc.0
0x1790f  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass6_0::node
0x17914  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x17919  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.IPackageIdentity::get_Version()
0x1791e  stelem.ref
0x1791f  dup
0x17920  ldc.i4.4
0x17921  ldloc.0
0x17922  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass6_0::node
0x17927  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x1792c  callvirt instance class Microsoft.VisualStudio.Setup.OriginInfo Microsoft.VisualStudio.Setup.IPackage::get_Origin()
0x17931  dup
0x17932  brtrue.s loc_17938
0x17934  pop
0x17935  ldnull
0x17936  br.s     loc_1793D
0x17938  call     instance string Microsoft.VisualStudio.Setup.OriginInfo::get_ManifestId()
0x1793d  stelem.ref
0x1793e  newobj   instance void Microsoft.VisualStudio.Setup.Dependencies.DependencyGraphConstructionException::.ctor(string resourceId, object[] args)
0x17943  stloc.3
0x17944  ldarg.0
0x17945  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class [mscorlib]System.Exception> Microsoft.VisualStudio.Setup.Dependencies.Visitors.UpdateVisitor::nonFatalExceptions
0x1794a  ldloc.3
0x1794b  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [mscorlib]System.Exception>::Add(var<u1>)
0x17950  ldloc.1
0x17951  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x17956  brtrue   loc_178BF
0x1795b  leave.s  loc_17967
0x1795d  ldloc.1
0x1795e  brfalse.s loc_17966
0x17960  ldloc.1
0x17961  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17966  endfinally
0x17967  ret
```
