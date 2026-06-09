# Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::UpdatePartialSelection

- ea: `0x14ef0`
- end: `0x14f45`
- name: `Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::UpdatePartialSelection`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14f50`

## callees

- `0x7f40`
- `0x14840`
- `0x14ef0`
- `0x164a0`
- `0x16690`
- `0x166c0`
- `0x16920`
- `0x173c0`

## pseudocode

```c

```

## disassembly

```asm
0x14ef0  ldarg.0
0x14ef1  call     instance class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::get_Root()
0x14ef6  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x14efb  callvirt instance valuetype Microsoft.VisualStudio.Setup.RequestedState Microsoft.VisualStudio.Setup.IPackage::get_RequestedState()
0x14f00  ldc.i4.1
0x14f01  beq.s    loc_14F44
0x14f03  ldarg.0
0x14f04  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::services
0x14f09  newobj   instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.SelectionVisitor::.ctor([opt] class [mscorlib]System.IServiceProvider services)
0x14f0e  stloc.0
0x14f0f  ldarg.1
0x14f10  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc> Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Children()
0x14f15  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc>::GetEnumerator()
0x14f1a  stloc.1
0x14f1b  br.s     loc_14F30
0x14f1d  ldloc.1
0x14f1e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc>::get_Current()
0x14f23  stloc.2
0x14f24  ldloc.0
0x14f25  ldloc.2
0x14f26  callvirt instance class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc::get_Node()
0x14f2b  callvirt instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.GraphVisitorBase::Visit(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode root)
0x14f30  ldloc.1
0x14f31  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x14f36  brtrue.s loc_14F1D
0x14f38  leave.s  loc_14F44
0x14f3a  ldloc.1
0x14f3b  brfalse.s loc_14F43
0x14f3d  ldloc.1
0x14f3e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14f43  endfinally
0x14f44  ret
```
