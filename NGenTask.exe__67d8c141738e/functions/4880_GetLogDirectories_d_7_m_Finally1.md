# <GetLogDirectories>d__7::<>m__Finally1

- ea: `0x4880`
- end: `0x489b`
- name: `<GetLogDirectories>d__7::<>m__Finally1`
- size: `27`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x45d0`
- `0x45f0`

## callees

- `0x4880`

## pseudocode

```c

```

## disassembly

```asm
0x4880  ldarg.0
0x4881  ldc.i4.m1
0x4882  stfld    int32 <GetLogDirectories>d__7::<>1__state
0x4887  ldarg.0
0x4888  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <GetLogDirectories>d__7::<>7__wrap2
0x488d  brfalse.s loc_489A
0x488f  ldarg.0
0x4890  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <GetLogDirectories>d__7::<>7__wrap2
0x4895  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x489a  ret
```
