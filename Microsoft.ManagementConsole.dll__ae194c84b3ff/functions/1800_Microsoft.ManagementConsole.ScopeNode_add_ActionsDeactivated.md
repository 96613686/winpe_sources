# Microsoft.ManagementConsole.ScopeNode::add_ActionsDeactivated

- ea: `0x1800`
- end: `0x181e`
- name: `Microsoft.ManagementConsole.ScopeNode::add_ActionsDeactivated`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1870`

## pseudocode

```c

```

## disassembly

```asm
0x1800  ldarg.0
0x1801  dup
0x1802  ldfld    class [mscorlib]System.EventHandler Microsoft.ManagementConsole.ScopeNode::_actionsDeactivated
0x1807  ldarg.1
0x1808  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x180d  castclass [mscorlib]System.EventHandler
0x1812  stfld    class [mscorlib]System.EventHandler Microsoft.ManagementConsole.ScopeNode::_actionsDeactivated
0x1817  ldarg.0
0x1818  call     instance void Microsoft.ManagementConsole.ScopeNode::NotifySendDeactivation()
0x181d  ret
```
