# NGenTask.AppDataDirectoryWalker::GetUserProfileAppDataDirectories

- ea: `0x4000`
- end: `0x400f`
- name: `NGenTask.AppDataDirectoryWalker::GetUserProfileAppDataDirectories`
- size: `15`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x45f0`
- `0x4dc0`

## callees

- `0x52c0`

## pseudocode

```c

```

## disassembly

```asm
0x4000  ldc.i4.s 0xFE
0x4002  newobj   instance void <GetUserProfileAppDataDirectories>d__11::.ctor(int32 <>1__state)
0x4007  dup
0x4008  ldarg.0
0x4009  stfld    class NGenTask.AppDataDirectoryWalker <GetUserProfileAppDataDirectories>d__11::<>4__this
0x400e  ret
```
