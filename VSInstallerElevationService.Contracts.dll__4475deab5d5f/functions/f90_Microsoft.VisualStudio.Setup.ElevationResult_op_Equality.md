# Microsoft.VisualStudio.Setup.ElevationResult::op_Equality

- ea: `0xf90`
- end: `0xfa3`
- name: `Microsoft.VisualStudio.Setup.ElevationResult::op_Equality`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xf80`

## callees

- `0xf90`
- `0x1000`

## pseudocode

```c

```

## disassembly

```asm
0xf90  ldarg.0
0xf91  ldarg.1
0xf92  beq.s    loc_FA1
0xf94  ldarg.0
0xf95  brfalse.s loc_F9F
0xf97  ldarg.0
0xf98  ldarg.1
0xf99  callvirt instance bool Microsoft.VisualStudio.Setup.ElevationResult::Equals(class Microsoft.VisualStudio.Setup.ElevationResult other)
0xf9e  ret
0xf9f  ldc.i4.0
0xfa0  ret
0xfa1  ldc.i4.1
0xfa2  ret
```
