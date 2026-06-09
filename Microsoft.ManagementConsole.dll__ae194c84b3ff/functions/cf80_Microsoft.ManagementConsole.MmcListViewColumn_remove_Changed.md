# Microsoft.ManagementConsole.MmcListViewColumn::remove_Changed

- ea: `0xcf80`
- end: `0xcf98`
- name: `Microsoft.ManagementConsole.MmcListViewColumn::remove_Changed`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x96c0`

## pseudocode

```c

```

## disassembly

```asm
0xcf80  ldarg.0
0xcf81  ldarg.0
0xcf82  ldfld    class ColumnChangedEventHandler Microsoft.ManagementConsole.MmcListViewColumn::Changed
0xcf87  ldarg.1
0xcf88  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0xcf8d  castclass ColumnChangedEventHandler
0xcf92  stfld    class ColumnChangedEventHandler Microsoft.ManagementConsole.MmcListViewColumn::Changed
0xcf97  ret
```
