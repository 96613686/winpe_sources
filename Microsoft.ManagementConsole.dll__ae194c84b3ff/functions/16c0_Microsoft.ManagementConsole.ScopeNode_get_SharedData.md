# Microsoft.ManagementConsole.ScopeNode::get_SharedData

- ea: `0x16c0`
- end: `0x1708`
- name: `Microsoft.ManagementConsole.ScopeNode::get_SharedData`
- size: `72`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xf10`
- `0xf80`
- `0x1aa0`
- `0x1b00`

## callees

- `0x16c0`
- `0x54f0`
- `0x56f0`
- `0x5730`
- `0x58c0`
- `0x5910`

## pseudocode

```c

```

## disassembly

```asm
0x16c0  ldarg.0
0x16c1  ldfld    class Microsoft.ManagementConsole.WritableSharedData Microsoft.ManagementConsole.ScopeNode::_sharedData
0x16c6  brtrue.s loc_1701
0x16c8  ldarg.0
0x16c9  newobj   instance void Microsoft.ManagementConsole.WritableSharedData::.ctor()
0x16ce  stfld    class Microsoft.ManagementConsole.WritableSharedData Microsoft.ManagementConsole.ScopeNode::_sharedData
0x16d3  ldarg.0
0x16d4  ldfld    class Microsoft.ManagementConsole.WritableSharedData Microsoft.ManagementConsole.ScopeNode::_sharedData
0x16d9  ldarg.0
0x16da  ldftn    instance void Microsoft.ManagementConsole.ScopeNode::OnSharedDataChanged(object source, class Microsoft.ManagementConsole.WritableSharedDataChangedEventArgs e)
0x16e0  newobj   instance void SharedDataChangedEventHandler::.ctor(object object, native int method)
0x16e5  callvirt instance void Microsoft.ManagementConsole.WritableSharedData::add_Changed(class SharedDataChangedEventHandler value)
0x16ea  ldarg.0
0x16eb  ldfld    class Microsoft.ManagementConsole.WritableSharedData Microsoft.ManagementConsole.ScopeNode::_sharedData
0x16f0  ldarg.0
0x16f1  ldftn    instance void Microsoft.ManagementConsole.ScopeNode::OnSharedDataPropertyChangeRequested(object source, class Microsoft.ManagementConsole.WritableSharedDataChangeRequestEventArgs e)
0x16f7  newobj   instance void SharedDataChangeRequestEventHandler::.ctor(object object, native int method)
0x16fc  callvirt instance void Microsoft.ManagementConsole.WritableSharedData::add_PropertyChangeRequested(class SharedDataChangeRequestEventHandler value)
0x1701  ldarg.0
0x1702  ldfld    class Microsoft.ManagementConsole.WritableSharedData Microsoft.ManagementConsole.ScopeNode::_sharedData
0x1707  ret
```
