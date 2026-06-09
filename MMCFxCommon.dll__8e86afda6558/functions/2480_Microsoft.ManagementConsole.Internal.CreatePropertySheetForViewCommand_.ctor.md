# Microsoft.ManagementConsole.Internal.CreatePropertySheetForViewCommand::.ctor

- ea: `0x2480`
- end: `0x248e`
- name: `Microsoft.ManagementConsole.Internal.CreatePropertySheetForViewCommand::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x23c0`

## pseudocode

```c

```

## disassembly

```asm
0x2480  ldarg.0
0x2481  ldc.i4.m1
0x2482  stfld    int32 Microsoft.ManagementConsole.Internal.CreatePropertySheetForViewCommand::_viewId
0x2487  ldarg.0
0x2488  call     instance void Microsoft.ManagementConsole.Internal.CreatePropertySheetCommand::.ctor()
0x248d  ret
```
