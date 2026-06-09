# Microsoft.ManagementConsole.ScopeNode::remove_ActionsDeactivated

- ea: `0x1820`
- end: `0x183e`
- name: `Microsoft.ManagementConsole.ScopeNode::remove_ActionsDeactivated`
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
0x1820  ldarg.0
0x1821  dup
0x1822  ldfld    class [mscorlib]System.EventHandler Microsoft.ManagementConsole.ScopeNode::_actionsDeactivated
0x1827  ldarg.1
0x1828  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x182d  castclass [mscorlib]System.EventHandler
0x1832  stfld    class [mscorlib]System.EventHandler Microsoft.ManagementConsole.ScopeNode::_actionsDeactivated
0x1837  ldarg.0
0x1838  call     instance void Microsoft.ManagementConsole.ScopeNode::NotifySendDeactivation()
0x183d  ret
```
