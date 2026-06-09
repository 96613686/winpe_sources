# CMetadataXMPSeqReaderWriter::CMetadataXMPSeqReaderWriter(int)

- ea: `0x180023200`
- end: `0x180023281`
- name: `??0CMetadataXMPSeqReaderWriter@@QEAA@H@Z`
- size: `129`
- prototype: `CMetadataXMPSeqReaderWriter *__fastcall(CMetadataXMPSeqReaderWriter *__hidden this, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800232b0`
- `0x1800232f0`

## callees

- `0x1800142e0`

## pseudocode

```c
CMetadataXMPSeqReaderWriter *__fastcall CMetadataXMPSeqReaderWriter::CMetadataXMPSeqReaderWriter(
        CMetadataXMPSeqReaderWriter *this,
        int a2)
{
  GUID *v4; // rax

  CMetadataRDFIndexReaderWriter::CMetadataRDFIndexReaderWriter(this, a2);
  *(_QWORD *)this = &CMetadataXMPSeqReaderWriter::`vftable'{for `IWICMetadataWriter'};
  *((_QWORD *)this + 1) = &CMetadataXMPBagReaderWriter::`vftable'{for `IWICPersistStream'};
  *((_QWORD *)this + 2) = &CMetadataRDFReaderWriter::`vftable'{for `IWICStreamProvider'};
  *((_QWORD *)this + 3) = &CMetadataXMPBagReaderWriter::`vftable'{for `CMILCOMBase'};
  *((_QWORD *)this + 5) = &CMetadataRDFIndexReaderWriter::`vftable'{for `CMTALock'};
  *((_QWORD *)this + 19) = &GUID_MetadataFormatXMPSeq;
  v4 = &CLSID_WICXMPSeqMetadataWriter;
  if ( !a2 )
    v4 = &CLSID_WICXMPSeqMetadataReader;
  *((_QWORD *)this + 20) = v4;
  return this;
}

```

## disassembly

```asm
0x180023200  mov     [rsp+arg_0], rbx
0x180023205  push    rdi
0x180023206  sub     rsp, 20h
0x18002320a  mov     ebx, edx
0x18002320c  mov     rdi, rcx
0x18002320f  call    ??0CMetadataRDFIndexReaderWriter@@QEAA@H@Z; CMetadataRDFIndexReaderWriter::CMetadataRDFIndexReaderWriter(int)
0x180023214  lea     rax, ??_7CMetadataXMPSeqReaderWriter@@6BIWICMetadataWriter@@@; const CMetadataXMPSeqReaderWriter::`vftable'{for `IWICMetadataWriter'}
0x18002321b  test    ebx, ebx
0x18002321d  mov     [rdi], rax
0x180023220  lea     rcx, CLSID_WICXMPSeqMetadataReader
0x180023227  lea     rax, ??_7CMetadataXMPBagReaderWriter@@6BIWICPersistStream@@@; const CMetadataXMPBagReaderWriter::`vftable'{for `IWICPersistStream'}
0x18002322e  mov     [rdi+8], rax
0x180023232  lea     rax, ??_7CMetadataRDFReaderWriter@@6BIWICStreamProvider@@@; const CMetadataRDFReaderWriter::`vftable'{for `IWICStreamProvider'}
0x180023239  mov     [rdi+10h], rax
0x18002323d  lea     rax, ??_7CMetadataXMPBagReaderWriter@@6BCMILCOMBase@@@; const CMetadataXMPBagReaderWriter::`vftable'{for `CMILCOMBase'}
0x180023244  mov     [rdi+18h], rax
0x180023248  lea     rax, ??_7CMetadataRDFIndexReaderWriter@@6BCMTALock@@@; const CMetadataRDFIndexReaderWriter::`vftable'{for `CMTALock'}
0x18002324f  mov     [rdi+28h], rax
0x180023253  lea     rax, GUID_MetadataFormatXMPSeq
0x18002325a  mov     [rdi+98h], rax
0x180023261  lea     rax, CLSID_WICXMPSeqMetadataWriter
0x180023268  cmovz   rax, rcx
0x18002326c  mov     [rdi+0A0h], rax
0x180023273  mov     rax, rdi
0x180023276  mov     rbx, [rsp+28h+arg_0]
0x18002327b  add     rsp, 20h
0x18002327f  pop     rdi
0x180023280  retn
```
