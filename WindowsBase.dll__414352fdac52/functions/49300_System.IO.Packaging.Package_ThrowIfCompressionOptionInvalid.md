# System.IO.Packaging.Package::ThrowIfCompressionOptionInvalid

- ea: `0x49300`
- end: `0x49314`
- name: `System.IO.Packaging.Package::ThrowIfCompressionOptionInvalid`
- size: `20`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x48c20`
- `0x49990`
- `0x4af50`

## callees

- `0x49300`

## string_xrefs

- `0x49308`: `compressionOption`

## pseudocode

```c

```

## disassembly

```asm
0x49300  ldarg.0
0x49301  ldc.i4.m1
0x49302  blt.s    loc_49308
0x49304  ldarg.0
0x49305  ldc.i4.3
0x49306  ble.s    loc_49313
0x49308  ldstr    aCompressionopt// "compressionOption"
0x4930d  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x49312  throw
0x49313  ret
```
