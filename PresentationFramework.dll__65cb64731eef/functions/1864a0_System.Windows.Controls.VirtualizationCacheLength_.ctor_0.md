# System.Windows.Controls.VirtualizationCacheLength::.ctor_0

- ea: `0x1864a0`
- end: `0x1864fb`
- name: `System.Windows.Controls.VirtualizationCacheLength::.ctor_0`
- size: `91`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x186490`
- `0x186790`
- `0x1a55f0`
- `0x1a5c50`
- `0x1a6560`
- `0x1a69f0`
- `0x1a8210`

## callees

- `0x38c70`
- `0x1864a0`

## string_xrefs

- `0x1864b5`: `cacheBeforeViewport`
- `0x1864db`: `cacheAfterViewport`

## pseudocode

```c

```

## disassembly

```asm
0x1864a0  ldarg.1
0x1864a1  call     bool [WindowsBase]MS.Internal.DoubleUtil::IsNaN(float64)
0x1864a6  brfalse.s loc_1864C6
0x1864a8  ldstr    aInvalidctorpar// "InvalidCtorParameterNoNaN"
0x1864ad  ldc.i4.1
0x1864ae  newarr   [mscorlib]System.Object
0x1864b3  dup
0x1864b4  ldc.i4.0
0x1864b5  ldstr    aCachebeforevie// "cacheBeforeViewport"
0x1864ba  stelem.ref
0x1864bb  call     string System.Windows.SR::Get(string id, object[] args)
0x1864c0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1864c5  throw
0x1864c6  ldarg.2
0x1864c7  call     bool [WindowsBase]MS.Internal.DoubleUtil::IsNaN(float64)
0x1864cc  brfalse.s loc_1864EC
0x1864ce  ldstr    aInvalidctorpar// "InvalidCtorParameterNoNaN"
0x1864d3  ldc.i4.1
0x1864d4  newarr   [mscorlib]System.Object
0x1864d9  dup
0x1864da  ldc.i4.0
0x1864db  ldstr    aCacheafterview// "cacheAfterViewport"
0x1864e0  stelem.ref
0x1864e1  call     string System.Windows.SR::Get(string id, object[] args)
0x1864e6  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1864eb  throw
0x1864ec  ldarg.0
0x1864ed  ldarg.1
0x1864ee  stfld    float64 System.Windows.Controls.VirtualizationCacheLength::_cacheBeforeViewport
0x1864f3  ldarg.0
0x1864f4  ldarg.2
0x1864f5  stfld    float64 System.Windows.Controls.VirtualizationCacheLength::_cacheAfterViewport
0x1864fa  ret
```
