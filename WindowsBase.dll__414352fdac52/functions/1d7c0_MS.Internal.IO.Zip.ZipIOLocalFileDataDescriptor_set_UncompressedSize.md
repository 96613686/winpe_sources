# MS.Internal.IO.Zip.ZipIOLocalFileDataDescriptor::set_UncompressedSize

- ea: `0x1d7c0`
- end: `0x1d7da`
- name: `MS.Internal.IO.Zip.ZipIOLocalFileDataDescriptor::set_UncompressedSize`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1c560`

## callees

- `0xd6a0`

## string_xrefs

- `0x1d7c8`: `UncompressedSize must be non-negative`

## pseudocode

```c

```

## disassembly

```asm
0x1d7c0  ldarg.1
0x1d7c1  ldc.i4.0
0x1d7c2  conv.i8
0x1d7c3  clt
0x1d7c5  ldc.i4.0
0x1d7c6  ceq
0x1d7c8  ldstr    aUncompressedsi// "UncompressedSize must be non-negative"
0x1d7cd  call     void MS.Internal.Invariant::Assert(bool condition, string invariantMessage)
0x1d7d2  ldarg.0
0x1d7d3  ldarg.1
0x1d7d4  stfld    int64 MS.Internal.IO.Zip.ZipIOLocalFileDataDescriptor::_uncompressedSize
0x1d7d9  ret
```
