# CreateXMPReader(void)

- ea: `0x180009a60`
- end: `0x180009b30`
- name: `?CreateXMPReader@@YAPEAUIUnknown@@XZ`
- size: `208`
- prototype: `struct IUnknown *(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800093c0`
- `0x180009a60`
- `0x1800215e8`

## pseudocode

```c
struct IUnknown *CreateXMPReader(void)
{
  CMetadataRDFReaderWriter *v0; // rax
  CMetadataRDFReaderWriter *v1; // rbx

  v0 = (CMetadataRDFReaderWriter *)operator new(0x128u);
  v1 = v0;
  if ( v0 )
  {
    CMetadataRDFReaderWriter::CMetadataRDFReaderWriter(v0, 0);
    *(_QWORD *)v1 = &CMetadataXMPReaderWriter::`vftable'{for `IWICMetadataWriter'};
    *((_QWORD *)v1 + 1) = &CMetadataXMPReaderWriter::`vftable'{for `IWICPersistStream'};
    *((_QWORD *)v1 + 2) = &CMetadataXMPReaderWriter::`vftable'{for `IWICStreamProvider'};
    *((_QWORD *)v1 + 3) = &CMetadataXMPReaderWriter::`vftable'{for `CMILCOMBase'};
    *((_QWORD *)v1 + 5) = &CMetadataXMPReaderWriter::`vftable'{for `CMTALock'};
    *((_QWORD *)v1 + 33) = 0;
    *((_QWORD *)v1 + 34) = 0;
    *((_QWORD *)v1 + 35) = 0;
    *((_DWORD *)v1 + 72) = 0;
    *((_QWORD *)v1 + 19) = &GUID_MetadataFormatXMP;
    *((_QWORD *)v1 + 20) = &CLSID_WICXMPMetadataReader;
    *((_QWORD *)v1 + 31) = 0;
    *((_QWORD *)v1 + 32) = 0;
  }
  else
  {
    v1 = 0;
  }
  return (struct IUnknown *)(((unsigned __int64)v1 + 24) & -(__int64)(v1 != 0));
}

```

## disassembly

```asm
0x180009a60  push    rbx
0x180009a62  sub     rsp, 20h
0x180009a66  mov     ecx, 128h; Size
0x180009a6b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009a70  mov     rbx, rax
0x180009a73  test    rax, rax
0x180009a76  jz      loc_180009B2C
0x180009a7c  xor     edx, edx; int
0x180009a7e  mov     rcx, rax; this
0x180009a81  call    ??0CMetadataRDFReaderWriter@@QEAA@H@Z; CMetadataRDFReaderWriter::CMetadataRDFReaderWriter(int)
0x180009a86  lea     rax, ??_7CMetadataXMPReaderWriter@@6BIWICMetadataWriter@@@; const CMetadataXMPReaderWriter::`vftable'{for `IWICMetadataWriter'}
0x180009a8d  mov     [rbx], rax
0x180009a90  lea     rax, ??_7CMetadataXMPReaderWriter@@6BIWICPersistStream@@@; const CMetadataXMPReaderWriter::`vftable'{for `IWICPersistStream'}
0x180009a97  mov     [rbx+8], rax
0x180009a9b  lea     rax, ??_7CMetadataXMPReaderWriter@@6BIWICStreamProvider@@@; const CMetadataXMPReaderWriter::`vftable'{for `IWICStreamProvider'}
0x180009aa2  mov     [rbx+10h], rax
0x180009aa6  lea     rax, ??_7CMetadataXMPReaderWriter@@6BCMILCOMBase@@@; const CMetadataXMPReaderWriter::`vftable'{for `CMILCOMBase'}
0x180009aad  mov     [rbx+18h], rax
0x180009ab1  lea     rax, ??_7CMetadataXMPReaderWriter@@6BCMTALock@@@; const CMetadataXMPReaderWriter::`vftable'{for `CMTALock'}
0x180009ab8  mov     [rbx+28h], rax
0x180009abc  lea     rax, GUID_MetadataFormatXMP
0x180009ac3  mov     qword ptr [rbx+108h], 0
0x180009ace  mov     qword ptr [rbx+110h], 0
0x180009ad9  mov     qword ptr [rbx+118h], 0
0x180009ae4  mov     dword ptr [rbx+120h], 0
0x180009aee  mov     [rbx+98h], rax
0x180009af5  lea     rax, CLSID_WICXMPMetadataReader
0x180009afc  mov     [rbx+0A0h], rax
0x180009b03  mov     qword ptr [rbx+0F8h], 0
0x180009b0e  mov     qword ptr [rbx+100h], 0
0x180009b19  lea     rcx, [rbx+18h]
0x180009b1d  neg     rbx
0x180009b20  sbb     rax, rax
0x180009b23  and     rax, rcx
0x180009b26  add     rsp, 20h
0x180009b2a  pop     rbx
0x180009b2b  retn
0x180009b2c  xor     ebx, ebx
0x180009b2e  jmp     short loc_180009B19
```
