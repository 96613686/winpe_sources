# Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::UpdateSelection

- ea: `0x14de0`
- end: `0x14e76`
- name: `Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::UpdateSelection`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x7f40`
- `0x7f50`
- `0x14840`
- `0x14850`
- `0x14de0`
- `0x14eb0`
- `0x16690`
- `0x16920`
- `0x173c0`

## pseudocode

```c

```

## disassembly

```asm
0x14de0  ldarg.0
0x14de1  call     instance class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::get_Root()
0x14de6  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x14deb  callvirt instance valuetype Microsoft.VisualStudio.Setup.RequestedState Microsoft.VisualStudio.Setup.IPackage::get_RequestedState()
0x14df0  ldc.i4.1
0x14df1  beq.s    loc_14E39
0x14df3  ldarg.0
0x14df4  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::services
0x14df9  newobj   instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.SelectionVisitor::.ctor([opt] class [mscorlib]System.IServiceProvider services)
0x14dfe  ldarg.0
0x14dff  call     instance class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::get_Root()
0x14e04  callvirt instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.GraphVisitorBase::Visit(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode root)
0x14e09  ldarg.0
0x14e0a  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::get_InstallOrder()
0x14e0f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::GetEnumerator()
0x14e14  stloc.0
0x14e15  br.s     loc_14E25
0x14e17  ldloc.0
0x14e18  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::get_Current()
0x14e1d  stloc.1
0x14e1e  ldarg.0
0x14e1f  ldloc.1
0x14e20  call     instance void Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::AdjustNodesSelectedState(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node)
0x14e25  ldloc.0
0x14e26  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x14e2b  brtrue.s loc_14E17
0x14e2d  leave.s  loc_14E75
0x14e2f  ldloc.0
0x14e30  brfalse.s loc_14E38
0x14e32  ldloc.0
0x14e33  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14e38  endfinally
0x14e39  ldarg.0
0x14e3a  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::get_InstallOrder()
0x14e3f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::GetEnumerator()
0x14e44  stloc.0
0x14e45  br.s     loc_14E61
0x14e47  ldloc.0
0x14e48  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::get_Current()
0x14e4d  stloc.2
0x14e4e  ldarg.0
0x14e4f  ldloc.2
0x14e50  call     instance void Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::AdjustNodesSelectedState(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node)
0x14e55  ldloc.2
0x14e56  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x14e5b  ldc.i4.1
0x14e5c  callvirt instance void Microsoft.VisualStudio.Setup.IPackage::set_RequestedState(valuetype Microsoft.VisualStudio.Setup.RequestedState value)
0x14e61  ldloc.0
0x14e62  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x14e67  brtrue.s loc_14E47
0x14e69  leave.s  loc_14E75
0x14e6b  ldloc.0
0x14e6c  brfalse.s loc_14E74
0x14e6e  ldloc.0
0x14e6f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14e74  endfinally
0x14e75  ret
```
