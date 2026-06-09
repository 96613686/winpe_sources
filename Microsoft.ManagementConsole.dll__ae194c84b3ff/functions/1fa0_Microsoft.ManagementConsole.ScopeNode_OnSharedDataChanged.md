# Microsoft.ManagementConsole.ScopeNode::OnSharedDataChanged

- ea: `0x1fa0`
- end: `0x1fb6`
- name: `Microsoft.ManagementConsole.ScopeNode::OnSharedDataChanged`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1fa0`
- `0x2050`

## pseudocode

```c

```

## disassembly

```asm
0x1fa0  ldarg.0
0x1fa1  ldfld    class SharedDataChangedEventHandler Microsoft.ManagementConsole.ScopeNode::SharedDataChanged
0x1fa6  brfalse.s loc_1FB5
0x1fa8  ldarg.0
0x1fa9  ldfld    class SharedDataChangedEventHandler Microsoft.ManagementConsole.ScopeNode::SharedDataChanged
0x1fae  ldarg.0
0x1faf  ldarg.2
0x1fb0  callvirt instance void SharedDataChangedEventHandler::Invoke(object sender, class Microsoft.ManagementConsole.WritableSharedDataChangedEventArgs e)
0x1fb5  ret
```
