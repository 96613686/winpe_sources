# CMetadataXMPBagReaderWriter::CMetadataXMPBagReaderWriter(int)

- ea: `0x180014258`
- end: `0x1800142d9`
- name: `??0CMetadataXMPBagReaderWriter@@QEAA@H@Z`
- size: `129`
- prototype: `CMetadataXMPBagReaderWriter *__fastcall(CMetadataXMPBagReaderWriter *__hidden this, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014220`
- `0x180023340`

## callees

- `0x1800142e0`

## pseudocode

```c
CMetadataXMPBagReaderWriter *__fastcall CMetadataXMPBagReaderWriter::CMetadataXMPBagReaderWriter(
        CMetadataXMPBagReaderWriter *this,
        int a2)
{
  GUID *v4; // rax

  CMetadataRDFIndexReaderWriter::CMetadataRDFIndexReaderWriter(this, a2);
  *(_QWORD *)this = &CMetadataXMPBagReaderWriter::`vftable'{for `IWICMetadataWriter'};
  *((_QWORD *)this + 1) = &CMetadataXMPBagReaderWriter::`vftable'{for `IWICPersistStream'};
  *((_QWORD *)this + 2) = &CMetadataRDFReaderWriter::`vftable'{for `IWICStreamProvider'};
  *((_QWORD *)this + 3) = &CMetadataXMPBagReaderWriter::`vftable'{for `CMILCOMBase'};
  *((_QWORD *)this + 5) = &CMetadataRDFIndexReaderWriter::`vftable'{for `CMTALock'};
  *((_QWORD *)this + 19) = &GUID_MetadataFormatXMPBag;
  v4 = &CLSID_WICXMPBagMetadataWriter;
  if ( !a2 )
    v4 = &CLSID_WICXMPBagMetadataReader;
  *((_QWORD *)this + 20) = v4;
  return this;
}

```

## disassembly

```asm
0x180014258  mov     [rsp+arg_0], rbx
0x18001425d  push    rdi
0x18001425e  sub     rsp, 20h
0x180014262  mov     ebx, edx
0x180014264  mov     rdi, rcx
0x180014267  call    ??0CMetadataRDFIndexReaderWriter@@QEAA@H@Z; CMetadataRDFIndexReaderWriter::CMetadataRDFIndexReaderWriter(int)
0x18001426c  lea     rax, ??_7CMetadataXMPBagReaderWriter@@6BIWICMetadataWriter@@@; const CMetadataXMPBagReaderWriter::`vftable'{for `IWICMetadataWriter'}
0x180014273  test    ebx, ebx
0x180014275  mov     [rdi], rax
0x180014278  lea     rcx, CLSID_WICXMPBagMetadataReader
0x18001427f  lea     rax, ??_7CMetadataXMPBagReaderWriter@@6BIWICPersistStream@@@; const CMetadataXMPBagReaderWriter::`vftable'{for `IWICPersistStream'}
0x180014286  mov     [rdi+8], rax
0x18001428a  lea     rax, ??_7CMetadataRDFReaderWriter@@6BIWICStreamProvider@@@; const CMetadataRDFReaderWriter::`vftable'{for `IWICStreamProvider'}
0x180014291  mov     [rdi+10h], rax
0x180014295  lea     rax, ??_7CMetadataXMPBagReaderWriter@@6BCMILCOMBase@@@; const CMetadataXMPBagReaderWriter::`vftable'{for `CMILCOMBase'}
0x18001429c  mov     [rdi+18h], rax
0x1800142a0  lea     rax, ??_7CMetadataRDFIndexReaderWriter@@6BCMTALock@@@; const CMetadataRDFIndexReaderWriter::`vftable'{for `CMTALock'}
0x1800142a7  mov     [rdi+28h], rax
0x1800142ab  lea     rax, GUID_MetadataFormatXMPBag
0x1800142b2  mov     [rdi+98h], rax
0x1800142b9  lea     rax, CLSID_WICXMPBagMetadataWriter
0x1800142c0  cmovz   rax, rcx
0x1800142c4  mov     [rdi+0A0h], rax
0x1800142cb  mov     rax, rdi
0x1800142ce  mov     rbx, [rsp+28h+arg_0]
0x1800142d3  add     rsp, 20h
0x1800142d7  pop     rdi
0x1800142d8  retn
```
