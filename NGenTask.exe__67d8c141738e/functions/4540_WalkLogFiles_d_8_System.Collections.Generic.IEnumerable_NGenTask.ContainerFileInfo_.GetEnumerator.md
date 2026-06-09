# <WalkLogFiles>d__8::System.Collections.Generic.IEnumerable<NGenTask.ContainerFileInfo>.GetEnumerator

- ea: `0x4540`
- end: `0x4583`
- name: `<WalkLogFiles>d__8::System.Collections.Generic.IEnumerable<NGenTask.ContainerFileInfo>.GetEnumerator`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x4590`

## callees

- `0x4230`
- `0x4540`

## pseudocode

```c

```

## disassembly

```asm
0x4540  ldarg.0
0x4541  ldfld    int32 <WalkLogFiles>d__8::<>1__state
0x4546  ldc.i4.s 0xFE
0x4548  bne.un.s loc_4562
0x454a  ldarg.0
0x454b  ldfld    int32 <WalkLogFiles>d__8::<>l__initialThreadId
0x4550  call     int32 [mscorlib]System.Environment::get_CurrentManagedThreadId()
0x4555  bne.un.s loc_4562
0x4557  ldarg.0
0x4558  ldc.i4.0
0x4559  stfld    int32 <WalkLogFiles>d__8::<>1__state
0x455e  ldarg.0
0x455f  stloc.0
0x4560  br.s     loc_4575
0x4562  ldc.i4.0
0x4563  newobj   instance void <WalkLogFiles>d__8::.ctor(int32 <>1__state)
0x4568  stloc.0
0x4569  ldloc.0
0x456a  ldarg.0
0x456b  ldfld    class NGenTask.LogWalker <WalkLogFiles>d__8::<>4__this
0x4570  stfld    class NGenTask.LogWalker <WalkLogFiles>d__8::<>4__this
0x4575  ldloc.0
0x4576  ldarg.0
0x4577  ldfld    bool <WalkLogFiles>d__8::<>3__fOldLogs
0x457c  stfld    bool <WalkLogFiles>d__8::fOldLogs
0x4581  ldloc.0
0x4582  ret
```
