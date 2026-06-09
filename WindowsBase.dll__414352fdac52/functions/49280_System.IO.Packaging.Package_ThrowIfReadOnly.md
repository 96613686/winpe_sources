# System.IO.Packaging.Package::ThrowIfReadOnly

- ea: `0x49280`
- end: `0x4929a`
- name: `System.IO.Packaging.Package::ThrowIfReadOnly`
- size: `26`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x22060`
- `0x48c20`
- `0x48cd0`
- `0x49010`
- `0x49080`
- `0x490b0`
- `0x49b50`
- `0x49b80`

## callees

- `0x2c100`
- `0x49280`

## string_xrefs

- `0x49289`: `CannotModifyReadOnlyContainer`

## pseudocode

```c

```

## disassembly

```asm
0x49280  ldarg.0
0x49281  ldfld    valuetype [mscorlib]System.IO.FileAccess System.IO.Packaging.Package::_openFileAccess
0x49286  ldc.i4.1
0x49287  bne.un.s loc_49299
0x49289  ldstr    aCannotmodifyre// "CannotModifyReadOnlyContainer"
0x4928e  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x49293  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0x49298  throw
0x49299  ret
```
