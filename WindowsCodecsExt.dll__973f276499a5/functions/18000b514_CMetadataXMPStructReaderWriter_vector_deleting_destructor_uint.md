# CMetadataXMPStructReaderWriter::`vector deleting destructor'(uint)

- ea: `0x18000b514`
- end: `0x18000b57e`
- name: `??_ECMetadataXMPStructReaderWriter@@UEAAPEAXI@Z`
- size: `106`
- prototype: `void *__fastcall(CMetadataXMPStructReaderWriter *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180023390`
- `0x1800233a0`

## callees

- `0x180009868`
- `0x18000b514`
- `0x180021a54`

## pseudocode

```c
CMetadataXMPStructReaderWriter *__fastcall CMetadataXMPStructReaderWriter::`vector deleting destructor'(
        CMetadataXMPStructReaderWriter *this,
        char a2)
{
  *(_QWORD *)this = &CMetadataXMPStructReaderWriter::`vftable'{for `IWICMetadataWriter'};
  *((_QWORD *)this + 1) = &CMetadataXMPBagReaderWriter::`vftable'{for `IWICPersistStream'};
  *((_QWORD *)this + 2) = &CMetadataRDFReaderWriter::`vftable'{for `IWICStreamProvider'};
  *((_QWORD *)this + 3) = &CMetadataXMPStructReaderWriter::`vftable'{for `CMILCOMBase'};
  *((_QWORD *)this + 5) = &CMetadataXMPStructReaderWriter::`vftable'{for `CMTALock'};
  CMetadataRDFReaderWriter::~CMetadataRDFReaderWriter(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000b514  mov     [rsp+arg_0], rbx
0x18000b519  push    rdi
0x18000b51a  sub     rsp, 20h
0x18000b51e  lea     rax, ??_7CMetadataXMPStructReaderWriter@@6BIWICMetadataWriter@@@; const CMetadataXMPStructReaderWriter::`vftable'{for `IWICMetadataWriter'}
0x18000b525  mov     ebx, edx
0x18000b527  mov     [rcx], rax
0x18000b52a  mov     rdi, rcx
0x18000b52d  lea     rax, ??_7CMetadataXMPBagReaderWriter@@6BIWICPersistStream@@@; const CMetadataXMPBagReaderWriter::`vftable'{for `IWICPersistStream'}
0x18000b534  mov     [rcx+8], rax
0x18000b538  lea     rax, ??_7CMetadataRDFReaderWriter@@6BIWICStreamProvider@@@; const CMetadataRDFReaderWriter::`vftable'{for `IWICStreamProvider'}
0x18000b53f  mov     [rcx+10h], rax
0x18000b543  lea     rax, ??_7CMetadataXMPStructReaderWriter@@6BCMILCOMBase@@@; const CMetadataXMPStructReaderWriter::`vftable'{for `CMILCOMBase'}
0x18000b54a  mov     [rcx+18h], rax
0x18000b54e  lea     rax, ??_7CMetadataXMPStructReaderWriter@@6BCMTALock@@@; const CMetadataXMPStructReaderWriter::`vftable'{for `CMTALock'}
0x18000b555  mov     [rcx+28h], rax
0x18000b559  call    ??1CMetadataRDFReaderWriter@@UEAA@XZ; CMetadataRDFReaderWriter::~CMetadataRDFReaderWriter(void)
0x18000b55e  test    bl, 1
0x18000b561  jz      short loc_18000B570
0x18000b563  mov     edx, 100h
0x18000b568  mov     rcx, rdi; Block
0x18000b56b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b570  mov     rbx, [rsp+28h+arg_0]
0x18000b575  mov     rax, rdi
0x18000b578  add     rsp, 20h
0x18000b57c  pop     rdi
0x18000b57d  retn
```
