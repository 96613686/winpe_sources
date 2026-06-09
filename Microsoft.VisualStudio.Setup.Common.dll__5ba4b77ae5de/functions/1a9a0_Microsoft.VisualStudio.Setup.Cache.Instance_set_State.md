# Microsoft.VisualStudio.Setup.Cache.Instance::set_State

- ea: `0x1a9a0`
- end: `0x1a9cc`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::set_State`
- size: `44`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1a110`
- `0x1aa70`
- `0x1b2c0`
- `0x1b360`
- `0x1b3a0`
- `0x1b460`
- `0x1b4b0`

## callees

- `0x1a9a0`

## pseudocode

```c

```

## disassembly

```asm
0x1a9a0  ldarg.0
0x1a9a1  ldarg.1
0x1a9a2  stfld    valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState Microsoft.VisualStudio.Setup.Cache.Instance::state
0x1a9a7  ldarg.0
0x1a9a8  ldfld    valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState Microsoft.VisualStudio.Setup.Cache.Instance::state
0x1a9ad  ldc.i4.s 0xF
0x1a9af  and
0x1a9b0  ldc.i4.s 0xF
0x1a9b2  bne.un.s loc_1A9BC
0x1a9b4  ldarg.0
0x1a9b5  ldc.i4.m1
0x1a9b6  stfld    valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState Microsoft.VisualStudio.Setup.Cache.Instance::state
0x1a9bb  ret
0x1a9bc  ldarg.0
0x1a9bd  ldarg.0
0x1a9be  ldfld    valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState Microsoft.VisualStudio.Setup.Cache.Instance::state
0x1a9c3  ldc.i4.s 0xF
0x1a9c5  and
0x1a9c6  stfld    valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState Microsoft.VisualStudio.Setup.Cache.Instance::state
0x1a9cb  ret
```
