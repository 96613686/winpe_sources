# <WalkLogDirectories>d__5::System.Collections.Generic.IEnumerable<NGenTask.ContainerDirectoryInfo>.GetEnumerator

- ea: `0x41c0`
- end: `0x41f7`
- name: `<WalkLogDirectories>d__5::System.Collections.Generic.IEnumerable<NGenTask.ContainerDirectoryInfo>.GetEnumerator`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x4200`

## callees

- `0x4100`
- `0x41c0`

## pseudocode

```c

```

## disassembly

```asm
0x41c0  ldarg.0
0x41c1  ldfld    int32 <WalkLogDirectories>d__5::<>1__state
0x41c6  ldc.i4.s 0xFE
0x41c8  bne.un.s loc_41E2
0x41ca  ldarg.0
0x41cb  ldfld    int32 <WalkLogDirectories>d__5::<>l__initialThreadId
0x41d0  call     int32 [mscorlib]System.Environment::get_CurrentManagedThreadId()
0x41d5  bne.un.s loc_41E2
0x41d7  ldarg.0
0x41d8  ldc.i4.0
0x41d9  stfld    int32 <WalkLogDirectories>d__5::<>1__state
0x41de  ldarg.0
0x41df  stloc.0
0x41e0  br.s     loc_41F5
0x41e2  ldc.i4.0
0x41e3  newobj   instance void <WalkLogDirectories>d__5::.ctor(int32 <>1__state)
0x41e8  stloc.0
0x41e9  ldloc.0
0x41ea  ldarg.0
0x41eb  ldfld    class NGenTask.LogWalker <WalkLogDirectories>d__5::<>4__this
0x41f0  stfld    class NGenTask.LogWalker <WalkLogDirectories>d__5::<>4__this
0x41f5  ldloc.0
0x41f6  ret
```
