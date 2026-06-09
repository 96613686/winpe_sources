# Microsoft.ManagementConsole.Internal.FindPropertySheetForViewCommand::.ctor

- ea: `0x2340`
- end: `0x234e`
- name: `Microsoft.ManagementConsole.Internal.FindPropertySheetForViewCommand::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2280`

## pseudocode

```c

```

## disassembly

```asm
0x2340  ldarg.0
0x2341  ldc.i4.m1
0x2342  stfld    int32 Microsoft.ManagementConsole.Internal.FindPropertySheetForViewCommand::_selectionId
0x2347  ldarg.0
0x2348  call     instance void Microsoft.ManagementConsole.Internal.FindPropertySheetCommand::.ctor()
0x234d  ret
```
