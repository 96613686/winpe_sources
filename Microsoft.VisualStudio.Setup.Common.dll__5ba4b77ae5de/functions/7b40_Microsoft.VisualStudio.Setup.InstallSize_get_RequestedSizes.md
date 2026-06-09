# Microsoft.VisualStudio.Setup.InstallSize::get_RequestedSizes

- ea: `0x7b40`
- end: `0x7b47`
- name: `Microsoft.VisualStudio.Setup.InstallSize::get_RequestedSizes`
- size: `7`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7b50`
- `0x7b80`
- `0x7bb0`
- `0x7be0`
- `0x7cc0`
- `0x14920`

## pseudocode

```c

```

## disassembly

```asm
0x7b40  ldarg.0
0x7b41  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64> Microsoft.VisualStudio.Setup.InstallSize::<RequestedSizes>k__BackingField
0x7b46  ret
```
