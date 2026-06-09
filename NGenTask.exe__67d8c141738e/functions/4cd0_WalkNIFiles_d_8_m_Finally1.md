# <WalkNIFiles>d__8::<>m__Finally1

- ea: `0x4cd0`
- end: `0x4ceb`
- name: `<WalkNIFiles>d__8::<>m__Finally1`
- size: `27`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x4960`
- `0x4980`

## callees

- `0x4cd0`

## pseudocode

```c

```

## disassembly

```asm
0x4cd0  ldarg.0
0x4cd1  ldc.i4.m1
0x4cd2  stfld    int32 <WalkNIFiles>d__8::<>1__state
0x4cd7  ldarg.0
0x4cd8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <WalkNIFiles>d__8::<>7__wrap2
0x4cdd  brfalse.s loc_4CEA
0x4cdf  ldarg.0
0x4ce0  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <WalkNIFiles>d__8::<>7__wrap2
0x4ce5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4cea  ret
```
