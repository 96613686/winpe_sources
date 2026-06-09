# Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::VisitHelper

- ea: `0x16d00`
- end: `0x16e38`
- name: `Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::VisitHelper`
- size: `312`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x16ba0`
- `0x16d00`

## callees

- `0x58c0`
- `0x7f30`
- `0x7f40`
- `0x7f70`
- `0x11dc0`
- `0x16690`
- `0x166c0`
- `0x16b40`
- `0x16b60`
- `0x16bf0`
- `0x16c00`
- `0x16d00`
- `0x16e40`
- `0x16f90`
- `0x18f40`
- `0x1d5e0`
- `0x1d620`

## pseudocode

```c

```

## disassembly

```asm
0x16d00  ldarg.0
0x16d01  ldarg.1
0x16d02  call     instance bool Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::ShouldVisitNode(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node)
0x16d07  brtrue.s loc_16D0A
0x16d09  ret
0x16d0a  ldarg.1
0x16d0b  ldarg.0
0x16d0c  ldarg.0
0x16d0d  ldfld    int32 Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::index
0x16d12  stloc.2
0x16d13  ldloc.2
0x16d14  ldc.i4.1
0x16d15  add
0x16d16  stfld    int32 Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::index
0x16d1b  ldloc.2
0x16d1c  newobj   instance void VisitationRecord::.ctor(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node, int32 index)
0x16d21  stloc.0
0x16d22  ldarg.0
0x16d23  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class VisitationRecord> Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::visitationLog
0x16d28  ldarg.1
0x16d29  ldloc.0
0x16d2a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class VisitationRecord>::Add(var<u1>, !!T0)
0x16d2f  ldarg.0
0x16d30  ldarg.1
0x16d31  call     instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::ValidateCandidates(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node)
0x16d36  ldarg.1
0x16d37  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc> Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Children()
0x16d3c  ldarg.0
0x16d3d  ldftn    instance bool Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::<VisitHelper>b__24_0(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc arc)
0x16d43  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc, bool>::.ctor(object, native int)
0x16d48  call     T0x2B000094
0x16d4d  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc, class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> <>c::<>9__24_1
0x16d52  dup
0x16d53  brtrue.s loc_16D6C
0x16d55  pop
0x16d56  ldsfld   class <>c <>c::<>9
0x16d5b  ldftn    instance class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c::<VisitHelper>b__24_1(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc arc)
0x16d61  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc, class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::.ctor(object, native int)
0x16d66  dup
0x16d67  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc, class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> <>c::<>9__24_1
0x16d6c  call     T0x2B000082
0x16d71  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::GetEnumerator()
0x16d76  stloc.3
0x16d77  br.s     loc_16D89
0x16d79  ldloc.3
0x16d7a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::get_Current()
0x16d7f  stloc.s  4
0x16d81  ldarg.0
0x16d82  ldloc.s  4
0x16d84  call     instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::VisitHelper(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node)
0x16d89  ldloc.3
0x16d8a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x16d8f  brtrue.s loc_16D79
0x16d91  leave.s  loc_16D9D
0x16d93  ldloc.3
0x16d94  brfalse.s loc_16D9C
0x16d96  ldloc.3
0x16d97  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16d9c  endfinally
0x16d9d  ldarg.1
0x16d9e  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x16da3  stloc.1
0x16da4  ldloc.1
0x16da5  brfalse.s loc_16E1D
0x16da7  ldarg.0
0x16da8  call     instance class Microsoft.VisualStudio.Setup.Cache.ICacheManager Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::get_Cache()
0x16dad  brfalse.s loc_16DC7
0x16daf  ldloc.1
0x16db0  ldarg.0
0x16db1  call     instance class Microsoft.VisualStudio.Setup.Cache.ICacheManager Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::get_Cache()
0x16db6  ldloc.1
0x16db7  call     bool Microsoft.VisualStudio.Setup.Cache.CommonExtensions::IsInstalled(class Microsoft.VisualStudio.Setup.Cache.ICacheManager manager, class Microsoft.VisualStudio.Setup.IPackageIdentity identity)
0x16dbc  brtrue.s loc_16DC1
0x16dbe  ldc.i4.1
0x16dbf  br.s     loc_16DC2
0x16dc1  ldc.i4.3
0x16dc2  callvirt instance void Microsoft.VisualStudio.Setup.IPackage::set_CurrentState(valuetype Microsoft.VisualStudio.Setup.CurrentState value)
0x16dc7  ldarg.0
0x16dc8  ldfld    class Microsoft.VisualStudio.Setup.Services.IPackageDetectionService Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::packageDetection
0x16dcd  brfalse.s loc_16DE7
0x16dcf  ldloc.1
0x16dd0  ldarg.0
0x16dd1  ldfld    class Microsoft.VisualStudio.Setup.Services.IPackageDetectionService Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::packageDetection
0x16dd6  ldloc.1
0x16dd7  callvirt instance bool Microsoft.VisualStudio.Setup.Services.IPackageDetectionService::IsInstalled(class Microsoft.VisualStudio.Setup.IPackage package)
0x16ddc  brtrue.s loc_16DE1
0x16dde  ldc.i4.1
0x16ddf  br.s     loc_16DE2
0x16de1  ldc.i4.2
0x16de2  callvirt instance void Microsoft.VisualStudio.Setup.IPackage::set_DetectedState(valuetype Microsoft.VisualStudio.Setup.DetectedState value)
0x16de7  ldloc.1
0x16de8  callvirt instance valuetype Microsoft.VisualStudio.Setup.RequestedState Microsoft.VisualStudio.Setup.IPackage::get_RequestedState()
0x16ded  ldc.i4.4
0x16dee  bne.un.s loc_16DF7
0x16df0  ldarg.0
0x16df1  ldloc.1
0x16df2  call     instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::Downgrade(class Microsoft.VisualStudio.Setup.IPackage package)
0x16df7  ldloc.1
0x16df8  isinst   Microsoft.VisualStudio.Setup.IRootPackage
0x16dfd  stloc.s  5
0x16dff  ldloc.s  5
0x16e01  brfalse.s loc_16E1D
0x16e03  ldloc.s  5
0x16e05  callvirt instance valuetype Microsoft.VisualStudio.Setup.RequestedState Microsoft.VisualStudio.Setup.IPackage::get_RequestedState()
0x16e0a  ldc.i4.1
0x16e0b  bne.un.s loc_16E1D
0x16e0d  ldloc.s  5
0x16e0f  call     bool Microsoft.VisualStudio.Setup.Extensions::IsExperimentRoot(class Microsoft.VisualStudio.Setup.IPackage package)
0x16e14  brfalse.s loc_16E1D
0x16e16  ldarg.0
0x16e17  ldloc.1
0x16e18  call     instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::Downgrade(class Microsoft.VisualStudio.Setup.IPackage package)
0x16e1d  ldloc.0
0x16e1e  ldc.i4.1
0x16e1f  callvirt instance void VisitationRecord::set_State(valuetype VisitationState value)
0x16e24  ldarg.0
0x16e25  call     instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::get_VisitedOrder()
0x16e2a  ldarg.1
0x16e2b  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::Add(var<u1>)
0x16e30  ldarg.0
0x16e31  ldarg.1
0x16e32  callvirt instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::PostNodeVisit(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node)
0x16e37  ret
```
