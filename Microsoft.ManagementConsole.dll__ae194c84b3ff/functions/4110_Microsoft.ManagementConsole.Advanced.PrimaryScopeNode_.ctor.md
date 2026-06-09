# Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::.ctor

- ea: `0x4110`
- end: `0x4144`
- name: `Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::.ctor`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x4b80`

## callees

- `0x4eb0`
- `0x5a60`
- `0x5c60`
- `0x5cb0`

## pseudocode

```c

```

## disassembly

```asm
0x4110  ldarg.0
0x4111  newobj   instance void Microsoft.ManagementConsole.ScopeNodeCollection::.ctor()
0x4116  stfld    class Microsoft.ManagementConsole.ScopeNodeCollection Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::_children
0x411b  ldarg.0
0x411c  newobj   instance void Microsoft.ManagementConsole.SharedData::.ctor()
0x4121  stfld    class Microsoft.ManagementConsole.SharedData Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::_sharedData
0x4126  ldarg.0
0x4127  call     instance void [mscorlib]System.Object::.ctor()
0x412c  ldarg.0
0x412d  ldfld    class Microsoft.ManagementConsole.ScopeNodeCollection Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::_children
0x4132  ldarg.0
0x4133  ldftn    instance void Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::OnChildrenChanged(object sender, class Microsoft.ManagementConsole.ScopeNodeCollectionEventArgs e)
0x4139  newobj   instance void ScopeNodeCollectionEventHandler::.ctor(object object, native int method)
0x413e  callvirt instance void Microsoft.ManagementConsole.ScopeNodeCollection::add_ItemsChanged(class ScopeNodeCollectionEventHandler value)
0x4143  ret
```
