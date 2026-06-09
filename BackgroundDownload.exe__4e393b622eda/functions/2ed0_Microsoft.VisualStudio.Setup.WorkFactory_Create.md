# Microsoft.VisualStudio.Setup.WorkFactory::Create

- ea: `0x2ed0`
- end: `0x2ee3`
- name: `Microsoft.VisualStudio.Setup.WorkFactory::Create`
- size: `19`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2480`
- `0x5530`

## callees

- `0x2eb0`
- `0x2ed0`
- `0x3560`

## pseudocode

```c

```

## disassembly

```asm
0x2ed0  ldarg.0
0x2ed1  brtrue.s loc_2EDB
0x2ed3  newobj   instance void Microsoft.VisualStudio.Setup.WorkPrimaryProcess::.ctor()
0x2ed8  stloc.0
0x2ed9  ldloc.0
0x2eda  ret
0x2edb  newobj   instance void Microsoft.VisualStudio.Setup.WorkChildProcess::.ctor()
0x2ee0  stloc.0
0x2ee1  ldloc.0
0x2ee2  ret
```
