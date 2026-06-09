# NGenTask.LogWalker::WalkLogFiles

- ea: `0x3f50`
- end: `0x3f66`
- name: `NGenTask.LogWalker::WalkLogFiles`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x3f30`
- `0x3f40`

## callees

- `0x4230`

## pseudocode

```c

```

## disassembly

```asm
0x3f50  ldc.i4.s 0xFE
0x3f52  newobj   instance void <WalkLogFiles>d__8::.ctor(int32 <>1__state)
0x3f57  dup
0x3f58  ldarg.0
0x3f59  stfld    class NGenTask.LogWalker <WalkLogFiles>d__8::<>4__this
0x3f5e  dup
0x3f5f  ldarg.1
0x3f60  stfld    bool <WalkLogFiles>d__8::<>3__fOldLogs
0x3f65  ret
```
