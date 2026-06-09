# CreateXMPSeqWriter(void)

- ea: `0x1800232f0`
- end: `0x180023322`
- name: `?CreateXMPSeqWriter@@YAPEAUIUnknown@@XZ`
- size: `50`
- prototype: `struct IUnknown *(void)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800215e8`
- `0x180023200`
- `0x1800232f0`

## pseudocode

```c
struct IUnknown *CreateXMPSeqWriter(void)
{
  CMetadataXMPSeqReaderWriter *v0; // rax

  v0 = (CMetadataXMPSeqReaderWriter *)operator new(0xF8u);
  if ( v0 )
    v0 = CMetadataXMPSeqReaderWriter::CMetadataXMPSeqReaderWriter(v0, 1);
  return (struct IUnknown *)(((unsigned __int64)v0 + 24) & -(__int64)(v0 != 0));
}

```

## disassembly

```asm
0x1800232f0  sub     rsp, 28h
0x1800232f4  mov     ecx, 0F8h; Size
0x1800232f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800232fe  test    rax, rax
0x180023301  jz      short loc_180023310
0x180023303  mov     edx, 1; int
0x180023308  mov     rcx, rax; this
0x18002330b  call    ??0CMetadataXMPSeqReaderWriter@@QEAA@H@Z; CMetadataXMPSeqReaderWriter::CMetadataXMPSeqReaderWriter(int)
0x180023310  lea     rcx, [rax+18h]
0x180023314  neg     rax
0x180023317  sbb     rax, rax
0x18002331a  and     rax, rcx
0x18002331d  add     rsp, 28h
0x180023321  retn
```
