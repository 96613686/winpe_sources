# System.IO.Packaging.PackageDigitalSignature::ThrowIfInvalidated

- ea: `0x4bd70`
- end: `0x4bd89`
- name: `System.IO.Packaging.PackageDigitalSignature::ThrowIfInvalidated`
- size: `25`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x4b9f0`
- `0x4ba20`
- `0x4ba50`
- `0x4ba70`
- `0x4ba90`
- `0x4bab0`
- `0x4bad0`
- `0x4baf0`
- `0x4bb10`
- `0x4bb30`
- `0x4bb60`
- `0x4bb80`
- `0x4bba0`
- `0x4bbc0`

## callees

- `0x2c100`
- `0x4bd70`

## string_xrefs

- `0x4bd78`: `SignatureDeleted`

## pseudocode

```c

```

## disassembly

```asm
0x4bd70  ldarg.0
0x4bd71  ldfld    bool System.IO.Packaging.PackageDigitalSignature::_invalid
0x4bd76  brfalse.s loc_4BD88
0x4bd78  ldstr    aSignaturedelet// "SignatureDeleted"
0x4bd7d  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4bd82  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x4bd87  throw
0x4bd88  ret
```
