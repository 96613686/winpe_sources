# Microsoft.ManagementConsole.ScopeNodeCollection::OnItemsRemoved

- ea: `0x5bf0`
- end: `0x5c3f`
- name: `Microsoft.ManagementConsole.ScopeNodeCollection::OnItemsRemoved`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x840`
- `0x870`
- `0x1960`
- `0x5bf0`
- `0x5c40`

## pseudocode

```c

```

## disassembly

```asm
0x5bf0  ldarg.2
0x5bf1  stloc.2
0x5bf2  ldc.i4.0
0x5bf3  stloc.3
0x5bf4  br.s     loc_5C1C
0x5bf6  ldloc.2
0x5bf7  ldloc.3
0x5bf8  ldelem.ref
0x5bf9  castclass Microsoft.ManagementConsole.ScopeNode
0x5bfe  stloc.0
0x5bff  ldloc.0
0x5c00  ldarg.0
0x5c01  ldftn    instance void Microsoft.ManagementConsole.ScopeNodeCollection::ItemChanged(object sender, class Microsoft.ManagementConsole.NodeChangedEventArgs e)
0x5c07  newobj   instance void NodeChangedEventHandler::.ctor(object object, native int method)
0x5c0c  callvirt instance void Microsoft.ManagementConsole.Node::remove_Changed(class NodeChangedEventHandler value)
0x5c11  ldloc.0
0x5c12  ldnull
0x5c13  callvirt instance void Microsoft.ManagementConsole.ScopeNode::SetParent(class Microsoft.ManagementConsole.ScopeNode parent)
0x5c18  ldloc.3
0x5c19  ldc.i4.1
0x5c1a  add
0x5c1b  stloc.3
0x5c1c  ldloc.3
0x5c1d  ldloc.2
0x5c1e  ldlen
0x5c1f  conv.i4
0x5c20  blt.s    loc_5BF6
0x5c22  ldarg.2
0x5c23  ldlen
0x5c24  conv.i4
0x5c25  newarr   Microsoft.ManagementConsole.ScopeNode
0x5c2a  stloc.1
0x5c2b  ldarg.2
0x5c2c  ldloc.1
0x5c2d  ldarg.2
0x5c2e  ldlen
0x5c2f  conv.i4
0x5c30  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, class [mscorlib]System.Array, int32)
0x5c35  ldarg.0
0x5c36  ldarg.1
0x5c37  ldloc.1
0x5c38  ldc.i4.1
0x5c39  call     instance void Microsoft.ManagementConsole.ScopeNodeCollection::Notify(int32 index, class Microsoft.ManagementConsole.ScopeNode[] items, valuetype Microsoft.ManagementConsole.ScopeNodeCollectionChangeType action)
0x5c3e  ret
```
