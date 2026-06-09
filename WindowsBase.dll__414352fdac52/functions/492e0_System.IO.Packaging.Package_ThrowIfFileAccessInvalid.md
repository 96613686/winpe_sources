# System.IO.Packaging.Package::ThrowIfFileAccessInvalid

- ea: `0x492e0`
- end: `0x492f4`
- name: `System.IO.Packaging.Package::ThrowIfFileAccessInvalid`
- size: `20`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x48af0`
- `0x49320`
- `0x495f0`
- `0x49e70`

## callees

- `0x492e0`

## string_xrefs

- `0x492e8`: `access`

## pseudocode

```c

```

## disassembly

```asm
0x492e0  ldarg.0
0x492e1  ldc.i4.1
0x492e2  blt.s    loc_492E8
0x492e4  ldarg.0
0x492e5  ldc.i4.3
0x492e6  ble.s    loc_492F3
0x492e8  ldstr    aAccess// "access"
0x492ed  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x492f2  throw
0x492f3  ret
```
