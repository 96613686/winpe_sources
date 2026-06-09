# Microsoft.VisualStudio.Setup.Dependencies.Visitors.SelectionVisitor::VisitNode

- ea: `0x173e0`
- end: `0x17598`
- name: `Microsoft.VisualStudio.Setup.Dependencies.Visitors.SelectionVisitor::VisitNode`
- size: `440`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callees

- `0x59a0`
- `0x5ec0`
- `0x7f40`
- `0x7f50`
- `0x8010`
- `0x8020`
- `0x8090`
- `0x8260`
- `0x8320`
- `0x8330`
- `0x8350`
- `0x11b00`
- `0x163d0`
- `0x164a0`
- `0x164b0`
- `0x16690`
- `0x166b0`
- `0x168e0`
- `0x16990`
- `0x173e0`

## string_xrefs

- `0x1757b`: `' will be removed: no previous version for downgrade.`

## pseudocode

```c

```

## disassembly

```asm
0x173e0  ldarg.1
0x173e1  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x173e6  stloc.0
0x173e7  ldc.i4.0
0x173e8  stloc.1
0x173e9  ldarg.1
0x173ea  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc> Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Parents()
0x173ef  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc>::GetEnumerator()
0x173f4  stloc.3
0x173f5  br       loc_174C1
0x173fa  ldloc.3
0x173fb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc>::get_Current()
0x17400  stloc.s  4
0x17402  ldloc.s  4
0x17404  callvirt instance class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc::get_Node()
0x17409  dup
0x1740a  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x1740f  stloc.s  5
0x17411  ldarg.0
0x17412  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Dependencies.Visitors.GraphVisitorBase::get_Services()
0x17417  call     valuetype Microsoft.VisualStudio.Setup.RequestedState Microsoft.VisualStudio.Setup.Dependencies.Extensions::GetRequestedState(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node, [opt] class [mscorlib]System.IServiceProvider services)
0x1741c  ldc.i4.3
0x1741d  bne.un   loc_174C1
0x17422  ldarg.1
0x17423  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x17428  callvirt instance class [System]System.Collections.Generic.ISet`1<class Microsoft.VisualStudio.Setup.IPackage> Microsoft.VisualStudio.Setup.IPackage::get_SelectedParents()
0x1742d  ldloc.s  5
0x1742f  callvirt instance bool class [System]System.Collections.Generic.ISet`1<class Microsoft.VisualStudio.Setup.IPackage>::Add(var<u1>)
0x17434  pop
0x17435  ldarg.1
0x17436  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x1743b  callvirt instance valuetype Microsoft.VisualStudio.Setup.RequestedState Microsoft.VisualStudio.Setup.IPackage::get_RequestedState()
0x17440  ldc.i4.4
0x17441  bne.un.s loc_17468
0x17443  ldarg.1
0x17444  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x17449  call     bool Microsoft.VisualStudio.Setup.Extensions::IsDowngradable(class Microsoft.VisualStudio.Setup.IPackage package)
0x1744e  brfalse.s loc_17468
0x17450  ldarg.1
0x17451  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x17456  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.IPackage::get_DowngradingPackage()
0x1745b  callvirt instance class [System]System.Collections.Generic.ISet`1<class Microsoft.VisualStudio.Setup.IPackage> Microsoft.VisualStudio.Setup.IPackage::get_SelectedParents()
0x17460  ldloc.s  5
0x17462  callvirt instance bool class [System]System.Collections.Generic.ISet`1<class Microsoft.VisualStudio.Setup.IPackage>::Add(var<u1>)
0x17467  pop
0x17468  ldloc.s  4
0x1746a  callvirt instance valuetype Microsoft.VisualStudio.Setup.DependencyType Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc::get_Type()
0x1746f  brfalse.s loc_17479
0x17471  ldloc.0
0x17472  call     bool Microsoft.VisualStudio.Setup.Extensions::IsSelectable(class Microsoft.VisualStudio.Setup.IPackage package)
0x17477  brtrue.s loc_174C1
0x17479  ldloc.s  5
0x1747b  callvirt instance class [System]System.Collections.Generic.ISet`1<class Microsoft.VisualStudio.Setup.IPackage> Microsoft.VisualStudio.Setup.IPackage::get_SelectedRequiredChildren()
0x17480  ldarg.1
0x17481  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x17486  callvirt instance bool class [System]System.Collections.Generic.ISet`1<class Microsoft.VisualStudio.Setup.IPackage>::Add(var<u1>)
0x1748b  pop
0x1748c  ldarg.1
0x1748d  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x17492  callvirt instance valuetype Microsoft.VisualStudio.Setup.RequestedState Microsoft.VisualStudio.Setup.IPackage::get_RequestedState()
0x17497  ldc.i4.4
0x17498  bne.un.s loc_174BF
0x1749a  ldarg.1
0x1749b  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x174a0  call     bool Microsoft.VisualStudio.Setup.Extensions::IsDowngradable(class Microsoft.VisualStudio.Setup.IPackage package)
0x174a5  brfalse.s loc_174BF
0x174a7  ldloc.s  5
0x174a9  callvirt instance class [System]System.Collections.Generic.ISet`1<class Microsoft.VisualStudio.Setup.IPackage> Microsoft.VisualStudio.Setup.IPackage::get_SelectedRequiredChildren()
0x174ae  ldarg.1
0x174af  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x174b4  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.IPackage::get_DowngradingPackage()
0x174b9  callvirt instance bool class [System]System.Collections.Generic.ISet`1<class Microsoft.VisualStudio.Setup.IPackage>::Add(var<u1>)
0x174be  pop
0x174bf  ldc.i4.1
0x174c0  stloc.1
0x174c1  ldloc.3
0x174c2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x174c7  brtrue   loc_173FA
0x174cc  leave.s  loc_174D8
0x174ce  ldloc.3
0x174cf  brfalse.s loc_174D7
0x174d1  ldloc.3
0x174d2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x174d7  endfinally
0x174d8  ldc.i4.0
0x174d9  stloc.2
0x174da  ldloc.1
0x174db  brfalse.s loc_17525
0x174dd  ldloc.0
0x174de  callvirt instance valuetype Microsoft.VisualStudio.Setup.RequestedState Microsoft.VisualStudio.Setup.IPackage::get_RequestedState()
0x174e3  ldc.i4.4
0x174e4  beq      loc_1758F
0x174e9  ldloc.0
0x174ea  callvirt instance valuetype Microsoft.VisualStudio.Setup.RequestedState Microsoft.VisualStudio.Setup.IPackage::get_RequestedState()
0x174ef  ldc.i4.3
0x174f0  beq.s    loc_174FB
0x174f2  ldc.i4.1
0x174f3  stloc.2
0x174f4  ldloc.0
0x174f5  ldc.i4.3
0x174f6  callvirt instance void Microsoft.VisualStudio.Setup.IPackage::set_RequestedState(valuetype Microsoft.VisualStudio.Setup.RequestedState value)
0x174fb  ldloc.0
0x174fc  isinst   Microsoft.VisualStudio.Setup.ISelectablePackage
0x17501  stloc.s  6
0x17503  ldloc.s  6
0x17505  brfalse  loc_1758F
0x1750a  ldloc.s  6
0x1750c  callvirt instance valuetype Microsoft.VisualStudio.Setup.SelectedState Microsoft.VisualStudio.Setup.ISelectablePackage::get_SelectedState()
0x17511  brtrue.s loc_1758F
0x17513  ldloc.s  6
0x17515  ldc.i4.2
0x17516  callvirt instance void Microsoft.VisualStudio.Setup.ISelectablePackage::set_SelectedState(valuetype Microsoft.VisualStudio.Setup.SelectedState value)
0x1751b  ldloc.s  6
0x1751d  ldc.i4.1
0x1751e  callvirt instance void Microsoft.VisualStudio.Setup.ISelectablePackage::set_UserSelectedState(valuetype Microsoft.VisualStudio.Setup.UserSelectedState value)
0x17523  br.s     loc_1758F
0x17525  ldloc.0
0x17526  call     bool Microsoft.VisualStudio.Setup.Extensions::IsSelectable(class Microsoft.VisualStudio.Setup.IPackage package)
0x1752b  brtrue.s loc_1758F
0x1752d  ldloc.0
0x1752e  callvirt instance valuetype Microsoft.VisualStudio.Setup.RequestedState Microsoft.VisualStudio.Setup.IPackage::get_RequestedState()
0x17533  ldc.i4.4
0x17534  beq.s    loc_1754A
0x17536  ldloc.0
0x17537  callvirt instance valuetype Microsoft.VisualStudio.Setup.RequestedState Microsoft.VisualStudio.Setup.IPackage::get_RequestedState()
0x1753c  ldc.i4.1
0x1753d  beq.s    loc_1754A
0x1753f  ldc.i4.1
0x17540  stloc.2
0x17541  ldloc.0
0x17542  ldc.i4.1
0x17543  callvirt instance void Microsoft.VisualStudio.Setup.IPackage::set_RequestedState(valuetype Microsoft.VisualStudio.Setup.RequestedState value)
0x17548  br.s     loc_1758F
0x1754a  ldloc.0
0x1754b  call     bool Microsoft.VisualStudio.Setup.Extensions::IsDowngradable(class Microsoft.VisualStudio.Setup.IPackage package)
0x17550  brtrue.s loc_1758F
0x17552  ldloc.0
0x17553  callvirt instance valuetype Microsoft.VisualStudio.Setup.RequestedState Microsoft.VisualStudio.Setup.IPackage::get_RequestedState()
0x17558  ldc.i4.1
0x17559  beq.s    loc_1758F
0x1755b  ldc.i4.1
0x1755c  stloc.2
0x1755d  ldloc.0
0x1755e  ldc.i4.1
0x1755f  callvirt instance void Microsoft.VisualStudio.Setup.IPackage::set_RequestedState(valuetype Microsoft.VisualStudio.Setup.RequestedState value)
0x17564  ldarg.0
0x17565  ldfld    class Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Dependencies.Visitors.SelectionVisitor::logger
0x1756a  dup
0x1756b  brtrue.s loc_17570
0x1756d  pop
0x1756e  br.s     loc_1758F
0x17570  ldstr    aPackage_1// "Package '"
0x17575  ldloc.0
0x17576  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x1757b  ldstr    aWillBeRemovedN// "' will be removed: no previous version "...
0x17580  call     string [mscorlib]System.String::Concat(string, string, string)
0x17585  call     T0x2B000016
0x1758a  callvirt instance void Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string format, object[] args)
0x1758f  ldarg.0
0x17590  ldarg.1
0x17591  ldloc.2
0x17592  call     instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.GraphVisitorBase::EnqueueChildren(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node, [opt] bool revisit)
0x17597  ret
```
