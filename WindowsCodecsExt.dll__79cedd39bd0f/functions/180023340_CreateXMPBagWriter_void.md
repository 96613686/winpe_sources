# CreateXMPBagWriter(void)

- ea: `0x180023340`
- end: `0x180023372`
- name: `?CreateXMPBagWriter@@YAPEAUIUnknown@@XZ`
- size: `50`
- prototype: `struct IUnknown *(void)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180014258`
- `0x1800215e8`
- `0x180023340`

## pseudocode

```c
struct IUnknown *CreateXMPBagWriter(void)
{
  CMetadataXMPBagReaderWriter *v0; // rax

  v0 = (CMetadataXMPBagReaderWriter *)operator new(0xF8u);
  if ( v0 )
    v0 = CMetadataXMPBagReaderWriter::CMetadataXMPBagReaderWriter(v0, 1);
  return (struct IUnknown *)(((unsigned __int64)v0 + 24) & -(__int64)(v0 != 0));
}

```

## disassembly

```asm
0x180023340  sub     rsp, 28h
0x180023344  mov     ecx, 0F8h; Size
0x180023349  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002334e  test    rax, rax
0x180023351  jz      short loc_180023360
0x180023353  mov     edx, 1; int
0x180023358  mov     rcx, rax; this
0x18002335b  call    ??0CMetadataXMPBagReaderWriter@@QEAA@H@Z; CMetadataXMPBagReaderWriter::CMetadataXMPBagReaderWriter(int)
0x180023360  lea     rcx, [rax+18h]
0x180023364  neg     rax
0x180023367  sbb     rax, rax
0x18002336a  and     rax, rcx
0x18002336d  add     rsp, 28h
0x180023371  retn
```
