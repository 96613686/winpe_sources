# <GetUserProfileAppDataDirectories>d__11::System.Collections.Generic.IEnumerable<NGenTask.ContainerDirectoryInfo>.GetEnumerator

- ea: `0x5610`
- end: `0x5647`
- name: `<GetUserProfileAppDataDirectories>d__11::System.Collections.Generic.IEnumerable<NGenTask.ContainerDirectoryInfo>.GetEnumerator`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x5650`

## callees

- `0x52c0`
- `0x5610`

## pseudocode

```c

```

## disassembly

```asm
0x5610  ldarg.0
0x5611  ldfld    int32 <GetUserProfileAppDataDirectories>d__11::<>1__state
0x5616  ldc.i4.s 0xFE
0x5618  bne.un.s loc_5632
0x561a  ldarg.0
0x561b  ldfld    int32 <GetUserProfileAppDataDirectories>d__11::<>l__initialThreadId
0x5620  call     int32 [mscorlib]System.Environment::get_CurrentManagedThreadId()
0x5625  bne.un.s loc_5632
0x5627  ldarg.0
0x5628  ldc.i4.0
0x5629  stfld    int32 <GetUserProfileAppDataDirectories>d__11::<>1__state
0x562e  ldarg.0
0x562f  stloc.0
0x5630  br.s     loc_5645
0x5632  ldc.i4.0
0x5633  newobj   instance void <GetUserProfileAppDataDirectories>d__11::.ctor(int32 <>1__state)
0x5638  stloc.0
0x5639  ldloc.0
0x563a  ldarg.0
0x563b  ldfld    class NGenTask.AppDataDirectoryWalker <GetUserProfileAppDataDirectories>d__11::<>4__this
0x5640  stfld    class NGenTask.AppDataDirectoryWalker <GetUserProfileAppDataDirectories>d__11::<>4__this
0x5645  ldloc.0
0x5646  ret
```
