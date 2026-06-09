# NGenTask.AppDataDirectoryWalker::GetUserProfileDirectories

- ea: `0x3ff0`
- end: `0x3fff`
- name: `NGenTask.AppDataDirectoryWalker::GetUserProfileDirectories`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x5310`

## callees

- `0x4fa0`

## pseudocode

```c

```

## disassembly

```asm
0x3ff0  ldc.i4.s 0xFE
0x3ff2  newobj   instance void <GetUserProfileDirectories>d__10::.ctor(int32 <>1__state)
0x3ff7  dup
0x3ff8  ldarg.0
0x3ff9  stfld    class NGenTask.AppDataDirectoryWalker <GetUserProfileDirectories>d__10::<>4__this
0x3ffe  ret
```
