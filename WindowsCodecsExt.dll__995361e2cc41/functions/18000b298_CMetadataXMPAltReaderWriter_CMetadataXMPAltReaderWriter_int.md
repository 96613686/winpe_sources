# CMetadataXMPAltReaderWriter::CMetadataXMPAltReaderWriter(int)

- ea: `0x18000b298`
- end: `0x18000b323`
- name: `??0CMetadataXMPAltReaderWriter@@QEAA@H@Z`
- size: `139`
- prototype: `CMetadataXMPAltReaderWriter *__fastcall(CMetadataXMPAltReaderWriter *__hidden this, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b5b0`
- `0x180023050`

## callees

- `0x1800093c0`

## pseudocode

```c
CMetadataXMPAltReaderWriter *__fastcall CMetadataXMPAltReaderWriter::CMetadataXMPAltReaderWriter(
        CMetadataXMPAltReaderWriter *this,
        int a2)
{
  GUID *v4; // rax
  CMetadataXMPAltReaderWriter *result; // rax

  CMetadataRDFReaderWriter::CMetadataRDFReaderWriter(this, a2);
  *(_QWORD *)this = &CMetadataXMPAltReaderWriter::`vftable'{for `IWICMetadataWriter'};
  *((_QWORD *)this + 1) = &CMetadataXMPBagReaderWriter::`vftable'{for `IWICPersistStream'};
  *((_QWORD *)this + 2) = &CMetadataRDFReaderWriter::`vftable'{for `IWICStreamProvider'};
  *((_QWORD *)this + 3) = &CMetadataXMPAltReaderWriter::`vftable'{for `CMILCOMBase'};
  *((_QWORD *)this + 5) = &CMetadataXMPAltReaderWriter::`vftable'{for `CMTALock'};
  *((_QWORD *)this + 19) = &GUID_MetadataFormatXMPAlt;
  v4 = &CLSID_WICXMPAltMetadataWriter;
  if ( !a2 )
    v4 = &CLSID_WICXMPAltMetadataReader;
  *((_QWORD *)this + 20) = v4;
  result = this;
  *((_DWORD *)this + 62) = 0;
  return result;
}

```

## disassembly

```asm
0x18000b298  mov     [rsp+arg_0], rbx
0x18000b29d  push    rdi
0x18000b29e  sub     rsp, 20h
0x18000b2a2  mov     ebx, edx
0x18000b2a4  mov     rdi, rcx
0x18000b2a7  call    ??0CMetadataRDFReaderWriter@@QEAA@H@Z; CMetadataRDFReaderWriter::CMetadataRDFReaderWriter(int)
0x18000b2ac  lea     rax, ??_7CMetadataXMPAltReaderWriter@@6BIWICMetadataWriter@@@; const CMetadataXMPAltReaderWriter::`vftable'{for `IWICMetadataWriter'}
0x18000b2b3  test    ebx, ebx
0x18000b2b5  mov     [rdi], rax
0x18000b2b8  lea     rcx, CLSID_WICXMPAltMetadataReader
0x18000b2bf  lea     rax, ??_7CMetadataXMPBagReaderWriter@@6BIWICPersistStream@@@; const CMetadataXMPBagReaderWriter::`vftable'{for `IWICPersistStream'}
0x18000b2c6  mov     [rdi+8], rax
0x18000b2ca  lea     rax, ??_7CMetadataRDFReaderWriter@@6BIWICStreamProvider@@@; const CMetadataRDFReaderWriter::`vftable'{for `IWICStreamProvider'}
0x18000b2d1  mov     [rdi+10h], rax
0x18000b2d5  lea     rax, ??_7CMetadataXMPAltReaderWriter@@6BCMILCOMBase@@@; const CMetadataXMPAltReaderWriter::`vftable'{for `CMILCOMBase'}
0x18000b2dc  mov     [rdi+18h], rax
0x18000b2e0  lea     rax, ??_7CMetadataXMPAltReaderWriter@@6BCMTALock@@@; const CMetadataXMPAltReaderWriter::`vftable'{for `CMTALock'}
0x18000b2e7  mov     [rdi+28h], rax
0x18000b2eb  lea     rax, GUID_MetadataFormatXMPAlt
0x18000b2f2  mov     [rdi+98h], rax
0x18000b2f9  lea     rax, CLSID_WICXMPAltMetadataWriter
0x18000b300  cmovz   rax, rcx
0x18000b304  mov     [rdi+0A0h], rax
0x18000b30b  mov     rax, rdi
0x18000b30e  mov     rbx, [rsp+28h+arg_0]
0x18000b313  mov     dword ptr [rdi+0F8h], 0
0x18000b31d  add     rsp, 20h
0x18000b321  pop     rdi
0x18000b322  retn
```
