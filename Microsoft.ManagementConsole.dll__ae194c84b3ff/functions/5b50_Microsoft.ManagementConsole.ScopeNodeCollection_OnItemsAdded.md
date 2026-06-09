# Microsoft.ManagementConsole.ScopeNodeCollection::OnItemsAdded

- ea: `0x5b50`
- end: `0x5ba4`
- name: `Microsoft.ManagementConsole.ScopeNodeCollection::OnItemsAdded`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x820`
- `0x870`
- `0x1960`
- `0x5a00`
- `0x5b50`
- `0x5c40`

## pseudocode

```c

```

## disassembly

```asm
0x5b50  ldarg.2
0x5b51  stloc.2
0x5b52  ldc.i4.0
0x5b53  stloc.3
0x5b54  br.s     loc_5B81
0x5b56  ldloc.2
0x5b57  ldloc.3
0x5b58  ldelem.ref
0x5b59  castclass Microsoft.ManagementConsole.ScopeNode
0x5b5e  stloc.0
0x5b5f  ldloc.0
0x5b60  ldarg.0
0x5b61  ldftn    instance void Microsoft.ManagementConsole.ScopeNodeCollection::ItemChanged(object sender, class Microsoft.ManagementConsole.NodeChangedEventArgs e)
0x5b67  newobj   instance void NodeChangedEventHandler::.ctor(object object, native int method)
0x5b6c  callvirt instance void Microsoft.ManagementConsole.Node::add_Changed(class NodeChangedEventHandler value)
0x5b71  ldloc.0
0x5b72  ldarg.0
0x5b73  call     instance class Microsoft.ManagementConsole.ScopeNode Microsoft.ManagementConsole.ScopeNodeCollection::get_ContainerNode()
0x5b78  callvirt instance void Microsoft.ManagementConsole.ScopeNode::SetParent(class Microsoft.ManagementConsole.ScopeNode parent)
0x5b7d  ldloc.3
0x5b7e  ldc.i4.1
0x5b7f  add
0x5b80  stloc.3
0x5b81  ldloc.3
0x5b82  ldloc.2
0x5b83  ldlen
0x5b84  conv.i4
0x5b85  blt.s    loc_5B56
0x5b87  ldarg.2
0x5b88  ldlen
0x5b89  conv.i4
0x5b8a  newarr   Microsoft.ManagementConsole.ScopeNode
0x5b8f  stloc.1
0x5b90  ldarg.2
0x5b91  ldloc.1
0x5b92  ldarg.2
0x5b93  ldlen
0x5b94  conv.i4
0x5b95  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, class [mscorlib]System.Array, int32)
0x5b9a  ldarg.0
0x5b9b  ldarg.1
0x5b9c  ldloc.1
0x5b9d  ldc.i4.0
0x5b9e  call     instance void Microsoft.ManagementConsole.ScopeNodeCollection::Notify(int32 index, class Microsoft.ManagementConsole.ScopeNode[] items, valuetype Microsoft.ManagementConsole.ScopeNodeCollectionChangeType action)
0x5ba3  ret
```
