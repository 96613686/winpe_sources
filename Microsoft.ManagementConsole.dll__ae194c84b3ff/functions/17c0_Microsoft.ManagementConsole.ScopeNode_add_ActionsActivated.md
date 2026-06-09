# Microsoft.ManagementConsole.ScopeNode::add_ActionsActivated

- ea: `0x17c0`
- end: `0x17de`
- name: `Microsoft.ManagementConsole.ScopeNode::add_ActionsActivated`
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
0x17c0  ldarg.0
0x17c1  dup
0x17c2  ldfld    class [mscorlib]System.EventHandler Microsoft.ManagementConsole.ScopeNode::_actionsActivated
0x17c7  ldarg.1
0x17c8  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x17cd  castclass [mscorlib]System.EventHandler
0x17d2  stfld    class [mscorlib]System.EventHandler Microsoft.ManagementConsole.ScopeNode::_actionsActivated
0x17d7  ldarg.0
0x17d8  call     instance void Microsoft.ManagementConsole.ScopeNode::NotifySendActivation()
0x17dd  ret
```
