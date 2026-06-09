# C1in1outDMO::~C1in1outDMO(void)

- ea: `0x1800027d4`
- end: `0x18000284f`
- name: `??1C1in1outDMO@@QEAA@XZ`
- size: `123`
- prototype: `void __fastcall(C1in1outDMO *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800026f0`

## callees

- `0x1800027d4`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800027f9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800027f9`
- `msdmo!MoFreeMediaType` at `0x180002809`
- `msdmo!MoFreeMediaType` at `0x18000281c`
- `msdmo!MoFreeMediaType` at `0x180002809`
- `msdmo!MoFreeMediaType` at `0x18000281c`

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
0x1800027d4  push    rbx
0x1800027d6  sub     rsp, 20h
0x1800027da  lea     rax, ??_7?$CSecureDMO@V?$CWMDSPDMOWMILoggingBase@VC1in1outDMO@@@@@@6B?$CMFTtoDMOImpl@VCMFTtoDMO@@@@@; const CSecureDMO<CWMDSPDMOWMILoggingBase<C1in1outDMO>>::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'}
0x1800027e1  mov     rbx, rcx
0x1800027e4  mov     [rcx], rax
0x1800027e7  lea     rax, ??_7C1in1outDMO@@6BIMediaObject@@@; const C1in1outDMO::`vftable'{for `IMediaObject'}
0x1800027ee  mov     [rcx+30h], rax
0x1800027f2  add     rcx, 0F8h; lpCriticalSection
0x1800027f9  call    cs:__imp_DeleteCriticalSection
0x1800027ff  cmp     dword ptr [rbx+38h], 0
0x180002803  jz      short loc_18000280F
0x180002805  lea     rcx, [rbx+40h]; pmt
0x180002809  call    cs:__imp_MoFreeMediaType
0x18000280f  cmp     dword ptr [rbx+3Ch], 0
0x180002813  jz      short loc_180002822
0x180002815  lea     rcx, [rbx+98h]; pmt
0x18000281c  call    cs:__imp_MoFreeMediaType
0x180002822  mov     rcx, [rbx+20h]
0x180002826  lea     rax, ??_7?$CMFTtoDMOImpl@VCMFTtoDMO@@@@6B@; const CMFTtoDMOImpl<CMFTtoDMO>::`vftable'
0x18000282d  mov     [rbx], rax
0x180002830  test    rcx, rcx
0x180002833  jz      short loc_180002849
0x180002835  mov     rax, [rcx]
0x180002838  mov     rax, [rax+10h]
0x18000283c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002841  mov     qword ptr [rbx+20h], 0
0x180002849  add     rsp, 20h
0x18000284d  pop     rbx
0x18000284e  retn
```
