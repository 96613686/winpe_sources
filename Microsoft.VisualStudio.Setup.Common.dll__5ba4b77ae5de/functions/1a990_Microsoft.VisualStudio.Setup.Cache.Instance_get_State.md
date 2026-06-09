# Microsoft.VisualStudio.Setup.Cache.Instance::get_State

- ea: `0x1a990`
- end: `0x1a997`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::get_State`
- size: `7`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1aa70`
- `0x1b2c0`
- `0x1b360`
- `0x1b3a0`
- `0x1b460`
- `0x1b4b0`

## pseudocode

```c

```

## disassembly

```asm
0x1a990  ldarg.0
0x1a991  ldfld    valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState Microsoft.VisualStudio.Setup.Cache.Instance::state
0x1a996  ret
```
