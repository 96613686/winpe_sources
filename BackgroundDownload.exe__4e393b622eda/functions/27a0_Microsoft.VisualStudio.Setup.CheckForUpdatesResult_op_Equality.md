# Microsoft.VisualStudio.Setup.CheckForUpdatesResult::op_Equality

- ea: `0x27a0`
- end: `0x27b3`
- name: `Microsoft.VisualStudio.Setup.CheckForUpdatesResult::op_Equality`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2790`

## callees

- `0x27a0`
- `0x2840`

## pseudocode

```c

```

## disassembly

```asm
0x27a0  ldarg.0
0x27a1  ldarg.1
0x27a2  beq.s    loc_27B1
0x27a4  ldarg.0
0x27a5  brfalse.s loc_27AF
0x27a7  ldarg.0
0x27a8  ldarg.1
0x27a9  callvirt instance bool Microsoft.VisualStudio.Setup.CheckForUpdatesResult::Equals(class Microsoft.VisualStudio.Setup.CheckForUpdatesResult other)
0x27ae  ret
0x27af  ldc.i4.0
0x27b0  ret
0x27b1  ldc.i4.1
0x27b2  ret
```
