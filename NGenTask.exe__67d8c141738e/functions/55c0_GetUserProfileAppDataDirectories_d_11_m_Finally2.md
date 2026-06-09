# <GetUserProfileAppDataDirectories>d__11::<>m__Finally2

- ea: `0x55c0`
- end: `0x55da`
- name: `<GetUserProfileAppDataDirectories>d__11::<>m__Finally2`
- size: `26`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x52e0`
- `0x5310`

## pseudocode

```c

```

## disassembly

```asm
0x55c0  ldarg.0
0x55c1  ldc.i4.s 0xFD
0x55c3  stfld    int32 <GetUserProfileAppDataDirectories>d__11::<>1__state
0x55c8  ldarg.0
0x55c9  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class NGenTask.ContainerDirectoryInfo> <GetUserProfileAppDataDirectories>d__11::<>7__wrap2
0x55ce  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class NGenTask.ContainerDirectoryInfo>
0x55d4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x55d9  ret
```
