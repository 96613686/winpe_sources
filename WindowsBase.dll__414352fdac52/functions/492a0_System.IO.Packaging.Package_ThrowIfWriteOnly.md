# System.IO.Packaging.Package::ThrowIfWriteOnly

- ea: `0x492a0`
- end: `0x492ba`
- name: `System.IO.Packaging.Package::ThrowIfWriteOnly`
- size: `26`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x22000`
- `0x48dc0`
- `0x49100`
- `0x49810`
- `0x49870`
- `0x498b0`
- `0x49be0`
- `0x49f50`
- `0x49f90`

## callees

- `0x2c100`
- `0x492a0`

## string_xrefs

- `0x492a9`: `CannotRetrievePartsOfWriteOnlyContainer`

## pseudocode

```c

```

## disassembly

```asm
0x492a0  ldarg.0
0x492a1  ldfld    valuetype [mscorlib]System.IO.FileAccess System.IO.Packaging.Package::_openFileAccess
0x492a6  ldc.i4.2
0x492a7  bne.un.s loc_492B9
0x492a9  ldstr    aCannotretrieve// "CannotRetrievePartsOfWriteOnlyContainer"
0x492ae  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x492b3  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0x492b8  throw
0x492b9  ret
```
