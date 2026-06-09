# C1in1outDMO::~C1in1outDMO(void)

- ea: `0x180002718`
- end: `0x180002793`
- name: `??1C1in1outDMO@@QEAA@XZ`
- size: `123`
- prototype: `void __fastcall(C1in1outDMO *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002634`

## callees

- `0x180002718`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000273d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000273d`
- `msdmo!MoFreeMediaType` at `0x18000274d`
- `msdmo!MoFreeMediaType` at `0x180002760`
- `msdmo!MoFreeMediaType` at `0x18000274d`
- `msdmo!MoFreeMediaType` at `0x180002760`

## pseudocode

```c
void __fastcall C1in1outDMO::~C1in1outDMO(C1in1outDMO *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CSecureDMO<CWMDSPDMOWMILoggingBase<C1in1outDMO>>::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'};
  *((_QWORD *)this + 6) = &C1in1outDMO::`vftable'{for `IMediaObject'};
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 248));
  if ( *((_DWORD *)this + 14) )
    MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 64));
  if ( *((_DWORD *)this + 15) )
    MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 152));
  v2 = *((_QWORD *)this + 4);
  *(_QWORD *)this = &CMFTtoDMOImpl<CMFTtoDMO>::`vftable';
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 4) = 0;
  }
}

```

## disassembly

```asm
0x180002718  push    rbx
0x18000271a  sub     rsp, 20h
0x18000271e  lea     rax, ??_7?$CSecureDMO@V?$CWMDSPDMOWMILoggingBase@VC1in1outDMO@@@@@@6B?$CMFTtoDMOImpl@VCMFTtoDMO@@@@@; const CSecureDMO<CWMDSPDMOWMILoggingBase<C1in1outDMO>>::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'}
0x180002725  mov     rbx, rcx
0x180002728  mov     [rcx], rax
0x18000272b  lea     rax, ??_7C1in1outDMO@@6BIMediaObject@@@; const C1in1outDMO::`vftable'{for `IMediaObject'}
0x180002732  mov     [rcx+30h], rax
0x180002736  add     rcx, 0F8h; lpCriticalSection
0x18000273d  call    cs:__imp_DeleteCriticalSection
0x180002743  cmp     dword ptr [rbx+38h], 0
0x180002747  jz      short loc_180002753
0x180002749  lea     rcx, [rbx+40h]; pmt
0x18000274d  call    cs:__imp_MoFreeMediaType
0x180002753  cmp     dword ptr [rbx+3Ch], 0
0x180002757  jz      short loc_180002766
0x180002759  lea     rcx, [rbx+98h]; pmt
0x180002760  call    cs:__imp_MoFreeMediaType
0x180002766  mov     rcx, [rbx+20h]
0x18000276a  lea     rax, ??_7?$CMFTtoDMOImpl@VCMFTtoDMO@@@@6B@; const CMFTtoDMOImpl<CMFTtoDMO>::`vftable'
0x180002771  mov     [rbx], rax
0x180002774  test    rcx, rcx
0x180002777  jz      short loc_18000278D
0x180002779  mov     rax, [rcx]
0x18000277c  mov     rax, [rax+10h]
0x180002780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002785  mov     qword ptr [rbx+20h], 0
0x18000278d  add     rsp, 20h
0x180002791  pop     rbx
0x180002792  retn
```
