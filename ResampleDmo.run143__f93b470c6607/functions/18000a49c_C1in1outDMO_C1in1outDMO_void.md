# C1in1outDMO::~C1in1outDMO(void)

- ea: `0x18000a49c`
- end: `0x18000a4f7`
- name: `??1C1in1outDMO@@QEAA@XZ`
- size: `91`
- prototype: `void __fastcall(C1in1outDMO *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007b64`

## callees

- `0x180009158`
- `0x18000a49c`

## import_xrefs

- `msdmo!MoFreeMediaType` at `0x18000a4d1`
- `msdmo!MoFreeMediaType` at `0x18000a4e4`
- `msdmo!MoFreeMediaType` at `0x18000a4d1`
- `msdmo!MoFreeMediaType` at `0x18000a4e4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a4c1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a4c1`

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
0x18000a49c  push    rbx
0x18000a49e  sub     rsp, 20h
0x18000a4a2  lea     rax, ??_7C1in1outDMO@@6B?$CMFTtoDMOImpl@VCMFTtoDMO@@@@@; const C1in1outDMO::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'}
0x18000a4a9  mov     rbx, rcx
0x18000a4ac  mov     [rcx], rax
0x18000a4af  lea     rax, ??_7C1in1outDMO@@6BIMediaObject@@@; const C1in1outDMO::`vftable'{for `IMediaObject'}
0x18000a4b6  mov     [rcx+30h], rax
0x18000a4ba  add     rcx, 0F8h; lpCriticalSection
0x18000a4c1  call    cs:__imp_DeleteCriticalSection
0x18000a4c7  cmp     dword ptr [rbx+38h], 0
0x18000a4cb  jz      short loc_18000A4D7
0x18000a4cd  lea     rcx, [rbx+40h]; pmt
0x18000a4d1  call    cs:__imp_MoFreeMediaType
0x18000a4d7  cmp     dword ptr [rbx+3Ch], 0
0x18000a4db  jz      short loc_18000A4EA
0x18000a4dd  lea     rcx, [rbx+98h]; pmt
0x18000a4e4  call    cs:__imp_MoFreeMediaType
0x18000a4ea  mov     rcx, rbx
0x18000a4ed  add     rsp, 20h
0x18000a4f1  pop     rbx
0x18000a4f2  jmp     ??1?$CMFTtoDMOImpl@VCMFTtoDMO@@@@QEAA@XZ; CMFTtoDMOImpl<CMFTtoDMO>::~CMFTtoDMOImpl<CMFTtoDMO>(void)
```
