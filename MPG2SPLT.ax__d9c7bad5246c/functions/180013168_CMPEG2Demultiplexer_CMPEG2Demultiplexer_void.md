# CMPEG2Demultiplexer::~CMPEG2Demultiplexer(void)

- ea: `0x180013168`
- end: `0x1800134b7`
- name: `??1CMPEG2Demultiplexer@@UEAA@XZ`
- size: `847`
- prototype: `void __fastcall(CMPEG2Demultiplexer *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x180013640`

## callees

- `0x180001048`
- `0x180003044`
- `0x180010ea8`
- `0x180013168`
- `0x180017a28`
- `0x18001ce2c`
- `0x180024044`
- `0x180025570`
- `0x180034010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180013485`
- `KERNEL32!HeapFree` at `0x180013485`
- `KERNEL32!CloseHandle` at `0x180013415`
- `KERNEL32!CloseHandle` at `0x180013415`
- `KERNEL32!DeleteCriticalSection` at `0x180013327`
- `KERNEL32!DeleteCriticalSection` at `0x1800133a9`
- `KERNEL32!DeleteCriticalSection` at `0x1800133cc`
- `KERNEL32!DeleteCriticalSection` at `0x18001346a`
- `KERNEL32!DeleteCriticalSection` at `0x180013492`
- `KERNEL32!DeleteCriticalSection` at `0x180013327`
- `KERNEL32!DeleteCriticalSection` at `0x1800133a9`
- `KERNEL32!DeleteCriticalSection` at `0x1800133cc`
- `KERNEL32!DeleteCriticalSection` at `0x18001346a`
- `KERNEL32!DeleteCriticalSection` at `0x180013492`
- `KERNEL32!LeaveCriticalSection` at `0x180013461`
- `KERNEL32!LeaveCriticalSection` at `0x180013461`
- `KERNEL32!EnterCriticalSection` at `0x18001343b`
- `KERNEL32!EnterCriticalSection` at `0x18001343b`
- `ADVAPI32!RegCloseKey` at `0x18001337c`
- `ADVAPI32!RegCloseKey` at `0x18001337c`

## pseudocode

```c
void __fastcall CMPEG2Demultiplexer::~CMPEG2Demultiplexer(CMPEG2Demultiplexer *this)
{
  unsigned int v1; // ebp
  __int64 v2; // r14
  __int64 v3; // rsi
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // rcx
  void *v8; // rbx
  _QWORD *v9; // rcx
  void *v10; // rbx
  void *v11; // rbx
  __int64 v12; // rbx
  volatile signed __int32 *v13; // rbx
  HKEY v14; // rcx
  __int64 v15; // rbx
  __int64 v16; // rcx
  void *v17; // rcx
  struct _RTL_CRITICAL_SECTION *v18; // rbx
  __int64 v19; // rcx
  void *v20; // r8

  v1 = *((_DWORD *)this + 48);
  v2 = *((_QWORD *)this + 23);
  v3 = 0;
  *(_QWORD *)this = &CMPEG2Demultiplexer::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CMPEG2Demultiplexer::`vftable'{for `IBaseFilter'};
  *((_QWORD *)this + 4) = &CBaseSplitterFilter::`vftable'{for `IAMovieSetup'};
  *((_QWORD *)this + 15) = &CMPEG2Demultiplexer::`vftable'{for `CPersistStream'};
  *((_QWORD *)this + 17) = &CMPEG2Demultiplexer::`vftable'{for `IAMFilterMiscFlags'};
  *((_QWORD *)this + 18) = &CMPEG2Demultiplexer::`vftable'{for `CIInputStreamEvent'};
  for ( *((_QWORD *)this + 19) = &CMPEG2Demultiplexer::`vftable'{for `CIProgramInfo'};
        (unsigned int)v3 < v1;
        v3 = (unsigned int)(v3 + 1) )
  {
    v5 = *(volatile signed __int32 **)(v2 + 8 * v3);
    if ( !_InterlockedDecrement(v5 + 2) && v5 )
    {
      operator delete(*((void **)v5 + 2), 2u);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)v5 + 8LL) + 16LL))(*(_QWORD *)(*(_QWORD *)v5 + 8LL));
      operator delete((void *)v5, 0x18u);
    }
  }
  v6 = *((_QWORD *)this + 20);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v6 + 24) + 16LL))(v6 + 24);
    *((_QWORD *)this + 20) = 0;
  }
  v7 = *((_QWORD *)this + 42);
  if ( v7 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 40LL))(v7, 1);
  v8 = (void *)*((_QWORD *)this + 35);
  if ( v8 )
  {
    CMPEG2PushClock::~CMPEG2PushClock(*((CMPEG2PushClock **)this + 35));
    operator delete(v8, 0x2B8u);
  }
  v9 = (_QWORD *)*((_QWORD *)this + 21);
  if ( v9 )
  {
    *v9 = &CDShowMPEG2Demux::`vftable'{for `IMpeg2Demultiplexer'};
    v9[1] = &CDShowMPEG2Demux::`vftable'{for `ISpecifyPropertyPages'};
    v9[2] = &CDShowMPEG2Demux::`vftable'{for `IMpeg2DemultiplexerTesting'};
    operator delete(v9, 0x28u);
  }
  v10 = (void *)*((_QWORD *)this + 22);
  if ( v10 )
  {
    CBDAMPEG2Demux::~CBDAMPEG2Demux(*((CBDAMPEG2Demux **)this + 22));
    operator delete(v10, 0x58u);
  }
  v11 = (void *)*((_QWORD *)this + 43);
  if ( v11 )
  {
    CMpeg2DemuxMediaSeekingCore::~CMpeg2DemuxMediaSeekingCore(*((CMpeg2DemuxMediaSeekingCore **)this + 43));
    operator delete(v11, 0x38u);
  }
  v12 = *((_QWORD *)this + 10);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v12 + 40), 0xFFFFFFFF) == 1 && v12 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)v12);
    operator delete((void *)v12, 0x30u);
  }
  v13 = (volatile signed __int32 *)*((_QWORD *)this + 33);
  if ( v13 )
  {
    if ( _InterlockedExchangeAdd(v13 + 10, 0xFFFFFFFF) == 1 )
    {
      CMpeg2Stats::~CMpeg2Stats((CMpeg2Stats *)v13);
      operator delete((void *)v13, 0x2530u);
    }
    *((_QWORD *)this + 33) = 0;
  }
  v14 = (HKEY)*((_QWORD *)this + 34);
  if ( v14 )
  {
    RegCloseKey(v14);
    *((_QWORD *)this + 34) = 0;
  }
  v15 = *((_QWORD *)this + 44);
  if ( v15 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v15 + 40), 0xFFFFFFFF) == 1 )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)v15);
      operator delete((void *)v15, 0x30u);
    }
    *((_QWORD *)this + 44) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
  v16 = *((_QWORD *)this + 46);
  if ( v16 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v16 + 136), 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(__int64, __int64))v16)(v16, 1);
    *((_QWORD *)this + 46) = 0;
  }
  v17 = (void *)*((_QWORD *)this + 47);
  if ( v17 )
    CloseHandle(v17);
  *((_QWORD *)this + 179) = &CDShowESEventEx::`vftable';
  CDShowESEventEx::UnRegisterForESEvents((CMPEG2Demultiplexer *)((char *)this + 1432));
  v18 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1440);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 36);
  v19 = *((_QWORD *)this + 185);
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    *((_QWORD *)this + 185) = 0;
  }
  LeaveCriticalSection(v18);
  DeleteCriticalSection(v18);
  v20 = (void *)*((_QWORD *)this + 23);
  if ( v20 )
    HeapFree(*((HANDLE *)this + 26), 0, v20);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  *((_QWORD *)this + 15) = &CPersistStream::`vftable';
  CBaseFilter::~CBaseFilter(this);
}

```

## disassembly

```asm
0x180013168  push    rbx
0x18001316a  push    rbp
0x18001316b  push    rsi
0x18001316c  push    rdi
0x18001316d  push    r12
0x18001316f  push    r14
0x180013171  sub     rsp, 28h
0x180013175  mov     ebp, [rcx+0C0h]
0x18001317b  lea     rax, ??_7CMPEG2Demultiplexer@@6BCUnknown@@@; const CMPEG2Demultiplexer::`vftable'{for `CUnknown'}
0x180013182  mov     r14, [rcx+0B8h]
0x180013189  xor     esi, esi
0x18001318b  mov     [rcx], rax
0x18001318e  or      r12d, 0FFFFFFFFh
0x180013192  lea     rax, ??_7CMPEG2Demultiplexer@@6BIBaseFilter@@@; const CMPEG2Demultiplexer::`vftable'{for `IBaseFilter'}
0x180013199  mov     rdi, rcx
0x18001319c  mov     [rcx+18h], rax
0x1800131a0  lea     rax, ??_7CBaseSplitterFilter@@6BIAMovieSetup@@@; const CBaseSplitterFilter::`vftable'{for `IAMovieSetup'}
0x1800131a7  mov     [rcx+20h], rax
0x1800131ab  lea     rax, ??_7CMPEG2Demultiplexer@@6BCPersistStream@@@; const CMPEG2Demultiplexer::`vftable'{for `CPersistStream'}
0x1800131b2  mov     [rcx+78h], rax
0x1800131b6  lea     rax, ??_7CMPEG2Demultiplexer@@6BIAMFilterMiscFlags@@@; const CMPEG2Demultiplexer::`vftable'{for `IAMFilterMiscFlags'}
0x1800131bd  mov     [rcx+88h], rax
0x1800131c4  lea     rax, ??_7CMPEG2Demultiplexer@@6BCIInputStreamEvent@@@; const CMPEG2Demultiplexer::`vftable'{for `CIInputStreamEvent'}
0x1800131cb  mov     [rcx+90h], rax
0x1800131d2  lea     rax, ??_7CMPEG2Demultiplexer@@6BCIProgramInfo@@@; const CMPEG2Demultiplexer::`vftable'{for `CIProgramInfo'}
0x1800131d9  mov     [rcx+98h], rax
0x1800131e0  test    ebp, ebp
0x1800131e2  jz      short loc_18001322C
0x1800131e4  mov     rbx, [r14+rsi*8]
0x1800131e8  mov     eax, r12d
0x1800131eb  lock xadd [rbx+8], eax
0x1800131f0  add     eax, r12d
0x1800131f3  jnz     short loc_180013226
0x1800131f5  test    rbx, rbx
0x1800131f8  jz      short loc_180013226
0x1800131fa  mov     rcx, [rbx+10h]; void *
0x1800131fe  lea     edx, [rax+2]; unsigned __int64
0x180013201  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013206  mov     rax, [rbx]
0x180013209  mov     rcx, [rax+8]
0x18001320d  mov     rax, [rcx]
0x180013210  mov     rax, [rax+10h]
0x180013214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013219  mov     edx, 18h; unsigned __int64
0x18001321e  mov     rcx, rbx; void *
0x180013221  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013226  inc     esi
0x180013228  cmp     esi, ebp
0x18001322a  jb      short loc_1800131E4
0x18001322c  mov     rcx, [rdi+0A0h]
0x180013233  test    rcx, rcx
0x180013236  jz      short loc_180013253
0x180013238  add     rcx, 18h
0x18001323c  mov     rax, [rcx]
0x18001323f  mov     rax, [rax+10h]
0x180013243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013248  mov     qword ptr [rdi+0A0h], 0
0x180013253  mov     rcx, [rdi+150h]
0x18001325a  test    rcx, rcx
0x18001325d  jz      short loc_180013270
0x18001325f  mov     rax, [rcx]
0x180013262  mov     edx, 1
0x180013267  mov     rax, [rax+28h]
0x18001326b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013270  mov     rbx, [rdi+118h]
0x180013277  test    rbx, rbx
0x18001327a  jz      short loc_180013291
0x18001327c  mov     rcx, rbx; this
0x18001327f  call    ??1CMPEG2PushClock@@QEAA@XZ; CMPEG2PushClock::~CMPEG2PushClock(void)
0x180013284  mov     edx, 2B8h; unsigned __int64
0x180013289  mov     rcx, rbx; void *
0x18001328c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013291  mov     rcx, [rdi+0A8h]; void *
0x180013298  test    rcx, rcx
0x18001329b  jz      short loc_1800132C7
0x18001329d  lea     rax, ??_7CDShowMPEG2Demux@@6BIMpeg2Demultiplexer@@@; const CDShowMPEG2Demux::`vftable'{for `IMpeg2Demultiplexer'}
0x1800132a4  mov     edx, 28h ; '('; unsigned __int64
0x1800132a9  mov     [rcx], rax
0x1800132ac  lea     rax, ??_7CDShowMPEG2Demux@@6BISpecifyPropertyPages@@@; const CDShowMPEG2Demux::`vftable'{for `ISpecifyPropertyPages'}
0x1800132b3  mov     [rcx+8], rax
0x1800132b7  lea     rax, ??_7CDShowMPEG2Demux@@6BIMpeg2DemultiplexerTesting@@@; const CDShowMPEG2Demux::`vftable'{for `IMpeg2DemultiplexerTesting'}
0x1800132be  mov     [rcx+10h], rax
0x1800132c2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800132c7  mov     rbx, [rdi+0B0h]
0x1800132ce  test    rbx, rbx
0x1800132d1  jz      short loc_1800132E8
0x1800132d3  mov     rcx, rbx; this
0x1800132d6  call    ??1CBDAMPEG2Demux@@QEAA@XZ; CBDAMPEG2Demux::~CBDAMPEG2Demux(void)
0x1800132db  mov     edx, 58h ; 'X'; unsigned __int64
0x1800132e0  mov     rcx, rbx; void *
0x1800132e3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800132e8  mov     rbx, [rdi+158h]
0x1800132ef  test    rbx, rbx
0x1800132f2  jz      short loc_180013309
0x1800132f4  mov     rcx, rbx; this
0x1800132f7  call    ??1CMpeg2DemuxMediaSeekingCore@@QEAA@XZ; CMpeg2DemuxMediaSeekingCore::~CMpeg2DemuxMediaSeekingCore(void)
0x1800132fc  mov     edx, 38h ; '8'; unsigned __int64
0x180013301  mov     rcx, rbx; void *
0x180013304  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013309  mov     rbx, [rdi+50h]
0x18001330d  mov     eax, r12d
0x180013310  lock xadd [rbx+28h], eax
0x180013315  mov     esi, 30h ; '0'
0x18001331a  add     eax, r12d
0x18001331d  jnz     short loc_180013337
0x18001331f  test    rbx, rbx
0x180013322  jz      short loc_180013337
0x180013324  mov     rcx, rbx; lpCriticalSection
0x180013327  call    cs:__imp_DeleteCriticalSection
0x18001332d  mov     edx, esi; unsigned __int64
0x18001332f  mov     rcx, rbx; void *
0x180013332  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013337  mov     rbx, [rdi+108h]
0x18001333e  test    rbx, rbx
0x180013341  jz      short loc_180013370
0x180013343  mov     eax, r12d
0x180013346  lock xadd [rbx+28h], eax
0x18001334b  add     eax, r12d
0x18001334e  jnz     short loc_180013365
0x180013350  mov     rcx, rbx; this
0x180013353  call    ??1CMpeg2Stats@@QEAA@XZ; CMpeg2Stats::~CMpeg2Stats(void)
0x180013358  mov     edx, 2530h; unsigned __int64
0x18001335d  mov     rcx, rbx; void *
0x180013360  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013365  mov     qword ptr [rdi+108h], 0
0x180013370  mov     rcx, [rdi+110h]; hKey
0x180013377  test    rcx, rcx
0x18001337a  jz      short loc_18001338D
0x18001337c  call    cs:__imp_RegCloseKey
0x180013382  mov     qword ptr [rdi+110h], 0
0x18001338d  mov     rbx, [rdi+160h]
0x180013394  test    rbx, rbx
0x180013397  jz      short loc_1800133C5
0x180013399  mov     eax, r12d
0x18001339c  lock xadd [rbx+28h], eax
0x1800133a1  add     eax, r12d
0x1800133a4  jnz     short loc_1800133BA
0x1800133a6  mov     rcx, rbx; lpCriticalSection
0x1800133a9  call    cs:__imp_DeleteCriticalSection
0x1800133af  mov     rdx, rsi; unsigned __int64
0x1800133b2  mov     rcx, rbx; void *
0x1800133b5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800133ba  mov     qword ptr [rdi+160h], 0
0x1800133c5  lea     rcx, [rdi+128h]; lpCriticalSection
0x1800133cc  call    cs:__imp_DeleteCriticalSection
0x1800133d2  mov     rcx, [rdi+170h]
0x1800133d9  test    rcx, rcx
0x1800133dc  jz      short loc_180013409
0x1800133de  mov     eax, r12d
0x1800133e1  lock xadd [rcx+88h], eax
0x1800133e9  add     eax, r12d
0x1800133ec  jnz     short loc_1800133FE
0x1800133ee  mov     rax, [rcx]
0x1800133f1  mov     edx, 1
0x1800133f6  mov     rax, [rax]
0x1800133f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133fe  mov     qword ptr [rdi+170h], 0
0x180013409  mov     rcx, [rdi+178h]; hObject
0x180013410  test    rcx, rcx
0x180013413  jz      short loc_18001341B
0x180013415  call    cs:__imp_CloseHandle
0x18001341b  lea     rbx, [rdi+598h]
0x180013422  lea     rax, ??_7CDShowESEventEx@@6B@; const CDShowESEventEx::`vftable'
0x180013429  mov     rcx, rbx; this
0x18001342c  mov     [rbx], rax
0x18001342f  call    ?UnRegisterForESEvents@CDShowESEventEx@@QEAAJXZ; CDShowESEventEx::UnRegisterForESEvents(void)
0x180013434  add     rbx, 8
0x180013438  mov     rcx, rbx; lpCriticalSection
0x18001343b  call    cs:__imp_EnterCriticalSection
0x180013441  mov     rcx, [rbx+28h]
0x180013445  test    rcx, rcx
0x180013448  jz      short loc_18001345E
0x18001344a  mov     rax, [rcx]
0x18001344d  mov     rax, [rax+10h]
0x180013451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013456  mov     qword ptr [rbx+28h], 0
0x18001345e  mov     rcx, rbx; lpCriticalSection
0x180013461  call    cs:__imp_LeaveCriticalSection
0x180013467  mov     rcx, rbx; lpCriticalSection
0x18001346a  call    cs:__imp_DeleteCriticalSection
0x180013470  mov     r8, [rdi+0B8h]; lpMem
0x180013477  test    r8, r8
0x18001347a  jz      short loc_18001348B
0x18001347c  mov     rcx, [rdi+0D0h]; hHeap
0x180013483  xor     edx, edx; dwFlags
0x180013485  call    cs:__imp_HeapFree
0x18001348b  lea     rcx, [rdi+0E0h]; lpCriticalSection
0x180013492  call    cs:__imp_DeleteCriticalSection
0x180013498  lea     rax, ??_7CPersistStream@@6B@; const CPersistStream::`vftable'
0x18001349f  mov     rcx, rdi; this
0x1800134a2  mov     [rdi+78h], rax
0x1800134a6  add     rsp, 28h
0x1800134aa  pop     r14
0x1800134ac  pop     r12
0x1800134ae  pop     rdi
0x1800134af  pop     rsi
0x1800134b0  pop     rbp
0x1800134b1  pop     rbx
0x1800134b2  jmp     ??1CBaseFilter@@UEAA@XZ; CBaseFilter::~CBaseFilter(void)
```
