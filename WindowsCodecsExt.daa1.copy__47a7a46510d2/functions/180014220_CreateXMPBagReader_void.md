# CreateXMPBagReader(void)

- ea: `0x180014220`
- end: `0x180014251`
- name: `?CreateXMPBagReader@@YAPEAUIUnknown@@XZ`
- size: `49`
- prototype: `struct IUnknown *(void)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180014220`
- `0x180014258`
- `0x1800215e8`

## pseudocode

```c
struct IUnknown *CreateXMPBagReader(void)
{
  CMetadataXMPBagReaderWriter *v0; // rax

  v0 = (CMetadataXMPBagReaderWriter *)operator new(0xF8u);
  if ( v0 )
    v0 = CMetadataXMPBagReaderWriter::CMetadataXMPBagReaderWriter(v0, 0);
  return (struct IUnknown *)(((unsigned __int64)v0 + 24) & -(__int64)(v0 != 0));
}

```

## disassembly

```asm
0x180014220  sub     rsp, 28h
0x180014224  mov     ecx, 0F8h; Size
0x180014229  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001422e  test    rax, rax
0x180014231  jnz     short loc_180014245
0x180014233  lea     rcx, [rax+18h]
0x180014237  neg     rax
0x18001423a  sbb     rax, rax
0x18001423d  and     rax, rcx
0x180014240  add     rsp, 28h
0x180014244  retn
0x180014245  xor     edx, edx; int
0x180014247  mov     rcx, rax; this
0x18001424a  call    ??0CMetadataXMPBagReaderWriter@@QEAA@H@Z; CMetadataXMPBagReaderWriter::CMetadataXMPBagReaderWriter(int)
0x18001424f  jmp     short loc_180014233
```
