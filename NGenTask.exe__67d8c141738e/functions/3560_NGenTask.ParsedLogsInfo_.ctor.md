# NGenTask.ParsedLogsInfo::.ctor

- ea: `0x3560`
- end: `0x3588`
- name: `NGenTask.ParsedLogsInfo::.ctor`
- size: `40`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x11c0`
- `0x3790`
- `0x3930`

## pseudocode

```c

```

## disassembly

```asm
0x3560  ldarg.0
0x3561  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.DateTime>::.ctor()
0x3566  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.DateTime> NGenTask.ParsedLogsInfo::m_nativeImages
0x356b  ldarg.0
0x356c  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<class NGenTask.ILAssembly>::.ctor()
0x3571  stfld    class [System.Core]System.Collections.Generic.HashSet`1<class NGenTask.ILAssembly> NGenTask.ParsedLogsInfo::m_ilAssemblies
0x3576  ldarg.0
0x3577  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class NGenTask.ContainerRootDirectoryInfo, class [System.Core]System.Collections.Generic.HashSet`1<string>>::.ctor()
0x357c  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class NGenTask.ContainerRootDirectoryInfo, class [System.Core]System.Collections.Generic.HashSet`1<string>> NGenTask.ParsedLogsInfo::m_containerAssociations
0x3581  ldarg.0
0x3582  call     instance void [mscorlib]System.Object::.ctor()
0x3587  ret
```
