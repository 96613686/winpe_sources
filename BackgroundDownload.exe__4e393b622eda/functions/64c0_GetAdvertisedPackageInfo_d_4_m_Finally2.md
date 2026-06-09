# <GetAdvertisedPackageInfo>d__4::<>m__Finally2

- ea: `0x64c0`
- end: `0x64dc`
- name: `<GetAdvertisedPackageInfo>d__4::<>m__Finally2`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x6330`
- `0x6380`

## callees

- `0x64c0`

## pseudocode

```c

```

## disassembly

```asm
0x64c0  ldarg.0
0x64c1  ldc.i4.s 0xFD
0x64c3  stfld    int32 <GetAdvertisedPackageInfo>d__4::<>1__state
0x64c8  ldarg.0
0x64c9  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedResource> <GetAdvertisedPackageInfo>d__4::<>7__wrap2
0x64ce  brfalse.s loc_64DB
0x64d0  ldarg.0
0x64d1  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedResource> <GetAdvertisedPackageInfo>d__4::<>7__wrap2
0x64d6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x64db  ret
```
