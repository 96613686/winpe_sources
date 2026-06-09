# Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::DowngradeNode

- ea: `0x16e70`
- end: `0x16f90`
- name: `Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::DowngradeNode`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x172e0`

## callees

- `0x7f00`
- `0x7f50`
- `0x8090`
- `0x81e0`
- `0x8320`
- `0x8330`
- `0x140c0`
- `0x16130`
- `0x161a0`
- `0x161d0`
- `0x161f0`
- `0x164a0`
- `0x164b0`
- `0x164c0`
- `0x16690`
- `0x166c0`
- `0x16bf0`
- `0x16e70`
- `0x1d6d0`

## pseudocode

```c

```

## disassembly

```asm
0x16e70  ldarg.1
0x16e71  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x16e76  stloc.0
0x16e77  ldloc.0
0x16e78  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x16e7d  ldloc.0
0x16e7e  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.IPackage::get_DowngradingPackage()
0x16e83  newobj   instance void Microsoft.VisualStudio.Setup.Dependencies.DependencyNode::.ctor(string id, class Microsoft.VisualStudio.Setup.IPackage package)
0x16e88  stloc.1
0x16e89  ldloc.1
0x16e8a  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.DependencyNode::get_Package()
0x16e8f  ldc.i4.3
0x16e90  callvirt instance void Microsoft.VisualStudio.Setup.IPackage::set_RequestedState(valuetype Microsoft.VisualStudio.Setup.RequestedState value)
0x16e95  ldloc.1
0x16e96  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.DependencyNode::get_Package()
0x16e9b  isinst   Microsoft.VisualStudio.Setup.ISelectablePackage
0x16ea0  stloc.2
0x16ea1  ldloc.2
0x16ea2  brfalse.s loc_16EBF
0x16ea4  ldarg.1
0x16ea5  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x16eaa  isinst   Microsoft.VisualStudio.Setup.ISelectablePackage
0x16eaf  stloc.3
0x16eb0  ldloc.3
0x16eb1  brfalse.s loc_16EBF
0x16eb3  ldloc.2
0x16eb4  ldloc.3
0x16eb5  callvirt instance valuetype Microsoft.VisualStudio.Setup.SelectedState Microsoft.VisualStudio.Setup.ISelectablePackage::get_SelectedState()
0x16eba  callvirt instance void Microsoft.VisualStudio.Setup.ISelectablePackage::set_SelectedState(valuetype Microsoft.VisualStudio.Setup.SelectedState value)
0x16ebf  ldarg.1
0x16ec0  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc> Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Children()
0x16ec5  stloc.s  4
0x16ec7  ldloc.0
0x16ec8  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.IPackage::get_DowngradingPackage()
0x16ecd  callvirt instance class Microsoft.VisualStudio.Setup.DependencyCollection Microsoft.VisualStudio.Setup.IPackage::get_Dependencies()
0x16ed2  brfalse.s loc_16F19
0x16ed4  ldloc.0
0x16ed5  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.IPackage::get_DowngradingPackage()
0x16eda  callvirt instance class Microsoft.VisualStudio.Setup.DependencyCollection Microsoft.VisualStudio.Setup.IPackage::get_Dependencies()
0x16edf  call     T0x2B000096
0x16ee4  brfalse.s loc_16F19
0x16ee6  newobj   instance void <>c__DisplayClass26_0::.ctor()
0x16eeb  stloc.s  5
0x16eed  ldloc.s  5
0x16eef  ldloc.0
0x16ef0  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.IPackage::get_DowngradingPackage()
0x16ef5  callvirt instance class Microsoft.VisualStudio.Setup.DependencyCollection Microsoft.VisualStudio.Setup.IPackage::get_Dependencies()
0x16efa  stfld    class Microsoft.VisualStudio.Setup.DependencyCollection <>c__DisplayClass26_0::dependencies
0x16eff  ldarg.1
0x16f00  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc> Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Children()
0x16f05  ldloc.s  5
0x16f07  ldftn    instance bool <>c__DisplayClass26_0::<DowngradeNode>b__0(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc arc)
0x16f0d  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc, bool>::.ctor(object, native int)
0x16f12  call     T0x2B000094
0x16f17  stloc.s  4
0x16f19  ldloc.s  4
0x16f1b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc>::GetEnumerator()
0x16f20  stloc.s  6
0x16f22  br.s     loc_16F70
0x16f24  ldloc.s  6
0x16f26  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc>::get_Current()
0x16f2b  stloc.s  7
0x16f2d  ldloc.1
0x16f2e  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc> Microsoft.VisualStudio.Setup.Dependencies.DependencyNode::get_Children()
0x16f33  ldloc.s  7
0x16f35  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc>::Add(var<u1>)
0x16f3a  ldloc.s  7
0x16f3c  callvirt instance class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc::get_Node()
0x16f41  isinst   Microsoft.VisualStudio.Setup.Dependencies.DependencyNode
0x16f46  stloc.s  8
0x16f48  ldloc.s  8
0x16f4a  brfalse.s loc_16F70
0x16f4c  ldloc.1
0x16f4d  ldloc.s  7
0x16f4f  callvirt instance valuetype Microsoft.VisualStudio.Setup.DependencyType Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc::get_Type()
0x16f54  ldloc.s  7
0x16f56  callvirt instance valuetype Microsoft.VisualStudio.Setup.DependencyBehaviors Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc::get_Behaviors()
0x16f5b  newobj   instance void Microsoft.VisualStudio.Setup.Dependencies.DependencyArc::.ctor(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node, valuetype Microsoft.VisualStudio.Setup.DependencyType type, valuetype Microsoft.VisualStudio.Setup.DependencyBehaviors behaviors)
0x16f60  stloc.s  9
0x16f62  ldloc.s  8
0x16f64  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc> Microsoft.VisualStudio.Setup.Dependencies.DependencyNode::get_Parents()
0x16f69  ldloc.s  9
0x16f6b  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc>::Add(var<u1>)
0x16f70  ldloc.s  6
0x16f72  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x16f77  brtrue.s loc_16F24
0x16f79  leave.s  loc_16F87
0x16f7b  ldloc.s  6
0x16f7d  brfalse.s loc_16F86
0x16f7f  ldloc.s  6
0x16f81  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16f86  endfinally
0x16f87  ldarg.0
0x16f88  ldloc.1
0x16f89  callvirt instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::PostNodeVisit(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node)
0x16f8e  ldloc.1
0x16f8f  ret
```
