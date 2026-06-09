# <WalkNIFiles>d__8::System.Collections.Generic.IEnumerable<NGenTask.ContainerFileInfo>.GetEnumerator

- ea: `0x4d20`
- end: `0x4d57`
- name: `<WalkNIFiles>d__8::System.Collections.Generic.IEnumerable<NGenTask.ContainerFileInfo>.GetEnumerator`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x4d60`

## callees

- `0x4940`
- `0x4d20`

## pseudocode

```c

```

## disassembly

```asm
0x4d20  ldarg.0
0x4d21  ldfld    int32 <WalkNIFiles>d__8::<>1__state
0x4d26  ldc.i4.s 0xFE
0x4d28  bne.un.s loc_4D42
0x4d2a  ldarg.0
0x4d2b  ldfld    int32 <WalkNIFiles>d__8::<>l__initialThreadId
0x4d30  call     int32 [mscorlib]System.Environment::get_CurrentManagedThreadId()
0x4d35  bne.un.s loc_4D42
0x4d37  ldarg.0
0x4d38  ldc.i4.0
0x4d39  stfld    int32 <WalkNIFiles>d__8::<>1__state
0x4d3e  ldarg.0
0x4d3f  stloc.0
0x4d40  br.s     loc_4D55
0x4d42  ldc.i4.0
0x4d43  newobj   instance void <WalkNIFiles>d__8::.ctor(int32 <>1__state)
0x4d48  stloc.0
0x4d49  ldloc.0
0x4d4a  ldarg.0
0x4d4b  ldfld    class NGenTask.AppDataDirectoryWalker <WalkNIFiles>d__8::<>4__this
0x4d50  stfld    class NGenTask.AppDataDirectoryWalker <WalkNIFiles>d__8::<>4__this
0x4d55  ldloc.0
0x4d56  ret
```
