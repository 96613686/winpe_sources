# CBaseSplitterFilter::~CBaseSplitterFilter(void)

- ea: `0x18000b87c`
- end: `0x18000b92d`
- name: `??1CBaseSplitterFilter@@UEAA@XZ`
- size: `177`
- prototype: `void __fastcall(CBaseSplitterFilter *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180007390`
- `0x18000a3fc`
- `0x18000b9f0`

## callees

- `0x180003044`
- `0x18000676c`
- `0x18000b87c`
- `0x18000c91c`
- `0x180034010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000b8e7`
- `KERNEL32!DeleteCriticalSection` at `0x18000b8f4`
- `KERNEL32!DeleteCriticalSection` at `0x18000b901`
- `KERNEL32!DeleteCriticalSection` at `0x18000b90e`
- `KERNEL32!DeleteCriticalSection` at `0x18000b8e7`
- `KERNEL32!DeleteCriticalSection` at `0x18000b8f4`
- `KERNEL32!DeleteCriticalSection` at `0x18000b901`
- `KERNEL32!DeleteCriticalSection` at `0x18000b90e`

## pseudocode

```c
void __fastcall CBaseSplitterFilter::~CBaseSplitterFilter(CBaseSplitterFilter *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CBaseSplitterFilter::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CBaseSplitterFilter::`vftable'{for `IBaseFilter'};
  *((_QWORD *)this + 4) = &CBaseSplitterFilter::`vftable'{for `IAMovieSetup'};
  *((_QWORD *)this + 15) = &CMPEG2SplitterFilter::`vftable'{for `CBaseSplitterFilter'};
  v2 = *((_QWORD *)this + 16);
  if ( v2 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 24LL))(v2, 1);
  *((_QWORD *)this + 16) = 0;
  CBaseSplitterFilter::DestroyOutputPins(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 8);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 256));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  CBaseList::~CBaseList((CBaseSplitterFilter *)((char *)this + 136));
  CBaseFilter::~CBaseFilter(this);
}

```

## disassembly

```asm
0x18000b87c  push    rbx
0x18000b87e  sub     rsp, 20h
0x18000b882  lea     rax, ??_7CBaseSplitterFilter@@6BCUnknown@@@; const CBaseSplitterFilter::`vftable'{for `CUnknown'}
0x18000b889  mov     rbx, rcx
0x18000b88c  mov     [rcx], rax
0x18000b88f  lea     rax, ??_7CBaseSplitterFilter@@6BIBaseFilter@@@; const CBaseSplitterFilter::`vftable'{for `IBaseFilter'}
0x18000b896  mov     [rcx+18h], rax
0x18000b89a  lea     rax, ??_7CBaseSplitterFilter@@6BIAMovieSetup@@@; const CBaseSplitterFilter::`vftable'{for `IAMovieSetup'}
0x18000b8a1  mov     [rcx+20h], rax
0x18000b8a5  lea     rax, ??_7CMPEG2SplitterFilter@@6BCBaseSplitterFilter@@@; const CMPEG2SplitterFilter::`vftable'{for `CBaseSplitterFilter'}
0x18000b8ac  mov     [rcx+78h], rax
0x18000b8b0  mov     rcx, [rcx+80h]
0x18000b8b7  test    rcx, rcx
0x18000b8ba  jz      short loc_18000B8CD
0x18000b8bc  mov     rax, [rcx]
0x18000b8bf  mov     edx, 1
0x18000b8c4  mov     rax, [rax+18h]
0x18000b8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8cd  mov     rcx, rbx; this
0x18000b8d0  mov     qword ptr [rbx+80h], 0
0x18000b8db  call    ?DestroyOutputPins@CBaseSplitterFilter@@QEAAXXZ; CBaseSplitterFilter::DestroyOutputPins(void)
0x18000b8e0  lea     rcx, [rbx+140h]; lpCriticalSection
0x18000b8e7  call    cs:__imp_DeleteCriticalSection
0x18000b8ed  lea     rcx, [rbx+100h]; lpCriticalSection
0x18000b8f4  call    cs:__imp_DeleteCriticalSection
0x18000b8fa  lea     rcx, [rbx+0D8h]; lpCriticalSection
0x18000b901  call    cs:__imp_DeleteCriticalSection
0x18000b907  lea     rcx, [rbx+0B0h]; lpCriticalSection
0x18000b90e  call    cs:__imp_DeleteCriticalSection
0x18000b914  lea     rcx, [rbx+88h]; this
0x18000b91b  call    ??1CBaseList@@QEAA@XZ; CBaseList::~CBaseList(void)
0x18000b920  mov     rcx, rbx; this
0x18000b923  add     rsp, 20h
0x18000b927  pop     rbx
0x18000b928  jmp     ??1CBaseFilter@@UEAA@XZ; CBaseFilter::~CBaseFilter(void)
```
