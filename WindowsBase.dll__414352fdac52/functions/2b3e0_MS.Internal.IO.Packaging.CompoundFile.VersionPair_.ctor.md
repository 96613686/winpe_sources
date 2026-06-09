# MS.Internal.IO.Packaging.CompoundFile.VersionPair::.ctor

- ea: `0x2b3e0`
- end: `0x2b427`
- name: `MS.Internal.IO.Packaging.CompoundFile.VersionPair::.ctor`
- size: `71`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x28490`
- `0x2a300`
- `0x2b2e0`
- `0x45000`

## callees

- `0x2b3e0`
- `0x2c100`

## string_xrefs

- `0x2b3ef`: `VersionNumberComponentNegative`
- `0x2b408`: `VersionNumberComponentNegative`

## pseudocode

```c

```

## disassembly

```asm
0x2b3e0  ldarg.0
0x2b3e1  call     instance void [mscorlib]System.Object::.ctor()
0x2b3e6  ldarg.1
0x2b3e7  ldc.i4.0
0x2b3e8  bge.s    loc_2B3FF
0x2b3ea  ldstr    aMajor// "major"
0x2b3ef  ldstr    aVersionnumberc// "VersionNumberComponentNegative"
0x2b3f4  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x2b3f9  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0x2b3fe  throw
0x2b3ff  ldarg.2
0x2b400  ldc.i4.0
0x2b401  bge.s    loc_2B418
0x2b403  ldstr    aMinor// "minor"
0x2b408  ldstr    aVersionnumberc// "VersionNumberComponentNegative"
0x2b40d  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x2b412  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0x2b417  throw
0x2b418  ldarg.0
0x2b419  ldarg.1
0x2b41a  stfld    int16 MS.Internal.IO.Packaging.CompoundFile.VersionPair::_major
0x2b41f  ldarg.0
0x2b420  ldarg.2
0x2b421  stfld    int16 MS.Internal.IO.Packaging.CompoundFile.VersionPair::_minor
0x2b426  ret
```
