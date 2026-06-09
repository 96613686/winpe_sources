# <WalkCurrentUserContainerNIDirectories>d__9::<>m__Finally1

- ea: `0x4ef0`
- end: `0x4f0b`
- name: `<WalkCurrentUserContainerNIDirectories>d__9::<>m__Finally1`
- size: `27`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x4da0`
- `0x4dc0`

## callees

- `0x4ef0`

## pseudocode

```c

```

## disassembly

```asm
0x4ef0  ldarg.0
0x4ef1  ldc.i4.m1
0x4ef2  stfld    int32 <WalkCurrentUserContainerNIDirectories>d__9::<>1__state
0x4ef7  ldarg.0
0x4ef8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <WalkCurrentUserContainerNIDirectories>d__9::<>7__wrap2
0x4efd  brfalse.s loc_4F0A
0x4eff  ldarg.0
0x4f00  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <WalkCurrentUserContainerNIDirectories>d__9::<>7__wrap2
0x4f05  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4f0a  ret
```
