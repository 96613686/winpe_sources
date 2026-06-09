# NGenTask.LogWalker::WalkLogDirectories

- ea: `0x3f20`
- end: `0x3f2f`
- name: `NGenTask.LogWalker::WalkLogDirectories`
- size: `15`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x3830`
- `0x4270`

## callees

- `0x4100`

## pseudocode

```c

```

## disassembly

```asm
0x3f20  ldc.i4.s 0xFE
0x3f22  newobj   instance void <WalkLogDirectories>d__5::.ctor(int32 <>1__state)
0x3f27  dup
0x3f28  ldarg.0
0x3f29  stfld    class NGenTask.LogWalker <WalkLogDirectories>d__5::<>4__this
0x3f2e  ret
```
