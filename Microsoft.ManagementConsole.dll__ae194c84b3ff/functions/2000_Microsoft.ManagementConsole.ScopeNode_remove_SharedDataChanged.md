# Microsoft.ManagementConsole.ScopeNode::remove_SharedDataChanged

- ea: `0x2000`
- end: `0x2018`
- name: `Microsoft.ManagementConsole.ScopeNode::remove_SharedDataChanged`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1350`

## pseudocode

```c

```

## disassembly

```asm
0x2000  ldarg.0
0x2001  ldarg.0
0x2002  ldfld    class SharedDataChangedEventHandler Microsoft.ManagementConsole.ScopeNode::SharedDataChanged
0x2007  ldarg.1
0x2008  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x200d  castclass SharedDataChangedEventHandler
0x2012  stfld    class SharedDataChangedEventHandler Microsoft.ManagementConsole.ScopeNode::SharedDataChanged
0x2017  ret
```
