# CMPEG2DemuxOutputPin::~CMPEG2DemuxOutputPin(void)

- ea: `0x1800221c4`
- end: `0x180022362`
- name: `??1CMPEG2DemuxOutputPin@@UEAA@XZ`
- size: `414`
- prototype: `void __fastcall(CMPEG2DemuxOutputPin *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180022490`

## callees

- `0x180001048`
- `0x1800030c8`
- `0x180006b18`
- `0x180010ea8`
- `0x1800221c4`
- `0x180033190`
- `0x180034010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180022269`
- `KERNEL32!DeleteCriticalSection` at `0x180022294`
- `KERNEL32!DeleteCriticalSection` at `0x18002232b`
- `KERNEL32!DeleteCriticalSection` at `0x180022269`
- `KERNEL32!DeleteCriticalSection` at `0x180022294`
- `KERNEL32!DeleteCriticalSection` at `0x18002232b`

## pseudocode

```c
void __fastcall CMPEG2DemuxOutputPin::~CMPEG2DemuxOutputPin(CMPEG2DemuxOutputPin *this)
{
  COutputQueue *v1; // rdi
  __int64 v3; // rdi
  __int64 v4; // rdi
  volatile signed __int32 *v5; // rdi
  void (__fastcall ***v6)(_QWORD, __int64); // rcx
  volatile signed __int32 *v7; // rcx

  v1 = (COutputQueue *)*((_QWORD *)this + 45);
  *(_QWORD *)this = &CMPEG2DemuxOutputPin::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CSplitterOutputPin::`vftable'{for `IPin'};
  *((_QWORD *)this + 4) = &CSplitterOutputPin::`vftable'{for `IQualityControl'};
  *((_QWORD *)this + 29) = &CMPEG2DemuxOutputPin::`vftable'{for `IMPEG2PIDMap'};
  *((_QWORD *)this + 30) = &CMPEG2DemuxOutputPin::`vftable'{for `IMPEG2StreamIdMap'};
  *((_QWORD *)this + 31) = &CMPEG2DemuxOutputPin::`vftable'{for `IAMPushSource'};
  *((_QWORD *)this + 32) = &CMPEG2DemuxOutputPin::`vftable'{for `IInbandEvent'};
  if ( v1 )
  {
    COutputQueue::~COutputQueue(v1);
    operator delete(v1, 0x90u);
  }
  v3 = *((_QWORD *)this + 8);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 40), 0xFFFFFFFF) == 1 && v3 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)v3);
    operator delete((void *)v3, 0x30u);
  }
  v4 = *((_QWORD *)this + 58);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 40), 0xFFFFFFFF) == 1 && v4 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)v4);
    operator delete((void *)v4, 0x30u);
  }
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 46);
  if ( _InterlockedExchangeAdd(v5 + 10, 0xFFFFFFFF) == 1 && v5 )
  {
    CMpeg2Stats::~CMpeg2Stats((CMpeg2Stats *)v5);
    operator delete((void *)v5, 0x2530u);
  }
  v6 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 63);
  if ( v6 )
    (**v6)(v6, 1);
  v7 = (volatile signed __int32 *)*((_QWORD *)this + 61);
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd(v7 + 38, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v7 + 16LL))(v7, 1);
    *((_QWORD *)this + 61) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 13);
  *((_QWORD *)this + 51) = &CMpeg2DemuxMediaSeekingCOM::`vftable';
  FreeMediaType((struct _AMMediaType *)this + 3);
  CBasePin::~CBasePin(this);
}

```

## disassembly

```asm
0x1800221c4  mov     [rsp+arg_8], rbx
0x1800221c9  mov     [rsp+arg_10], rsi
0x1800221ce  push    rdi
0x1800221cf  sub     rsp, 20h
0x1800221d3  mov     rdi, [rcx+168h]
0x1800221da  lea     rax, ??_7CMPEG2DemuxOutputPin@@6BCUnknown@@@; const CMPEG2DemuxOutputPin::`vftable'{for `CUnknown'}
0x1800221e1  mov     [rcx], rax
0x1800221e4  lea     rax, ??_7CSplitterOutputPin@@6BIPin@@@; const CSplitterOutputPin::`vftable'{for `IPin'}
0x1800221eb  mov     [rcx+18h], rax
0x1800221ef  lea     rax, ??_7CSplitterOutputPin@@6BIQualityControl@@@; const CSplitterOutputPin::`vftable'{for `IQualityControl'}
0x1800221f6  mov     [rcx+20h], rax
0x1800221fa  lea     rax, ??_7CMPEG2DemuxOutputPin@@6BIMPEG2PIDMap@@@; const CMPEG2DemuxOutputPin::`vftable'{for `IMPEG2PIDMap'}
0x180022201  mov     [rcx+0E8h], rax
0x180022208  lea     rax, ??_7CMPEG2DemuxOutputPin@@6BIMPEG2StreamIdMap@@@; const CMPEG2DemuxOutputPin::`vftable'{for `IMPEG2StreamIdMap'}
0x18002220f  mov     [rcx+0F0h], rax
0x180022216  lea     rax, ??_7CMPEG2DemuxOutputPin@@6BIAMPushSource@@@; const CMPEG2DemuxOutputPin::`vftable'{for `IAMPushSource'}
0x18002221d  mov     [rcx+0F8h], rax
0x180022224  lea     rax, ??_7CMPEG2DemuxOutputPin@@6BIInbandEvent@@@; const CMPEG2DemuxOutputPin::`vftable'{for `IInbandEvent'}
0x18002222b  mov     [rcx+100h], rax
0x180022232  mov     rbx, rcx
0x180022235  test    rdi, rdi
0x180022238  jz      short loc_18002224F
0x18002223a  mov     rcx, rdi; this
0x18002223d  call    ??1COutputQueue@@QEAA@XZ; COutputQueue::~COutputQueue(void)
0x180022242  mov     edx, 90h; unsigned __int64
0x180022247  mov     rcx, rdi; void *
0x18002224a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002224f  mov     rdi, [rbx+40h]
0x180022253  or      esi, 0FFFFFFFFh
0x180022256  mov     eax, esi
0x180022258  lock xadd [rdi+28h], eax
0x18002225d  add     eax, esi
0x18002225f  jnz     short loc_18002227A
0x180022261  test    rdi, rdi
0x180022264  jz      short loc_18002227A
0x180022266  mov     rcx, rdi; lpCriticalSection
0x180022269  call    cs:__imp_DeleteCriticalSection
0x18002226f  lea     edx, [rsi+31h]; unsigned __int64
0x180022272  mov     rcx, rdi; void *
0x180022275  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002227a  mov     rdi, [rbx+1D0h]
0x180022281  mov     eax, esi
0x180022283  lock xadd [rdi+28h], eax
0x180022288  add     eax, esi
0x18002228a  jnz     short loc_1800222A7
0x18002228c  test    rdi, rdi
0x18002228f  jz      short loc_1800222A7
0x180022291  mov     rcx, rdi; lpCriticalSection
0x180022294  call    cs:__imp_DeleteCriticalSection
0x18002229a  mov     edx, 30h ; '0'; unsigned __int64
0x18002229f  mov     rcx, rdi; void *
0x1800222a2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800222a7  mov     rdi, [rbx+170h]
0x1800222ae  mov     eax, esi
0x1800222b0  lock xadd [rdi+28h], eax
0x1800222b5  add     eax, esi
0x1800222b7  jnz     short loc_1800222D3
0x1800222b9  test    rdi, rdi
0x1800222bc  jz      short loc_1800222D3
0x1800222be  mov     rcx, rdi; this
0x1800222c1  call    ??1CMpeg2Stats@@QEAA@XZ; CMpeg2Stats::~CMpeg2Stats(void)
0x1800222c6  mov     edx, 2530h; unsigned __int64
0x1800222cb  mov     rcx, rdi; void *
0x1800222ce  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800222d3  mov     rcx, [rbx+1F8h]
0x1800222da  mov     edi, 1
0x1800222df  test    rcx, rcx
0x1800222e2  jz      short loc_1800222F1
0x1800222e4  mov     rax, [rcx]
0x1800222e7  mov     edx, edi
0x1800222e9  mov     rax, [rax]
0x1800222ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222f1  mov     rcx, [rbx+1E8h]
0x1800222f8  test    rcx, rcx
0x1800222fb  jz      short loc_180022324
0x1800222fd  mov     eax, esi
0x1800222ff  lock xadd [rcx+98h], eax
0x180022307  add     eax, esi
0x180022309  jnz     short loc_180022319
0x18002230b  mov     rax, [rcx]
0x18002230e  mov     edx, edi
0x180022310  mov     rax, [rax+10h]
0x180022314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022319  mov     qword ptr [rbx+1E8h], 0
0x180022324  lea     rcx, [rbx+208h]; lpCriticalSection
0x18002232b  call    cs:__imp_DeleteCriticalSection
0x180022331  lea     rax, ??_7CMpeg2DemuxMediaSeekingCOM@@6B@; const CMpeg2DemuxMediaSeekingCOM::`vftable'
0x180022338  lea     rcx, [rbx+108h]; struct _AMMediaType *
0x18002233f  mov     [rbx+198h], rax
0x180022346  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x18002234b  mov     rcx, rbx; this
0x18002234e  mov     rbx, [rsp+28h+arg_8]
0x180022353  mov     rsi, [rsp+28h+arg_10]
0x180022358  add     rsp, 20h
0x18002235c  pop     rdi
0x18002235d  jmp     ??1CBasePin@@UEAA@XZ; CBasePin::~CBasePin(void)
```
