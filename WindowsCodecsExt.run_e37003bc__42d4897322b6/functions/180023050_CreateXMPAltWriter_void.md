# CreateXMPAltWriter(void)

- ea: `0x180023050`
- end: `0x180023082`
- name: `?CreateXMPAltWriter@@YAPEAUIUnknown@@XZ`
- size: `50`
- prototype: `struct IUnknown *(void)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000b298`
- `0x1800215e8`
- `0x180023050`

## pseudocode

```c
struct IUnknown *CreateXMPAltWriter(void)
{
  CMetadataXMPAltReaderWriter *v0; // rax

  v0 = (CMetadataXMPAltReaderWriter *)operator new(0x100u);
  if ( v0 )
    v0 = CMetadataXMPAltReaderWriter::CMetadataXMPAltReaderWriter(v0, 1);
  return (struct IUnknown *)(((unsigned __int64)v0 + 24) & -(__int64)(v0 != 0));
}

```

## disassembly

```asm
0x180023050  sub     rsp, 28h
0x180023054  mov     ecx, 100h; Size
0x180023059  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002305e  test    rax, rax
0x180023061  jz      short loc_180023070
0x180023063  mov     edx, 1; int
0x180023068  mov     rcx, rax; this
0x18002306b  call    ??0CMetadataXMPAltReaderWriter@@QEAA@H@Z; CMetadataXMPAltReaderWriter::CMetadataXMPAltReaderWriter(int)
0x180023070  lea     rcx, [rax+18h]
0x180023074  neg     rax
0x180023077  sbb     rax, rax
0x18002307a  and     rax, rcx
0x18002307d  add     rsp, 28h
0x180023081  retn
```
