# C1in1outDMO::~C1in1outDMO(void)

- ea: `0x18000df1c`
- end: `0x18000df77`
- name: `??1C1in1outDMO@@QEAA@XZ`
- size: `91`
- prototype: `void __fastcall(C1in1outDMO *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bf78`

## callees

- `0x18000df1c`
- `0x18000df80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000df41`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000df41`
- `msdmo!MoFreeMediaType` at `0x18000df51`
- `msdmo!MoFreeMediaType` at `0x18000df64`
- `msdmo!MoFreeMediaType` at `0x18000df51`
- `msdmo!MoFreeMediaType` at `0x18000df64`

## pseudocode

```c
void __fastcall C1in1outDMO::~C1in1outDMO(C1in1outDMO *this)
{
  *(_QWORD *)this = &C1in1outDMO::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'};
  *((_QWORD *)this + 6) = &C1in1outDMO::`vftable'{for `IMediaObject'};
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 248));
  if ( *((_DWORD *)this + 14) )
    MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 64));
  if ( *((_DWORD *)this + 15) )
    MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 152));
  CMFTtoDMOImpl<CMFTtoDMO>::~CMFTtoDMOImpl<CMFTtoDMO>(this);
}

```

## disassembly

```asm
0x18000df1c  push    rbx
0x18000df1e  sub     rsp, 20h
0x18000df22  lea     rax, ??_7C1in1outDMO@@6B?$CMFTtoDMOImpl@VCMFTtoDMO@@@@@; const C1in1outDMO::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'}
0x18000df29  mov     rbx, rcx
0x18000df2c  mov     [rcx], rax
0x18000df2f  lea     rax, ??_7C1in1outDMO@@6BIMediaObject@@@; const C1in1outDMO::`vftable'{for `IMediaObject'}
0x18000df36  mov     [rcx+30h], rax
0x18000df3a  add     rcx, 0F8h; lpCriticalSection
0x18000df41  call    cs:__imp_DeleteCriticalSection
0x18000df47  cmp     dword ptr [rbx+38h], 0
0x18000df4b  jz      short loc_18000DF57
0x18000df4d  lea     rcx, [rbx+40h]; pmt
0x18000df51  call    cs:__imp_MoFreeMediaType
0x18000df57  cmp     dword ptr [rbx+3Ch], 0
0x18000df5b  jz      short loc_18000DF6A
0x18000df5d  lea     rcx, [rbx+98h]; pmt
0x18000df64  call    cs:__imp_MoFreeMediaType
0x18000df6a  mov     rcx, rbx
0x18000df6d  add     rsp, 20h
0x18000df71  pop     rbx
0x18000df72  jmp     ??1?$CMFTtoDMOImpl@VCMFTtoDMO@@@@QEAA@XZ; CMFTtoDMOImpl<CMFTtoDMO>::~CMFTtoDMOImpl<CMFTtoDMO>(void)
```
