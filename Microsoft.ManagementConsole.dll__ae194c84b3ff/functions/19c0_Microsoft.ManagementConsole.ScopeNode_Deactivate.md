# Microsoft.ManagementConsole.ScopeNode::Deactivate

- ea: `0x19c0`
- end: `0x19da`
- name: `Microsoft.ManagementConsole.ScopeNode::Deactivate`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xde0`

## callees

- `0x19c0`

## pseudocode

```c

```

## disassembly

```asm
0x19c0  ldarg.0
0x19c1  ldfld    class [mscorlib]System.EventHandler Microsoft.ManagementConsole.ScopeNode::_actionsDeactivated
0x19c6  brfalse.s loc_19D9
0x19c8  ldarg.0
0x19c9  ldfld    class [mscorlib]System.EventHandler Microsoft.ManagementConsole.ScopeNode::_actionsDeactivated
0x19ce  ldarg.0
0x19cf  ldsfld   class [mscorlib]System.EventArgs Microsoft.ManagementConsole.ScopeNode::_eventArgs
0x19d4  callvirt instance void [mscorlib]System.EventHandler::Invoke(object, class [mscorlib]System.EventArgs)
0x19d9  ret
```
