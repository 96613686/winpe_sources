# Microsoft.ManagementConsole.ScopeNode::remove_ActionsActivated

- ea: `0x17e0`
- end: `0x17fe`
- name: `Microsoft.ManagementConsole.ScopeNode::remove_ActionsActivated`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1840`

## pseudocode

```c

```

## disassembly

```asm
0x17e0  ldarg.0
0x17e1  dup
0x17e2  ldfld    class [mscorlib]System.EventHandler Microsoft.ManagementConsole.ScopeNode::_actionsActivated
0x17e7  ldarg.1
0x17e8  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x17ed  castclass [mscorlib]System.EventHandler
0x17f2  stfld    class [mscorlib]System.EventHandler Microsoft.ManagementConsole.ScopeNode::_actionsActivated
0x17f7  ldarg.0
0x17f8  call     instance void Microsoft.ManagementConsole.ScopeNode::NotifySendActivation()
0x17fd  ret
```
