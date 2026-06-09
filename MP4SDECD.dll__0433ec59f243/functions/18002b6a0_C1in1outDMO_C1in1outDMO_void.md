# C1in1outDMO::~C1in1outDMO(void)

- ea: `0x18002b6a0`
- end: `0x18002b6fb`
- name: `??1C1in1outDMO@@QEAA@XZ`
- size: `91`
- prototype: `void __fastcall(C1in1outDMO *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002b620`

## callees

- `0x18002b5e4`
- `0x18002b6a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b6c5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b6c5`
- `msdmo!MoFreeMediaType` at `0x18002b6d5`
- `msdmo!MoFreeMediaType` at `0x18002b6e8`
- `msdmo!MoFreeMediaType` at `0x18002b6d5`
- `msdmo!MoFreeMediaType` at `0x18002b6e8`

## pseudocode

```c
void __fastcall C1in1outDMO::~C1in1outDMO(C1in1outDMO *this)
{
  *(_QWORD *)this = &CSecureDMO<CWMDSPDMOWMILoggingBase<C1in1outDMO>>::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'};
  *((_QWORD *)this + 6) = &C1in1outDMO::`vftable'{for `IMediaObject'};
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  if ( *((_DWORD *)this + 14) )
    MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 64));
  if ( *((_DWORD *)this + 15) )
    MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 152));
  CMFTtoDMOImpl<CMFTtoDMO>::~CMFTtoDMOImpl<CMFTtoDMO>(this);
}

```

## disassembly

```asm
0x18002b6a0  push    rbx
0x18002b6a2  sub     rsp, 20h
0x18002b6a6  lea     rax, ??_7?$CSecureDMO@V?$CWMDSPDMOWMILoggingBase@VC1in1outDMO@@@@@@6B?$CMFTtoDMOImpl@VCMFTtoDMO@@@@@; const CSecureDMO<CWMDSPDMOWMILoggingBase<C1in1outDMO>>::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'}
0x18002b6ad  mov     rbx, rcx
0x18002b6b0  mov     [rcx], rax
0x18002b6b3  lea     rax, ??_7C1in1outDMO@@6BIMediaObject@@@; const C1in1outDMO::`vftable'{for `IMediaObject'}
0x18002b6ba  mov     [rcx+30h], rax
0x18002b6be  add     rcx, 108h; lpCriticalSection
0x18002b6c5  call    cs:__imp_DeleteCriticalSection
0x18002b6cb  cmp     dword ptr [rbx+38h], 0
0x18002b6cf  jz      short loc_18002B6DB
0x18002b6d1  lea     rcx, [rbx+40h]; pmt
0x18002b6d5  call    cs:__imp_MoFreeMediaType
0x18002b6db  cmp     dword ptr [rbx+3Ch], 0
0x18002b6df  jz      short loc_18002B6EE
0x18002b6e1  lea     rcx, [rbx+98h]; pmt
0x18002b6e8  call    cs:__imp_MoFreeMediaType
0x18002b6ee  mov     rcx, rbx
0x18002b6f1  add     rsp, 20h
0x18002b6f5  pop     rbx
0x18002b6f6  jmp     ??1?$CMFTtoDMOImpl@VCMFTtoDMO@@@@QEAA@XZ; CMFTtoDMOImpl<CMFTtoDMO>::~CMFTtoDMOImpl<CMFTtoDMO>(void)
```
