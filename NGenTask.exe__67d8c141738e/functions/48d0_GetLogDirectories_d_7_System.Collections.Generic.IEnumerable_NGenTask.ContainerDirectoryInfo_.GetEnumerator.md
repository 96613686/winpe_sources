# <GetLogDirectories>d__7::System.Collections.Generic.IEnumerable<NGenTask.ContainerDirectoryInfo>.GetEnumerator

- ea: `0x48d0`
- end: `0x4907`
- name: `<GetLogDirectories>d__7::System.Collections.Generic.IEnumerable<NGenTask.ContainerDirectoryInfo>.GetEnumerator`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x4910`

## callees

- `0x45b0`
- `0x48d0`

## pseudocode

```c

```

## disassembly

```asm
0x48d0  ldarg.0
0x48d1  ldfld    int32 <GetLogDirectories>d__7::<>1__state
0x48d6  ldc.i4.s 0xFE
0x48d8  bne.un.s loc_48F2
0x48da  ldarg.0
0x48db  ldfld    int32 <GetLogDirectories>d__7::<>l__initialThreadId
0x48e0  call     int32 [mscorlib]System.Environment::get_CurrentManagedThreadId()
0x48e5  bne.un.s loc_48F2
0x48e7  ldarg.0
0x48e8  ldc.i4.0
0x48e9  stfld    int32 <GetLogDirectories>d__7::<>1__state
0x48ee  ldarg.0
0x48ef  stloc.0
0x48f0  br.s     loc_4905
0x48f2  ldc.i4.0
0x48f3  newobj   instance void <GetLogDirectories>d__7::.ctor(int32 <>1__state)
0x48f8  stloc.0
0x48f9  ldloc.0
0x48fa  ldarg.0
0x48fb  ldfld    class NGenTask.AppDataDirectoryWalker <GetLogDirectories>d__7::<>4__this
0x4900  stfld    class NGenTask.AppDataDirectoryWalker <GetLogDirectories>d__7::<>4__this
0x4905  ldloc.0
0x4906  ret
```
