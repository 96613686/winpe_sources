# Microsoft.ManagementConsole.SharedDataItem::remove_Changed

- ea: `0x53b0`
- end: `0x53c8`
- name: `Microsoft.ManagementConsole.SharedDataItem::remove_Changed`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x50c0`

## pseudocode

```c

```

## disassembly

```asm
0x53b0  ldarg.0
0x53b1  ldarg.0
0x53b2  ldfld    class SharedDataChangedEventHandler Microsoft.ManagementConsole.SharedDataItem::Changed
0x53b7  ldarg.1
0x53b8  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x53bd  castclass SharedDataChangedEventHandler
0x53c2  stfld    class SharedDataChangedEventHandler Microsoft.ManagementConsole.SharedDataItem::Changed
0x53c7  ret
```
