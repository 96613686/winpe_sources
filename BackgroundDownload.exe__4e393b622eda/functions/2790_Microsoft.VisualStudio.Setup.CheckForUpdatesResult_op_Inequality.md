# Microsoft.VisualStudio.Setup.CheckForUpdatesResult::op_Inequality

- ea: `0x2790`
- end: `0x279b`
- name: `Microsoft.VisualStudio.Setup.CheckForUpdatesResult::op_Inequality`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x27a0`

## pseudocode

```c

```

## disassembly

```asm
0x2790  ldarg.0
0x2791  ldarg.1
0x2792  call     bool Microsoft.VisualStudio.Setup.CheckForUpdatesResult::op_Equality(class Microsoft.VisualStudio.Setup.CheckForUpdatesResult left, class Microsoft.VisualStudio.Setup.CheckForUpdatesResult right)
0x2797  ldc.i4.0
0x2798  ceq
0x279a  ret
```
