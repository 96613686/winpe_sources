# Microsoft.ManagementConsole.ScopeNode::add_SharedDataChanged

- ea: `0x1fe0`
- end: `0x1ff8`
- name: `Microsoft.ManagementConsole.ScopeNode::add_SharedDataChanged`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1230`

## pseudocode

```c

```

## disassembly

```asm
0x1fe0  ldarg.0
0x1fe1  ldarg.0
0x1fe2  ldfld    class SharedDataChangedEventHandler Microsoft.ManagementConsole.ScopeNode::SharedDataChanged
0x1fe7  ldarg.1
0x1fe8  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x1fed  castclass SharedDataChangedEventHandler
0x1ff2  stfld    class SharedDataChangedEventHandler Microsoft.ManagementConsole.ScopeNode::SharedDataChanged
0x1ff7  ret
```
