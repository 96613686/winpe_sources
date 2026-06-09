# Microsoft.VisualStudio.Setup.CommandLine::set_Args

- ea: `0x1c20`
- end: `0x1c28`
- name: `Microsoft.VisualStudio.Setup.CommandLine::set_Args`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1df0`

## pseudocode

```c

```

## disassembly

```asm
0x1c20  ldarg.0
0x1c21  ldarg.1
0x1c22  stfld    class [mscorlib]System.Collections.Generic.IReadOnlyList`1<string> Microsoft.VisualStudio.Setup.CommandLine::<Args>k__BackingField
0x1c27  ret
```
