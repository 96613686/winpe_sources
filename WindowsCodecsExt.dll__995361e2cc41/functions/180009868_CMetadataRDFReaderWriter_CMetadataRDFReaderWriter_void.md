# CMetadataRDFReaderWriter::~CMetadataRDFReaderWriter(void)

- ea: `0x180009868`
- end: `0x1800098c5`
- name: `??1CMetadataRDFReaderWriter@@UEAA@XZ`
- size: `93`
- prototype: `void __fastcall(CMetadataRDFReaderWriter *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000979c`
- `0x18000b42c`
- `0x18000b4d8`
- `0x18000b514`
- `0x180023430`

## callees

- `0x1800098cc`
- `0x1800098fc`
- `0x180009990`

## pseudocode

```c
void __fastcall CMetadataRDFReaderWriter::~CMetadataRDFReaderWriter(CMetadataRDFReaderWriter *this)
{
  *(_QWORD *)this = &CMetadataRDFReaderWriter::`vftable'{for `IWICMetadataWriter'};
  *((_QWORD *)this + 1) = &CMetadataXMPBagReaderWriter::`vftable'{for `IWICPersistStream'};
  *((_QWORD *)this + 2) = &CMetadataRDFReaderWriter::`vftable'{for `IWICStreamProvider'};
  *((_QWORD *)this + 3) = &CMetadataRDFReaderWriter::`vftable'{for `CMILCOMBase'};
  *((_QWORD *)this + 5) = &CMetadataRDFReaderWriter::`vftable'{for `CMTALock'};
  CMetadataRDFReaderWriter::ClearFields(this);
  CMILObjectArray<RDFItem *>::~CMILObjectArray<RDFItem *>((char *)this + 208);
  CMetadataHandler::~CMetadataHandler(this);
}

```

## disassembly

```asm
0x180009868  push    rbx
0x18000986a  sub     rsp, 20h
0x18000986e  lea     rax, ??_7CMetadataRDFReaderWriter@@6BIWICMetadataWriter@@@; const CMetadataRDFReaderWriter::`vftable'{for `IWICMetadataWriter'}
0x180009875  mov     rbx, rcx
0x180009878  mov     [rcx], rax
0x18000987b  lea     rax, ??_7CMetadataXMPBagReaderWriter@@6BIWICPersistStream@@@; const CMetadataXMPBagReaderWriter::`vftable'{for `IWICPersistStream'}
0x180009882  mov     [rcx+8], rax
0x180009886  lea     rax, ??_7CMetadataRDFReaderWriter@@6BIWICStreamProvider@@@; const CMetadataRDFReaderWriter::`vftable'{for `IWICStreamProvider'}
0x18000988d  mov     [rcx+10h], rax
0x180009891  lea     rax, ??_7CMetadataRDFReaderWriter@@6BCMILCOMBase@@@; const CMetadataRDFReaderWriter::`vftable'{for `CMILCOMBase'}
0x180009898  mov     [rcx+18h], rax
0x18000989c  lea     rax, ??_7CMetadataRDFReaderWriter@@6BCMTALock@@@; const CMetadataRDFReaderWriter::`vftable'{for `CMTALock'}
0x1800098a3  mov     [rcx+28h], rax
0x1800098a7  call    ?ClearFields@CMetadataRDFReaderWriter@@MEAAJXZ; CMetadataRDFReaderWriter::ClearFields(void)
0x1800098ac  lea     rcx, [rbx+0D0h]
0x1800098b3  call    ??1?$CMILObjectArray@PEAVRDFItem@@@@QEAA@XZ; CMILObjectArray<RDFItem *>::~CMILObjectArray<RDFItem *>(void)
0x1800098b8  mov     rcx, rbx; this
0x1800098bb  add     rsp, 20h
0x1800098bf  pop     rbx
0x1800098c0  jmp     ??1CMetadataHandler@@UEAA@XZ; CMetadataHandler::~CMetadataHandler(void)
```
