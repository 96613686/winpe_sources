# System.Net.Http.Internal.ByteRangeStream::ReadByte

- ea: `0x4c80`
- end: `0x4c93`
- name: `System.Net.Http.Internal.ByteRangeStream::ReadByte`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x4c80`
- `0x4dd0`
- `0x53c0`

## pseudocode

```c

```

## disassembly

```asm
0x4c80  ldarg.0
0x4c81  ldc.i4.1
0x4c82  call     instance int32 System.Net.Http.Internal.ByteRangeStream::PrepareStreamForRangeRead(int32 count)
0x4c87  ldc.i4.0
0x4c88  bgt.s    loc_4C8C
0x4c8a  ldc.i4.m1
0x4c8b  ret
0x4c8c  ldarg.0
0x4c8d  call     instance int32 System.Net.Http.Internal.DelegatingStream::ReadByte()
0x4c92  ret
```
