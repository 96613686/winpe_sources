# <WalkLogFiles>d__8::<>m__Finally1

- ea: `0x44f0`
- end: `0x450b`
- name: `<WalkLogFiles>d__8::<>m__Finally1`
- size: `27`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x4250`
- `0x4270`

## callees

- `0x44f0`

## pseudocode

```c

```

## disassembly

```asm
0x44f0  ldarg.0
0x44f1  ldc.i4.m1
0x44f2  stfld    int32 <WalkLogFiles>d__8::<>1__state
0x44f7  ldarg.0
0x44f8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <WalkLogFiles>d__8::<>7__wrap3
0x44fd  brfalse.s loc_450A
0x44ff  ldarg.0
0x4500  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <WalkLogFiles>d__8::<>7__wrap3
0x4505  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x450a  ret
```
