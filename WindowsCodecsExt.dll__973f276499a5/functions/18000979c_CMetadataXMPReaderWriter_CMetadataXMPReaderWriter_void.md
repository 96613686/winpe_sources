# CMetadataXMPReaderWriter::~CMetadataXMPReaderWriter(void)

- ea: `0x18000979c`
- end: `0x180009862`
- name: `??1CMetadataXMPReaderWriter@@UEAA@XZ`
- size: `198`
- prototype: `void __fastcall(CMetadataXMPReaderWriter *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009760`

## callees

- `0x18000979c`
- `0x180009868`
- `0x1800098cc`
- `0x180033010`

## pseudocode

```c
void __fastcall CMetadataXMPReaderWriter::~CMetadataXMPReaderWriter(CMetadataXMPReaderWriter *this)
{
  unsigned int v1; // ebp
  char *v2; // rdi
  __int64 v3; // rsi
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  __int64 v6; // rcx

  v1 = *((_DWORD *)this + 72);
  *(_QWORD *)this = &CMetadataXMPReaderWriter::`vftable'{for `IWICMetadataWriter'};
  v2 = (char *)this + 264;
  v3 = 0;
  *((_QWORD *)this + 1) = &CMetadataXMPReaderWriter::`vftable'{for `IWICPersistStream'};
  *((_QWORD *)this + 2) = &CMetadataXMPReaderWriter::`vftable'{for `IWICStreamProvider'};
  *((_QWORD *)this + 3) = &CMetadataXMPReaderWriter::`vftable'{for `CMILCOMBase'};
  for ( *((_QWORD *)this + 5) = &CMetadataXMPReaderWriter::`vftable'{for `CMTALock'};
        (unsigned int)v3 < v1;
        v3 = (unsigned int)(v3 + 1) )
  {
    v5 = *(void (__fastcall ****)(_QWORD, __int64))(*(_QWORD *)v2 + 8 * v3);
    if ( v5 )
      (**v5)(v5, 1);
  }
  *((_DWORD *)v2 + 6) = 0;
  v6 = *((_QWORD *)this + 31);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 31) = 0;
  }
  *((_QWORD *)this + 32) = 0;
  CMILObjectArray<RDFItem *>::~CMILObjectArray<RDFItem *>(v2);
  CMetadataRDFReaderWriter::~CMetadataRDFReaderWriter(this);
}

```

## disassembly

```asm
0x18000979c  push    rbx
0x18000979e  push    rbp
0x18000979f  push    rsi
0x1800097a0  push    rdi
0x1800097a1  sub     rsp, 28h
0x1800097a5  mov     ebp, [rcx+120h]
0x1800097ab  lea     rax, ??_7CMetadataXMPReaderWriter@@6BIWICMetadataWriter@@@; const CMetadataXMPReaderWriter::`vftable'{for `IWICMetadataWriter'}
0x1800097b2  mov     [rcx], rax
0x1800097b5  lea     rdi, [rcx+108h]
0x1800097bc  lea     rax, ??_7CMetadataXMPReaderWriter@@6BIWICPersistStream@@@; const CMetadataXMPReaderWriter::`vftable'{for `IWICPersistStream'}
0x1800097c3  xor     esi, esi
0x1800097c5  mov     [rcx+8], rax
0x1800097c9  lea     rax, ??_7CMetadataXMPReaderWriter@@6BIWICStreamProvider@@@; const CMetadataXMPReaderWriter::`vftable'{for `IWICStreamProvider'}
0x1800097d0  mov     [rcx+10h], rax
0x1800097d4  lea     rax, ??_7CMetadataXMPReaderWriter@@6BCMILCOMBase@@@; const CMetadataXMPReaderWriter::`vftable'{for `CMILCOMBase'}
0x1800097db  mov     [rcx+18h], rax
0x1800097df  lea     rax, ??_7CMetadataXMPReaderWriter@@6BCMTALock@@@; const CMetadataXMPReaderWriter::`vftable'{for `CMTALock'}
0x1800097e6  mov     [rcx+28h], rax
0x1800097ea  mov     rbx, rcx
0x1800097ed  test    ebp, ebp
0x1800097ef  jz      short loc_180009813
0x1800097f1  mov     rax, [rdi]
0x1800097f4  mov     rcx, [rax+rsi*8]
0x1800097f8  test    rcx, rcx
0x1800097fb  jz      short loc_18000980D
0x1800097fd  mov     rax, [rcx]
0x180009800  mov     edx, 1
0x180009805  mov     rax, [rax]
0x180009808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000980d  inc     esi
0x18000980f  cmp     esi, ebp
0x180009811  jb      short loc_1800097F1
0x180009813  mov     dword ptr [rdi+18h], 0
0x18000981a  mov     rcx, [rbx+0F8h]
0x180009821  test    rcx, rcx
0x180009824  jnz     short loc_180009849
0x180009826  mov     qword ptr [rbx+100h], 0
0x180009831  mov     rcx, rdi
0x180009834  call    ??1?$CMILObjectArray@PEAVRDFItem@@@@QEAA@XZ; CMILObjectArray<RDFItem *>::~CMILObjectArray<RDFItem *>(void)
0x180009839  mov     rcx, rbx; this
0x18000983c  add     rsp, 28h
0x180009840  pop     rdi
0x180009841  pop     rsi
0x180009842  pop     rbp
0x180009843  pop     rbx
0x180009844  jmp     ??1CMetadataRDFReaderWriter@@UEAA@XZ; CMetadataRDFReaderWriter::~CMetadataRDFReaderWriter(void)
0x180009849  mov     rax, [rcx]
0x18000984c  mov     rax, [rax+10h]
0x180009850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009855  mov     qword ptr [rbx+0F8h], 0
0x180009860  jmp     short loc_180009826
```
