# <WalkLogDirectories>d__5::MoveNext

- ea: `0x4130`
- end: `0x4186`
- name: `<WalkLogDirectories>d__5::MoveNext`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x3e00`
- `0x3f10`
- `0x4130`

## pseudocode

```c

```

## disassembly

```asm
0x4130  ldarg.0
0x4131  ldfld    int32 <WalkLogDirectories>d__5::<>1__state
0x4136  stloc.0
0x4137  ldarg.0
0x4138  ldfld    class NGenTask.LogWalker <WalkLogDirectories>d__5::<>4__this
0x413d  stloc.1
0x413e  ldloc.0
0x413f  brfalse.s loc_4147
0x4141  ldloc.0
0x4142  ldc.i4.1
0x4143  beq.s    loc_417D
0x4145  ldc.i4.0
0x4146  ret
0x4147  ldarg.0
0x4148  ldc.i4.m1
0x4149  stfld    int32 <WalkLogDirectories>d__5::<>1__state
0x414e  ldloc.1
0x414f  ldfld    class NGenTask.ContainerDirectoryInfo NGenTask.LogWalker::m_logDirectory
0x4154  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x4159  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x415e  brfalse.s loc_4184
0x4160  ldloc.1
0x4161  call     instance bool NGenTask.LogWalker::IsStopRequested()
0x4166  brtrue.s loc_4184
0x4168  ldarg.0
0x4169  ldloc.1
0x416a  ldfld    class NGenTask.ContainerDirectoryInfo NGenTask.LogWalker::m_logDirectory
0x416f  stfld    class NGenTask.ContainerDirectoryInfo <WalkLogDirectories>d__5::<>2__current
0x4174  ldarg.0
0x4175  ldc.i4.1
0x4176  stfld    int32 <WalkLogDirectories>d__5::<>1__state
0x417b  ldc.i4.1
0x417c  ret
0x417d  ldarg.0
0x417e  ldc.i4.m1
0x417f  stfld    int32 <WalkLogDirectories>d__5::<>1__state
0x4184  ldc.i4.0
0x4185  ret
```
