# CMetadataXMPReaderWriter::CMetadataXMPReaderWriter(int)

- ea: `0x18000930c`
- end: `0x1800093b8`
- name: `??0CMetadataXMPReaderWriter@@QEAA@H@Z`
- size: `172`
- prototype: `CMetadataXMPReaderWriter *__fastcall(CMetadataXMPReaderWriter *__hidden this, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022a20`

## callees

- `0x1800093c0`

## pseudocode

```c
CMetadataXMPReaderWriter *__fastcall CMetadataXMPReaderWriter::CMetadataXMPReaderWriter(
        CMetadataXMPReaderWriter *this,
        int a2)
{
  GUID *v4; // rax
  CMetadataXMPReaderWriter *result; // rax

  CMetadataRDFReaderWriter::CMetadataRDFReaderWriter(this, a2);
  *(_QWORD *)this = &CMetadataXMPReaderWriter::`vftable'{for `IWICMetadataWriter'};
  *((_QWORD *)this + 1) = &CMetadataXMPReaderWriter::`vftable'{for `IWICPersistStream'};
  *((_QWORD *)this + 2) = &CMetadataXMPReaderWriter::`vftable'{for `IWICStreamProvider'};
  *((_QWORD *)this + 3) = &CMetadataXMPReaderWriter::`vftable'{for `CMILCOMBase'};
  *((_QWORD *)this + 5) = &CMetadataXMPReaderWriter::`vftable'{for `CMTALock'};
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_DWORD *)this + 72) = 0;
  *((_QWORD *)this + 19) = &GUID_MetadataFormatXMP;
  v4 = &CLSID_WICXMPMetadataWriter;
  if ( !a2 )
    v4 = &CLSID_WICXMPMetadataReader;
  *((_QWORD *)this + 20) = v4;
  result = this;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  return result;
}

```

## disassembly

```asm
0x18000930c  mov     [rsp+arg_0], rbx
0x180009311  push    rdi
0x180009312  sub     rsp, 20h
0x180009316  mov     ebx, edx
0x180009318  mov     rdi, rcx
0x18000931b  call    ??0CMetadataRDFReaderWriter@@QEAA@H@Z; CMetadataRDFReaderWriter::CMetadataRDFReaderWriter(int)
0x180009320  xor     edx, edx
0x180009322  lea     rax, ??_7CMetadataXMPReaderWriter@@6BIWICMetadataWriter@@@; const CMetadataXMPReaderWriter::`vftable'{for `IWICMetadataWriter'}
0x180009329  mov     [rdi], rax
0x18000932c  lea     rcx, CLSID_WICXMPMetadataReader
0x180009333  lea     rax, ??_7CMetadataXMPReaderWriter@@6BIWICPersistStream@@@; const CMetadataXMPReaderWriter::`vftable'{for `IWICPersistStream'}
0x18000933a  test    ebx, ebx
0x18000933c  mov     [rdi+8], rax
0x180009340  lea     rax, ??_7CMetadataXMPReaderWriter@@6BIWICStreamProvider@@@; const CMetadataXMPReaderWriter::`vftable'{for `IWICStreamProvider'}
0x180009347  mov     [rdi+10h], rax
0x18000934b  lea     rax, ??_7CMetadataXMPReaderWriter@@6BCMILCOMBase@@@; const CMetadataXMPReaderWriter::`vftable'{for `CMILCOMBase'}
0x180009352  mov     [rdi+18h], rax
0x180009356  lea     rax, ??_7CMetadataXMPReaderWriter@@6BCMTALock@@@; const CMetadataXMPReaderWriter::`vftable'{for `CMTALock'}
0x18000935d  mov     [rdi+28h], rax
0x180009361  lea     rax, GUID_MetadataFormatXMP
0x180009368  mov     [rdi+108h], rdx
0x18000936f  mov     [rdi+110h], rdx
0x180009376  mov     [rdi+118h], rdx
0x18000937d  mov     [rdi+120h], edx
0x180009383  mov     [rdi+98h], rax
0x18000938a  lea     rax, CLSID_WICXMPMetadataWriter
0x180009391  cmovz   rax, rcx
0x180009395  mov     [rdi+0A0h], rax
0x18000939c  mov     rax, rdi
0x18000939f  mov     rbx, [rsp+28h+arg_0]
0x1800093a4  mov     [rdi+0F8h], rdx
0x1800093ab  mov     [rdi+100h], rdx
0x1800093b2  add     rsp, 20h
0x1800093b6  pop     rdi
0x1800093b7  retn
```
