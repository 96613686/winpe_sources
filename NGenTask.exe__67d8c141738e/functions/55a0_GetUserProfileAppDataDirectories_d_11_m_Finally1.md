# <GetUserProfileAppDataDirectories>d__11::<>m__Finally1

- ea: `0x55a0`
- end: `0x55bb`
- name: `<GetUserProfileAppDataDirectories>d__11::<>m__Finally1`
- size: `27`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x52e0`
- `0x5310`

## callees

- `0x55a0`

## pseudocode

```c

```

## disassembly

```asm
0x55a0  ldarg.0
0x55a1  ldc.i4.m1
0x55a2  stfld    int32 <GetUserProfileAppDataDirectories>d__11::<>1__state
0x55a7  ldarg.0
0x55a8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.IO.DirectoryInfo> <GetUserProfileAppDataDirectories>d__11::<>7__wrap1
0x55ad  brfalse.s loc_55BA
0x55af  ldarg.0
0x55b0  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.IO.DirectoryInfo> <GetUserProfileAppDataDirectories>d__11::<>7__wrap1
0x55b5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x55ba  ret
```
