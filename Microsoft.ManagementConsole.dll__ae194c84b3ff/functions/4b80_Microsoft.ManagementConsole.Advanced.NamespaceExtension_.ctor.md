# Microsoft.ManagementConsole.Advanced.NamespaceExtension::.ctor

- ea: `0x4b80`
- end: `0x4bae`
- name: `Microsoft.ManagementConsole.Advanced.NamespaceExtension::.ctor`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x40e0`
- `0x4110`
- `0x4800`
- `0x5150`
- `0x51b0`

## pseudocode

```c

```

## disassembly

```asm
0x4b80  ldarg.0
0x4b81  newobj   instance void Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::.ctor()
0x4b86  stfld    class Microsoft.ManagementConsole.Advanced.PrimaryScopeNode Microsoft.ManagementConsole.Advanced.NamespaceExtension::_primaryNode
0x4b8b  ldarg.0
0x4b8c  call     instance void Microsoft.ManagementConsole.NamespaceSnapInBase::.ctor()
0x4b91  ldarg.0
0x4b92  ldfld    class Microsoft.ManagementConsole.Advanced.PrimaryScopeNode Microsoft.ManagementConsole.Advanced.NamespaceExtension::_primaryNode
0x4b97  callvirt instance class Microsoft.ManagementConsole.SharedData Microsoft.ManagementConsole.Advanced.PrimaryScopeNode::get_SharedData()
0x4b9c  ldarg.0
0x4b9d  ldftn    instance void Microsoft.ManagementConsole.Advanced.NamespaceExtension::SharedDataChanged(object sender, class Microsoft.ManagementConsole.SharedDataChangedEventArgs e)
0x4ba3  newobj   instance void SharedDataChangedEventHandler::.ctor(object object, native int method)
0x4ba8  callvirt instance void Microsoft.ManagementConsole.SharedData::add_Changed(class SharedDataChangedEventHandler value)
0x4bad  ret
```
