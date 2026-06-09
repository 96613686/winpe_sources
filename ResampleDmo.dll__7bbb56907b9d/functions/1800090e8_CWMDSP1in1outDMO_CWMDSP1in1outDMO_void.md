# CWMDSP1in1outDMO::~CWMDSP1in1outDMO(void)

- ea: `0x1800090e8`
- end: `0x180009151`
- name: `??1CWMDSP1in1outDMO@@QEAA@XZ`
- size: `105`
- prototype: `void __fastcall(CWMDSP1in1outDMO *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a17c`

## callees

- `0x1800090e8`
- `0x180009158`

## import_xrefs

- `msdmo!MoFreeMediaType` at `0x180009110`
- `msdmo!MoFreeMediaType` at `0x18000912a`
- `msdmo!MoFreeMediaType` at `0x180009110`
- `msdmo!MoFreeMediaType` at `0x18000912a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000913e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000913e`

## pseudocode

```c
void __fastcall CWMDSP1in1outDMO::~CWMDSP1in1outDMO(CWMDSP1in1outDMO *this)
{
  bool v1; // zf

  v1 = *((_DWORD *)this + 14) == 0;
  *(_QWORD *)this = &CWMDSP1in1outDMO::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'};
  *((_QWORD *)this + 6) = &CWMDSP1in1outDMO::`vftable'{for `IMediaObject'};
  if ( !v1 )
  {
    MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 64));
    *((_DWORD *)this + 14) = 0;
  }
  if ( *((_DWORD *)this + 15) )
  {
    MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 152));
    *((_DWORD *)this + 15) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 256));
  CMFTtoDMOImpl<CMFTtoDMO>::~CMFTtoDMOImpl<CMFTtoDMO>(this);
}

```

## disassembly

```asm
0x1800090e8  push    rbx
0x1800090ea  sub     rsp, 20h
0x1800090ee  cmp     dword ptr [rcx+38h], 0
0x1800090f2  lea     rax, ??_7CWMDSP1in1outDMO@@6B?$CMFTtoDMOImpl@VCMFTtoDMO@@@@@; const CWMDSP1in1outDMO::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'}
0x1800090f9  mov     [rcx], rax
0x1800090fc  mov     rbx, rcx
0x1800090ff  lea     rax, ??_7CWMDSP1in1outDMO@@6BIMediaObject@@@; const CWMDSP1in1outDMO::`vftable'{for `IMediaObject'}
0x180009106  mov     [rcx+30h], rax
0x18000910a  jz      short loc_18000911D
0x18000910c  add     rcx, 40h ; '@'; pmt
0x180009110  call    cs:__imp_MoFreeMediaType
0x180009116  mov     dword ptr [rbx+38h], 0
0x18000911d  cmp     dword ptr [rbx+3Ch], 0
0x180009121  jz      short loc_180009137
0x180009123  lea     rcx, [rbx+98h]; pmt
0x18000912a  call    cs:__imp_MoFreeMediaType
0x180009130  mov     dword ptr [rbx+3Ch], 0
0x180009137  lea     rcx, [rbx+100h]; lpCriticalSection
0x18000913e  call    cs:__imp_DeleteCriticalSection
0x180009144  mov     rcx, rbx
0x180009147  add     rsp, 20h
0x18000914b  pop     rbx
0x18000914c  jmp     ??1?$CMFTtoDMOImpl@VCMFTtoDMO@@@@QEAA@XZ; CMFTtoDMOImpl<CMFTtoDMO>::~CMFTtoDMOImpl<CMFTtoDMO>(void)
```
