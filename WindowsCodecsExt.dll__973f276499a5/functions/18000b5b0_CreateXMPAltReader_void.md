# CreateXMPAltReader(void)

- ea: `0x18000b5b0`
- end: `0x18000b5e1`
- name: `?CreateXMPAltReader@@YAPEAUIUnknown@@XZ`
- size: `49`
- prototype: `struct IUnknown *(void)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000b298`
- `0x18000b5b0`
- `0x1800215e8`

## pseudocode

```c
struct IUnknown *CreateXMPAltReader(void)
{
  CMetadataXMPAltReaderWriter *v0; // rax

  v0 = (CMetadataXMPAltReaderWriter *)operator new(0x100u);
  if ( v0 )
    v0 = CMetadataXMPAltReaderWriter::CMetadataXMPAltReaderWriter(v0, 0);
  return (struct IUnknown *)(((unsigned __int64)v0 + 24) & -(__int64)(v0 != 0));
}

```

## disassembly

```asm
0x18000b5b0  sub     rsp, 28h
0x18000b5b4  mov     ecx, 100h; Size
0x18000b5b9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b5be  test    rax, rax
0x18000b5c1  jnz     short loc_18000B5D5
0x18000b5c3  lea     rcx, [rax+18h]
0x18000b5c7  neg     rax
0x18000b5ca  sbb     rax, rax
0x18000b5cd  and     rax, rcx
0x18000b5d0  add     rsp, 28h
0x18000b5d4  retn
0x18000b5d5  xor     edx, edx; int
0x18000b5d7  mov     rcx, rax; this
0x18000b5da  call    ??0CMetadataXMPAltReaderWriter@@QEAA@H@Z; CMetadataXMPAltReaderWriter::CMetadataXMPAltReaderWriter(int)
0x18000b5df  jmp     short loc_18000B5C3
```
