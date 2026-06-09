# Microsoft.ManagementConsole.Internal.ConsoleDialogCommand::.ctor

- ea: `0x1d50`
- end: `0x1d5e`
- name: `Microsoft.ManagementConsole.Internal.ConsoleDialogCommand::.ctor`
- size: `14`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1d70`
- `0x24a0`
- `0x2530`

## callees

- `0x370`

## pseudocode

```c

```

## disassembly

```asm
0x1d50  ldarg.0
0x1d51  ldc.i4.m1
0x1d52  stfld    int32 Microsoft.ManagementConsole.Internal.ConsoleDialogCommand::_ownerId
0x1d57  ldarg.0
0x1d58  call     instance void Microsoft.ManagementConsole.Internal.Command::.ctor()
0x1d5d  ret
```
