# <GetAdvertisedPackageInfo>d__4::<>m__Finally1

- ea: `0x64a0`
- end: `0x64bb`
- name: `<GetAdvertisedPackageInfo>d__4::<>m__Finally1`
- size: `27`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x6330`
- `0x6380`

## callees

- `0x64a0`

## pseudocode

```c

```

## disassembly

```asm
0x64a0  ldarg.0
0x64a1  ldc.i4.m1
0x64a2  stfld    int32 <GetAdvertisedPackageInfo>d__4::<>1__state
0x64a7  ldarg.0
0x64a8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage> <GetAdvertisedPackageInfo>d__4::<>7__wrap1
0x64ad  brfalse.s loc_64BA
0x64af  ldarg.0
0x64b0  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage> <GetAdvertisedPackageInfo>d__4::<>7__wrap1
0x64b5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x64ba  ret
```
