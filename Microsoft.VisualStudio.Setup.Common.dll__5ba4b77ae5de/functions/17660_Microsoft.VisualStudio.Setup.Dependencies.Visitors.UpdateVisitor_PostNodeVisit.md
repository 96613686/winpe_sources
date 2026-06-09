# Microsoft.VisualStudio.Setup.Dependencies.Visitors.UpdateVisitor::PostNodeVisit

- ea: `0x17660`
- end: `0x1788c`
- name: `Microsoft.VisualStudio.Setup.Dependencies.Visitors.UpdateVisitor::PostNodeVisit`
- size: `556`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `installer_update, broker_com_uri`

## callees

- `0x5950`
- `0x5ec0`
- `0x5ed0`
- `0x7ee0`
- `0x7f30`
- `0x7f40`
- `0x7f50`
- `0x8060`
- `0x8090`
- `0x80a0`
- `0x81e0`
- `0x81f0`
- `0x15650`
- `0x16130`
- `0x161d0`
- `0x161f0`
- `0x163a0`
- `0x16690`
- `0x166b0`
- `0x166c0`
- `0x16b60`
- `0x16bf0`
- `0x16e40`
- `0x17660`
- `0x17890`
- `0x17970`
- `0x18f40`
- `0x1d790`

## pseudocode

```c

```

## disassembly

```asm
0x17660  newobj   instance void <>c__DisplayClass5_0::.ctor()
0x17665  stloc.0
0x17666  ldloc.0
0x17667  ldarg.1
0x17668  stfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x1766d  ldloc.0
0x1766e  ldarg.0
0x1766f  stfld    class Microsoft.VisualStudio.Setup.Dependencies.Visitors.UpdateVisitor <>c__DisplayClass5_0::<>4__this
0x17674  ldarg.0
0x17675  ldloc.0
0x17676  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x1767b  call     instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::PostNodeVisit(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node)
0x17680  ldc.i4.0
0x17681  stloc.1
0x17682  ldarg.0
0x17683  ldloc.0
0x17684  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x17689  call     instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.UpdateVisitor::VersionCheck(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node)
0x1768e  ldloc.0
0x1768f  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x17694  ldloc.0
0x17695  ldftn    instance bool <>c__DisplayClass5_0::<PostNodeVisit>b__0(class Microsoft.VisualStudio.Setup.IPackage c)
0x1769b  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.IPackage, bool>::.ctor(object, native int)
0x176a0  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.IPackage> Microsoft.VisualStudio.Setup.Dependencies.Extensions::GetCandidates(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node, [opt] class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.IPackage, bool> predicate)
0x176a5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.IPackage>::GetEnumerator()
0x176aa  stloc.2
0x176ab  br.s     loc_1771E
0x176ad  ldloc.2
0x176ae  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.IPackage>::get_Current()
0x176b3  stloc.3
0x176b4  ldc.i4.1
0x176b5  stloc.1
0x176b6  ldloc.3
0x176b7  ldc.i4.2
0x176b8  callvirt instance void Microsoft.VisualStudio.Setup.IPackage::set_CurrentState(valuetype Microsoft.VisualStudio.Setup.CurrentState value)
0x176bd  ldloc.3
0x176be  ldc.i4.1
0x176bf  callvirt instance void Microsoft.VisualStudio.Setup.IPackage::set_RequestedState(valuetype Microsoft.VisualStudio.Setup.RequestedState value)
0x176c4  ldloc.3
0x176c5  ldloc.0
0x176c6  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x176cb  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x176d0  callvirt instance void Microsoft.VisualStudio.Setup.IPackage::set_SupersedingPackage(class Microsoft.VisualStudio.Setup.IPackage value)
0x176d5  ldloc.3
0x176d6  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x176db  ldloc.3
0x176dc  newobj   instance void Microsoft.VisualStudio.Setup.Dependencies.DependencyNode::.ctor(string id, class Microsoft.VisualStudio.Setup.IPackage package)
0x176e1  stloc.s  4
0x176e3  ldloc.s  4
0x176e5  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc> Microsoft.VisualStudio.Setup.Dependencies.DependencyNode::get_Parents()
0x176ea  ldloc.0
0x176eb  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x176f0  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc> Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Parents()
0x176f5  call     T0x2B00009B
0x176fa  ldloc.s  4
0x176fc  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc> Microsoft.VisualStudio.Setup.Dependencies.DependencyNode::get_Children()
0x17701  ldloc.0
0x17702  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x17707  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc> Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Children()
0x1770c  call     T0x2B00009B
0x17711  ldarg.0
0x17712  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> Microsoft.VisualStudio.Setup.Dependencies.Visitors.UpdateVisitor::uninstalls
0x17717  ldloc.s  4
0x17719  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::Add(var<u1>)
0x1771e  ldloc.2
0x1771f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x17724  brtrue.s loc_176AD
0x17726  leave.s  loc_17732
0x17728  ldloc.2
0x17729  brfalse.s loc_17731
0x1772b  ldloc.2
0x1772c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17731  endfinally
0x17732  ldloc.1
0x17733  brfalse.s loc_17759
0x17735  ldloc.0
0x17736  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x1773b  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x17740  callvirt instance valuetype Microsoft.VisualStudio.Setup.RequestedState Microsoft.VisualStudio.Setup.IPackage::get_RequestedState()
0x17745  brtrue.s loc_17758
0x17747  ldloc.0
0x17748  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x1774d  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x17752  ldc.i4.3
0x17753  callvirt instance void Microsoft.VisualStudio.Setup.IPackage::set_RequestedState(valuetype Microsoft.VisualStudio.Setup.RequestedState value)
0x17758  ret
0x17759  ldloc.0
0x1775a  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x1775f  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x17764  call     bool Microsoft.VisualStudio.Setup.Extensions::IsExternal(class Microsoft.VisualStudio.Setup.IPackage package)
0x17769  brfalse.s loc_1776C
0x1776b  ret
0x1776c  ldarg.0
0x1776d  call     instance class Microsoft.VisualStudio.Setup.Cache.ICacheManager Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::get_Cache()
0x17772  ldloc.0
0x17773  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x17778  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x1777d  call     bool Microsoft.VisualStudio.Setup.Cache.CommonExtensions::IsInstalled(class Microsoft.VisualStudio.Setup.Cache.ICacheManager manager, class Microsoft.VisualStudio.Setup.IPackageIdentity identity)
0x17782  brtrue.s loc_17785
0x17784  ret
0x17785  ldloc.0
0x17786  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x1778b  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x17790  call     bool Microsoft.VisualStudio.Setup.Extensions::IsDowngradable(class Microsoft.VisualStudio.Setup.IPackage package)
0x17795  brtrue.s loc_17798
0x17797  ret
0x17798  ldarg.0
0x17799  ldloc.0
0x1779a  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x1779f  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x177a4  ldloc.0
0x177a5  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x177aa  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x177af  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.IPackage::get_DowngradingPackage()
0x177b4  call     instance bool Microsoft.VisualStudio.Setup.Dependencies.Visitors.UpdateVisitor::IsLowerVersionInNewerOrigin(class Microsoft.VisualStudio.Setup.IPackage newestPackage, class Microsoft.VisualStudio.Setup.IPackage olderPackage)
0x177b9  brfalse.s loc_177CD
0x177bb  ldloc.0
0x177bc  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x177c1  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x177c6  ldnull
0x177c7  callvirt instance void Microsoft.VisualStudio.Setup.IPackage::set_DowngradingPackage(class Microsoft.VisualStudio.Setup.IPackage value)
0x177cc  ret
0x177cd  ldloc.0
0x177ce  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x177d3  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x177d8  call     bool Microsoft.VisualStudio.Setup.Extensions::IsInstanceDowngradableType(class Microsoft.VisualStudio.Setup.IPackage package)
0x177dd  brtrue   loc_17869
0x177e2  ldstr    aDowngradereque// "DowngradeRequestedForUnsupportedPackage"...
0x177e7  ldc.i4.4
0x177e8  newarr   [mscorlib]System.Object
0x177ed  dup
0x177ee  ldc.i4.0
0x177ef  ldloc.0
0x177f0  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x177f5  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x177fa  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x177ff  stelem.ref
0x17800  dup
0x17801  ldc.i4.1
0x17802  ldloc.0
0x17803  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x17808  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x1780d  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.IPackageIdentity::get_Version()
0x17812  stelem.ref
0x17813  dup
0x17814  ldc.i4.2
0x17815  ldloc.0
0x17816  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x1781b  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x17820  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.IPackage::get_DowngradingPackage()
0x17825  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.IPackageIdentity::get_Version()
0x1782a  stelem.ref
0x1782b  dup
0x1782c  ldc.i4.3
0x1782d  ldloc.0
0x1782e  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x17833  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x17838  callvirt instance valuetype Microsoft.VisualStudio.Setup.PackageType Microsoft.VisualStudio.Setup.IPackage::get_Type()
0x1783d  box      Microsoft.VisualStudio.Setup.PackageType
0x17842  stelem.ref
0x17843  newobj   instance void Microsoft.VisualStudio.Setup.Dependencies.DependencyGraphConstructionException::.ctor(string resourceId, object[] args)
0x17848  stloc.s  5
0x1784a  ldarg.0
0x1784b  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class [mscorlib]System.Exception> Microsoft.VisualStudio.Setup.Dependencies.Visitors.UpdateVisitor::nonFatalExceptions
0x17850  ldloc.s  5
0x17852  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [mscorlib]System.Exception>::Add(var<u1>)
0x17857  ldloc.0
0x17858  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x1785d  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x17862  ldnull
0x17863  callvirt instance void Microsoft.VisualStudio.Setup.IPackage::set_DowngradingPackage(class Microsoft.VisualStudio.Setup.IPackage value)
0x17868  ret
0x17869  ldloc.0
0x1786a  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x1786f  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x17874  ldc.i4.4
0x17875  callvirt instance void Microsoft.VisualStudio.Setup.IPackage::set_RequestedState(valuetype Microsoft.VisualStudio.Setup.RequestedState value)
0x1787a  ldarg.0
0x1787b  ldloc.0
0x1787c  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c__DisplayClass5_0::node
0x17881  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x17886  call     instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::Downgrade(class Microsoft.VisualStudio.Setup.IPackage package)
0x1788b  ret
```
