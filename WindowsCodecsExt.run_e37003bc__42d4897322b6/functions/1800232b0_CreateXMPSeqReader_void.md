# CreateXMPSeqReader(void)

- ea: `0x1800232b0`
- end: `0x1800232df`
- name: `?CreateXMPSeqReader@@YAPEAUIUnknown@@XZ`
- size: `47`
- prototype: `struct IUnknown *(void)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800215e8`
- `0x180023200`
- `0x1800232b0`

## pseudocode

```c
struct IUnknown *CreateXMPSeqReader(void)
{
  CMetadataXMPSeqReaderWriter *v0; // rax

  v0 = (CMetadataXMPSeqReaderWriter *)operator new(0xF8u);
  if ( v0 )
    v0 = CMetadataXMPSeqReaderWriter::CMetadataXMPSeqReaderWriter(v0, 0);
  return (struct IUnknown *)(((unsigned __int64)v0 + 24) & -(__int64)(v0 != 0));
}

```

## disassembly

```asm
0x1800232b0  sub     rsp, 28h
0x1800232b4  mov     ecx, 0F8h; Size
0x1800232b9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800232be  test    rax, rax
0x1800232c1  jz      short loc_1800232CD
0x1800232c3  xor     edx, edx; int
0x1800232c5  mov     rcx, rax; this
0x1800232c8  call    ??0CMetadataXMPSeqReaderWriter@@QEAA@H@Z; CMetadataXMPSeqReaderWriter::CMetadataXMPSeqReaderWriter(int)
0x1800232cd  lea     rcx, [rax+18h]
0x1800232d1  neg     rax
0x1800232d4  sbb     rax, rax
0x1800232d7  and     rax, rcx
0x1800232da  add     rsp, 28h
0x1800232de  retn
```
