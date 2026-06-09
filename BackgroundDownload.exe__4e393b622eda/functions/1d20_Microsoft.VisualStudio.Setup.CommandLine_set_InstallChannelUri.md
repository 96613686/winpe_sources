# Microsoft.VisualStudio.Setup.CommandLine::set_InstallChannelUri

- ea: `0x1d20`
- end: `0x1d28`
- name: `Microsoft.VisualStudio.Setup.CommandLine::set_InstallChannelUri`
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
0x1d20  ldarg.0
0x1d21  ldarg.1
0x1d22  stfld    class [System]System.Uri Microsoft.VisualStudio.Setup.CommandLine::<InstallChannelUri>k__BackingField
0x1d27  ret
```
