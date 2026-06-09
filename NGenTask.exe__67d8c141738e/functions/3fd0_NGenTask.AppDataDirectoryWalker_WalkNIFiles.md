# NGenTask.AppDataDirectoryWalker::WalkNIFiles

- ea: `0x3fd0`
- end: `0x3fdf`
- name: `NGenTask.AppDataDirectoryWalker::WalkNIFiles`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400`

## callees

- `0x4940`

## pseudocode

```c

```

## disassembly

```asm
0x3fd0  ldc.i4.s 0xFE
0x3fd2  newobj   instance void <WalkNIFiles>d__8::.ctor(int32 <>1__state)
0x3fd7  dup
0x3fd8  ldarg.0
0x3fd9  stfld    class NGenTask.AppDataDirectoryWalker <WalkNIFiles>d__8::<>4__this
0x3fde  ret
```
