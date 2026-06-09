# <GetUserProfileDirectories>d__10::System.Collections.Generic.IEnumerable<System.IO.DirectoryInfo>.GetEnumerator

- ea: `0x5260`
- end: `0x5297`
- name: `<GetUserProfileDirectories>d__10::System.Collections.Generic.IEnumerable<System.IO.DirectoryInfo>.GetEnumerator`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x52a0`

## callees

- `0x4fa0`
- `0x5260`

## pseudocode

```c

```

## disassembly

```asm
0x5260  ldarg.0
0x5261  ldfld    int32 <GetUserProfileDirectories>d__10::<>1__state
0x5266  ldc.i4.s 0xFE
0x5268  bne.un.s loc_5282
0x526a  ldarg.0
0x526b  ldfld    int32 <GetUserProfileDirectories>d__10::<>l__initialThreadId
0x5270  call     int32 [mscorlib]System.Environment::get_CurrentManagedThreadId()
0x5275  bne.un.s loc_5282
0x5277  ldarg.0
0x5278  ldc.i4.0
0x5279  stfld    int32 <GetUserProfileDirectories>d__10::<>1__state
0x527e  ldarg.0
0x527f  stloc.0
0x5280  br.s     loc_5295
0x5282  ldc.i4.0
0x5283  newobj   instance void <GetUserProfileDirectories>d__10::.ctor(int32 <>1__state)
0x5288  stloc.0
0x5289  ldloc.0
0x528a  ldarg.0
0x528b  ldfld    class NGenTask.AppDataDirectoryWalker <GetUserProfileDirectories>d__10::<>4__this
0x5290  stfld    class NGenTask.AppDataDirectoryWalker <GetUserProfileDirectories>d__10::<>4__this
0x5295  ldloc.0
0x5296  ret
```
