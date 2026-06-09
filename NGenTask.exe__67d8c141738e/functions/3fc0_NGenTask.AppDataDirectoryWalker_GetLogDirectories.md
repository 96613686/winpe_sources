# NGenTask.AppDataDirectoryWalker::GetLogDirectories

- ea: `0x3fc0`
- end: `0x3fcf`
- name: `NGenTask.AppDataDirectoryWalker::GetLogDirectories`
- size: `15`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1120`
- `0x11c0`

## callees

- `0x45b0`

## pseudocode

```c

```

## disassembly

```asm
0x3fc0  ldc.i4.s 0xFE
0x3fc2  newobj   instance void <GetLogDirectories>d__7::.ctor(int32 <>1__state)
0x3fc7  dup
0x3fc8  ldarg.0
0x3fc9  stfld    class NGenTask.AppDataDirectoryWalker <GetLogDirectories>d__7::<>4__this
0x3fce  ret
```
