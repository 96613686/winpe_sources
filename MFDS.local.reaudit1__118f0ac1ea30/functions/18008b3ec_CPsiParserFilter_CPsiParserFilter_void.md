# CPsiParserFilter::~CPsiParserFilter(void)

- ea: `0x18008b3ec`
- end: `0x18008b4a3`
- name: `??1CPsiParserFilter@@UEAA@XZ`
- size: `183`
- prototype: `void __fastcall(CPsiParserFilter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18008b650`

## callees

- `0x180023b3c`
- `0x18008b3ec`
- `0x18008b690`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008b464`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008b477`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008b48a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008b464`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008b477`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008b48a`

## pseudocode

```c
void __fastcall CPsiParserFilter::~CPsiParserFilter(CPsiParserFilter *this)
{
  CPsiParserInputPin *v2; // rcx

  *(_QWORD *)this = &CPsiParserFilter::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CPsiParserFilter::`vftable'{for `IBaseFilter'};
  *((_QWORD *)this + 4) = &CPsiParserFilter::`vftable'{for `IAMovieSetup'};
  *((_QWORD *)this + 15) = &CPsiParserFilter::`vftable'{for `IMpeg2TSPsiParser'};
  *((_QWORD *)this + 16) = &CPsiParserFilter::`vftable'{for `IAMFilterMiscFlags'};
  *((_QWORD *)this + 17) = &CPsiParserFilter::`vftable'{for `IMFPsiFilterConfig'};
  v2 = (CPsiParserInputPin *)*((_QWORD *)this + 33);
  if ( v2 )
    CPsiParserInputPin::`vector deleting destructor'(v2, 1u);
  *((_QWORD *)this + 33) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  CBaseFilter::~CBaseFilter(this);
}

```

## disassembly

```asm
0x18008b3ec  push    rbx
0x18008b3ee  sub     rsp, 20h
0x18008b3f2  lea     rax, ??_7CPsiParserFilter@@6BCUnknown@@@; const CPsiParserFilter::`vftable'{for `CUnknown'}
0x18008b3f9  mov     rbx, rcx
0x18008b3fc  mov     [rcx], rax
0x18008b3ff  lea     rax, ??_7CPsiParserFilter@@6BIBaseFilter@@@; const CPsiParserFilter::`vftable'{for `IBaseFilter'}
0x18008b406  mov     [rcx+18h], rax
0x18008b40a  lea     rax, ??_7CPsiParserFilter@@6BIAMovieSetup@@@; const CPsiParserFilter::`vftable'{for `IAMovieSetup'}
0x18008b411  mov     [rcx+20h], rax
0x18008b415  lea     rax, ??_7CPsiParserFilter@@6BIMpeg2TSPsiParser@@@; const CPsiParserFilter::`vftable'{for `IMpeg2TSPsiParser'}
0x18008b41c  mov     [rcx+78h], rax
0x18008b420  lea     rax, ??_7CPsiParserFilter@@6BIAMFilterMiscFlags@@@; const CPsiParserFilter::`vftable'{for `IAMFilterMiscFlags'}
0x18008b427  mov     [rcx+80h], rax
0x18008b42e  lea     rax, ??_7CPsiParserFilter@@6BIMFPsiFilterConfig@@@; const CPsiParserFilter::`vftable'{for `IMFPsiFilterConfig'}
0x18008b435  mov     [rcx+88h], rax
0x18008b43c  mov     rcx, [rcx+108h]; this
0x18008b443  test    rcx, rcx
0x18008b446  jz      short loc_18008B452
0x18008b448  mov     edx, 1; unsigned int
0x18008b44d  call    ??_ECPsiParserInputPin@@UEAAPEAXI@Z; CPsiParserInputPin::`vector deleting destructor'(uint)
0x18008b452  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x18008b459  mov     qword ptr [rbx+108h], 0
0x18008b464  call    cs:__imp_DeleteCriticalSection
0x18008b46b  nop     dword ptr [rax+rax+00h]
0x18008b470  lea     rcx, [rbx+0B8h]; lpCriticalSection
0x18008b477  call    cs:__imp_DeleteCriticalSection
0x18008b47e  nop     dword ptr [rax+rax+00h]
0x18008b483  lea     rcx, [rbx+90h]; lpCriticalSection
0x18008b48a  call    cs:__imp_DeleteCriticalSection
0x18008b491  nop     dword ptr [rax+rax+00h]
0x18008b496  mov     rcx, rbx; this
0x18008b499  add     rsp, 20h
0x18008b49d  pop     rbx
0x18008b49e  jmp     ??1CBaseFilter@@UEAA@XZ; CBaseFilter::~CBaseFilter(void)
```
