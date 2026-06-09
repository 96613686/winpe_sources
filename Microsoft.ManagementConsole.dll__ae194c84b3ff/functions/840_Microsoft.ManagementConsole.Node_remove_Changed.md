# Microsoft.ManagementConsole.Node::remove_Changed

- ea: `0x840`
- end: `0x858`
- name: `Microsoft.ManagementConsole.Node::remove_Changed`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1350`
- `0x5bf0`
- `0x6160`

## pseudocode

```c

```

## disassembly

```asm
0x840  ldarg.0
0x841  ldarg.0
0x842  ldfld    class NodeChangedEventHandler Microsoft.ManagementConsole.Node::Changed
0x847  ldarg.1
0x848  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x84d  castclass NodeChangedEventHandler
0x852  stfld    class NodeChangedEventHandler Microsoft.ManagementConsole.Node::Changed
0x857  ret
```
