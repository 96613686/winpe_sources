# <WalkCurrentUserContainerNIDirectories>d__9::System.Collections.Generic.IEnumerable<NGenTask.ContainerDirectoryInfo>.GetEnumerator

- ea: `0x4f40`
- end: `0x4f77`
- name: `<WalkCurrentUserContainerNIDirectories>d__9::System.Collections.Generic.IEnumerable<NGenTask.ContainerDirectoryInfo>.GetEnumerator`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x4f80`

## callees

- `0x4d80`
- `0x4f40`

## pseudocode

```c

```

## disassembly

```asm
0x4f40  ldarg.0
0x4f41  ldfld    int32 <WalkCurrentUserContainerNIDirectories>d__9::<>1__state
0x4f46  ldc.i4.s 0xFE
0x4f48  bne.un.s loc_4F62
0x4f4a  ldarg.0
0x4f4b  ldfld    int32 <WalkCurrentUserContainerNIDirectories>d__9::<>l__initialThreadId
0x4f50  call     int32 [mscorlib]System.Environment::get_CurrentManagedThreadId()
0x4f55  bne.un.s loc_4F62
0x4f57  ldarg.0
0x4f58  ldc.i4.0
0x4f59  stfld    int32 <WalkCurrentUserContainerNIDirectories>d__9::<>1__state
0x4f5e  ldarg.0
0x4f5f  stloc.0
0x4f60  br.s     loc_4F75
0x4f62  ldc.i4.0
0x4f63  newobj   instance void <WalkCurrentUserContainerNIDirectories>d__9::.ctor(int32 <>1__state)
0x4f68  stloc.0
0x4f69  ldloc.0
0x4f6a  ldarg.0
0x4f6b  ldfld    class NGenTask.AppDataDirectoryWalker <WalkCurrentUserContainerNIDirectories>d__9::<>4__this
0x4f70  stfld    class NGenTask.AppDataDirectoryWalker <WalkCurrentUserContainerNIDirectories>d__9::<>4__this
0x4f75  ldloc.0
0x4f76  ret
```
