# CMetadataXMPBagReaderWriter::`vector deleting destructor'(uint)

- ea: `0x18000b42c`
- end: `0x18000b496`
- name: `??_ECMetadataXMPBagReaderWriter@@UEAAPEAXI@Z`
- size: `106`
- prototype: `void *__fastcall(CMetadataXMPBagReaderWriter *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180023290`
- `0x1800232a0`

## callees

- `0x180009868`
- `0x18000b42c`
- `0x180021a54`

## pseudocode

```c
CMetadataXMPBagReaderWriter *__fastcall CMetadataXMPBagReaderWriter::`vector deleting destructor'(
        CMetadataXMPBagReaderWriter *this,
        char a2)
{
  *(_QWORD *)this = &CMetadataRDFIndexReaderWriter::`vftable'{for `IWICMetadataWriter'};
  *((_QWORD *)this + 1) = &CMetadataXMPBagReaderWriter::`vftable'{for `IWICPersistStream'};
  *((_QWORD *)this + 2) = &CMetadataRDFReaderWriter::`vftable'{for `IWICStreamProvider'};
  *((_QWORD *)this + 3) = &CMetadataXMPBagReaderWriter::`vftable'{for `CMILCOMBase'};
  *((_QWORD *)this + 5) = &CMetadataRDFIndexReaderWriter::`vftable'{for `CMTALock'};
  CMetadataRDFReaderWriter::~CMetadataRDFReaderWriter(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000b42c  mov     [rsp+arg_0], rbx
0x18000b431  push    rdi
0x18000b432  sub     rsp, 20h
0x18000b436  lea     rax, ??_7CMetadataRDFIndexReaderWriter@@6BIWICMetadataWriter@@@; const CMetadataRDFIndexReaderWriter::`vftable'{for `IWICMetadataWriter'}
0x18000b43d  mov     ebx, edx
0x18000b43f  mov     [rcx], rax
0x18000b442  mov     rdi, rcx
0x18000b445  lea     rax, ??_7CMetadataXMPBagReaderWriter@@6BIWICPersistStream@@@; const CMetadataXMPBagReaderWriter::`vftable'{for `IWICPersistStream'}
0x18000b44c  mov     [rcx+8], rax
0x18000b450  lea     rax, ??_7CMetadataRDFReaderWriter@@6BIWICStreamProvider@@@; const CMetadataRDFReaderWriter::`vftable'{for `IWICStreamProvider'}
0x18000b457  mov     [rcx+10h], rax
0x18000b45b  lea     rax, ??_7CMetadataXMPBagReaderWriter@@6BCMILCOMBase@@@; const CMetadataXMPBagReaderWriter::`vftable'{for `CMILCOMBase'}
0x18000b462  mov     [rcx+18h], rax
0x18000b466  lea     rax, ??_7CMetadataRDFIndexReaderWriter@@6BCMTALock@@@; const CMetadataRDFIndexReaderWriter::`vftable'{for `CMTALock'}
0x18000b46d  mov     [rcx+28h], rax
0x18000b471  call    ??1CMetadataRDFReaderWriter@@UEAA@XZ; CMetadataRDFReaderWriter::~CMetadataRDFReaderWriter(void)
0x18000b476  test    bl, 1
0x18000b479  jz      short loc_18000B488
0x18000b47b  mov     edx, 0F8h
0x18000b480  mov     rcx, rdi; Block
0x18000b483  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b488  mov     rbx, [rsp+28h+arg_0]
0x18000b48d  mov     rax, rdi
0x18000b490  add     rsp, 20h
0x18000b494  pop     rdi
0x18000b495  retn
```
