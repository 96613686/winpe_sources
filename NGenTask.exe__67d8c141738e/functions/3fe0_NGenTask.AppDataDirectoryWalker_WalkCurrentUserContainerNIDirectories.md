# NGenTask.AppDataDirectoryWalker::WalkCurrentUserContainerNIDirectories

- ea: `0x3fe0`
- end: `0x3fef`
- name: `NGenTask.AppDataDirectoryWalker::WalkCurrentUserContainerNIDirectories`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x4980`

## callees

- `0x4d80`

## pseudocode

```c

```

## disassembly

```asm
0x3fe0  ldc.i4.s 0xFE
0x3fe2  newobj   instance void <WalkCurrentUserContainerNIDirectories>d__9::.ctor(int32 <>1__state)
0x3fe7  dup
0x3fe8  ldarg.0
0x3fe9  stfld    class NGenTask.AppDataDirectoryWalker <WalkCurrentUserContainerNIDirectories>d__9::<>4__this
0x3fee  ret
```
