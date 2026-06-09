# Microsoft.ManagementConsole.ActionsPaneItem::remove_Changed

- ea: `0x2200`
- end: `0x2218`
- name: `Microsoft.ManagementConsole.ActionsPaneItem::remove_Changed`
- size: `24`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2580`
- `0x3070`

## pseudocode

```c

```

## disassembly

```asm
0x2200  ldarg.0
0x2201  ldarg.0
0x2202  ldfld    class [mscorlib]System.EventHandler Microsoft.ManagementConsole.ActionsPaneItem::Changed
0x2207  ldarg.1
0x2208  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x220d  castclass [mscorlib]System.EventHandler
0x2212  stfld    class [mscorlib]System.EventHandler Microsoft.ManagementConsole.ActionsPaneItem::Changed
0x2217  ret
```
