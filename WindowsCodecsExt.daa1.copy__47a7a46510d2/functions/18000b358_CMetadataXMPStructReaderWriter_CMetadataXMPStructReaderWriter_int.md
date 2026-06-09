# CMetadataXMPStructReaderWriter::CMetadataXMPStructReaderWriter(int)

- ea: `0x18000b358`
- end: `0x18000b3e3`
- name: `??0CMetadataXMPStructReaderWriter@@QEAA@H@Z`
- size: `139`
- prototype: `CMetadataXMPStructReaderWriter *__fastcall(CMetadataXMPStructReaderWriter *__hidden this, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b4a0`
- `0x1800233b0`

## callees

- `0x1800093c0`

## pseudocode

```c
CMetadataXMPStructReaderWriter *__fastcall CMetadataXMPStructReaderWriter::CMetadataXMPStructReaderWriter(
        CMetadataXMPStructReaderWriter *this,
        int a2)
{
  GUID *v4; // rax

  CMetadataRDFReaderWriter::CMetadataRDFReaderWriter(this, a2);
  *((_DWORD *)this + 62) = 1;
  *(_QWORD *)this = &CMetadataXMPStructReaderWriter::`vftable'{for `IWICMetadataWriter'};
  *((_QWORD *)this + 1) = &CMetadataXMPBagReaderWriter::`vftable'{for `IWICPersistStream'};
  *((_QWORD *)this + 2) = &CMetadataRDFReaderWriter::`vftable'{for `IWICStreamProvider'};
  *((_QWORD *)this + 3) = &CMetadataXMPStructReaderWriter::`vftable'{for `CMILCOMBase'};
  *((_QWORD *)this + 5) = &CMetadataXMPStructReaderWriter::`vftable'{for `CMTALock'};
  *((_QWORD *)this + 19) = &GUID_MetadataFormatXMPStruct;
  v4 = &CLSID_WICXMPStructMetadataWriter;
  if ( !a2 )
    v4 = &CLSID_WICXMPStructMetadataReader;
  *((_QWORD *)this + 20) = v4;
  return this;
}

```

## disassembly

```asm
0x18000b358  mov     [rsp+arg_0], rbx
0x18000b35d  push    rdi
0x18000b35e  sub     rsp, 20h
0x18000b362  mov     ebx, edx
0x18000b364  mov     rdi, rcx
0x18000b367  call    ??0CMetadataRDFReaderWriter@@QEAA@H@Z; CMetadataRDFReaderWriter::CMetadataRDFReaderWriter(int)
0x18000b36c  lea     rax, ??_7CMetadataXMPStructReaderWriter@@6BIWICMetadataWriter@@@; const CMetadataXMPStructReaderWriter::`vftable'{for `IWICMetadataWriter'}
0x18000b373  mov     dword ptr [rdi+0F8h], 1
0x18000b37d  mov     [rdi], rax
0x18000b380  lea     rcx, CLSID_WICXMPStructMetadataReader
0x18000b387  lea     rax, ??_7CMetadataXMPBagReaderWriter@@6BIWICPersistStream@@@; const CMetadataXMPBagReaderWriter::`vftable'{for `IWICPersistStream'}
0x18000b38e  test    ebx, ebx
0x18000b390  mov     [rdi+8], rax
0x18000b394  lea     rax, ??_7CMetadataRDFReaderWriter@@6BIWICStreamProvider@@@; const CMetadataRDFReaderWriter::`vftable'{for `IWICStreamProvider'}
0x18000b39b  mov     [rdi+10h], rax
0x18000b39f  lea     rax, ??_7CMetadataXMPStructReaderWriter@@6BCMILCOMBase@@@; const CMetadataXMPStructReaderWriter::`vftable'{for `CMILCOMBase'}
0x18000b3a6  mov     [rdi+18h], rax
0x18000b3aa  lea     rax, ??_7CMetadataXMPStructReaderWriter@@6BCMTALock@@@; const CMetadataXMPStructReaderWriter::`vftable'{for `CMTALock'}
0x18000b3b1  mov     [rdi+28h], rax
0x18000b3b5  lea     rax, GUID_MetadataFormatXMPStruct
0x18000b3bc  mov     [rdi+98h], rax
0x18000b3c3  lea     rax, CLSID_WICXMPStructMetadataWriter
0x18000b3ca  cmovz   rax, rcx
0x18000b3ce  mov     [rdi+0A0h], rax
0x18000b3d5  mov     rax, rdi
0x18000b3d8  mov     rbx, [rsp+28h+arg_0]
0x18000b3dd  add     rsp, 20h
0x18000b3e1  pop     rdi
0x18000b3e2  retn
```
