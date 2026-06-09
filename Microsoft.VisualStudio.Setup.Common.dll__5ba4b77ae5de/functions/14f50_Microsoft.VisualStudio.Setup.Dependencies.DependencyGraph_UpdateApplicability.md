# Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::UpdateApplicability

- ea: `0x14f50`
- end: `0x14fa3`
- name: `Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::UpdateApplicability`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x7f50`
- `0x14840`
- `0x14ef0`
- `0x14f50`
- `0x16690`
- `0x167d0`
- `0x16800`
- `0x16ba0`

## pseudocode

```c

```

## disassembly

```asm
0x14f50  ldarg.0
0x14f51  call     instance class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::get_Root()
0x14f56  ldarg.0
0x14f57  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::services
0x14f5c  newobj   instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.ApplicabilityVisitor::.ctor(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode rootNode, [opt] class [mscorlib]System.IServiceProvider services)
0x14f61  dup
0x14f62  callvirt instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::Visit()
0x14f67  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> Microsoft.VisualStudio.Setup.Dependencies.Visitors.ApplicabilityVisitor::get_PackagesToUpdateSelection()
0x14f6c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::GetEnumerator()
0x14f71  stloc.0
0x14f72  br.s     loc_14F8E
0x14f74  ldloc.0
0x14f75  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::get_Current()
0x14f7a  stloc.1
0x14f7b  ldloc.1
0x14f7c  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x14f81  ldc.i4.1
0x14f82  callvirt instance void Microsoft.VisualStudio.Setup.IPackage::set_RequestedState(valuetype Microsoft.VisualStudio.Setup.RequestedState value)
0x14f87  ldarg.0
0x14f88  ldloc.1
0x14f89  call     instance void Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::UpdatePartialSelection(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode subRoot)
0x14f8e  ldloc.0
0x14f8f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x14f94  brtrue.s loc_14F74
0x14f96  leave.s  loc_14FA2
0x14f98  ldloc.0
0x14f99  brfalse.s loc_14FA1
0x14f9b  ldloc.0
0x14f9c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14fa1  endfinally
0x14fa2  ret
```
