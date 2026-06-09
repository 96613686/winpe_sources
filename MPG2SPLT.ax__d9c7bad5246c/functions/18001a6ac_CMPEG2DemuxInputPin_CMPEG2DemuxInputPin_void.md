# CMPEG2DemuxInputPin::~CMPEG2DemuxInputPin(void)

- ea: `0x18001a6ac`
- end: `0x18001a79f`
- name: `??1CMPEG2DemuxInputPin@@UEAA@XZ`
- size: `243`
- prototype: `void __fastcall(CMPEG2DemuxInputPin *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001a7e0`

## callees

- `0x180001048`
- `0x180003088`
- `0x180010ea8`
- `0x18001a6ac`
- `0x180034010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001a71d`
- `KERNEL32!DeleteCriticalSection` at `0x18001a74c`
- `KERNEL32!DeleteCriticalSection` at `0x18001a71d`
- `KERNEL32!DeleteCriticalSection` at `0x18001a74c`

## pseudocode

```c
void __fastcall CMPEG2DemuxInputPin::~CMPEG2DemuxInputPin(CMPEG2DemuxInputPin *this)
{
  __int64 v2; // rcx
  __int64 v3; // rdi
  __int64 v4; // rdi
  volatile signed __int32 *v5; // rdi

  *(_QWORD *)this = &CMPEG2DemuxInputPin::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CMPEG2DemuxInputPin::`vftable'{for `IPin'};
  *((_QWORD *)this + 4) = &CMPEG2DemuxInputPin::`vftable'{for `IQualityControl'};
  *((_QWORD *)this + 27) = &CMPEG2DemuxInputPin::`vftable';
  v2 = *((_QWORD *)this + 38);
  if ( v2 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 8LL))(v2, 1);
  v3 = *((_QWORD *)this + 8);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 40), 0xFFFFFFFF) == 1 && v3 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)v3);
    operator delete((void *)v3, 0x30u);
  }
  v4 = *((_QWORD *)this + 41);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 40), 0xFFFFFFFF) == 1 && v4 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)v4);
    operator delete((void *)v4, 0x30u);
  }
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 40);
  if ( _InterlockedExchangeAdd(v5 + 10, 0xFFFFFFFF) == 1 && v5 )
  {
    CMpeg2Stats::~CMpeg2Stats((CMpeg2Stats *)v5);
    operator delete((void *)v5, 0x2530u);
  }
  CBaseInputPin::~CBaseInputPin(this);
}

```

## disassembly

```asm
0x18001a6ac  mov     [rsp+arg_8], rbx
0x18001a6b1  push    rdi
0x18001a6b2  sub     rsp, 20h
0x18001a6b6  lea     rax, ??_7CMPEG2DemuxInputPin@@6BCUnknown@@@; const CMPEG2DemuxInputPin::`vftable'{for `CUnknown'}
0x18001a6bd  mov     rbx, rcx
0x18001a6c0  mov     [rcx], rax
0x18001a6c3  lea     rax, ??_7CMPEG2DemuxInputPin@@6BIPin@@@; const CMPEG2DemuxInputPin::`vftable'{for `IPin'}
0x18001a6ca  mov     [rcx+18h], rax
0x18001a6ce  lea     rax, ??_7CMPEG2DemuxInputPin@@6BIQualityControl@@@; const CMPEG2DemuxInputPin::`vftable'{for `IQualityControl'}
0x18001a6d5  mov     [rcx+20h], rax
0x18001a6d9  lea     rax, ??_7CMPEG2DemuxInputPin@@6B@; const CMPEG2DemuxInputPin::`vftable'
0x18001a6e0  mov     [rcx+0D8h], rax
0x18001a6e7  mov     rcx, [rcx+130h]
0x18001a6ee  test    rcx, rcx
0x18001a6f1  jz      short loc_18001A704
0x18001a6f3  mov     rax, [rcx]
0x18001a6f6  mov     edx, 1
0x18001a6fb  mov     rax, [rax+8]
0x18001a6ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a704  mov     rdi, [rbx+40h]
0x18001a708  or      eax, 0FFFFFFFFh
0x18001a70b  lock xadd [rdi+28h], eax
0x18001a710  cmp     eax, 1
0x18001a713  jnz     short loc_18001A730
0x18001a715  test    rdi, rdi
0x18001a718  jz      short loc_18001A730
0x18001a71a  mov     rcx, rdi; lpCriticalSection
0x18001a71d  call    cs:__imp_DeleteCriticalSection
0x18001a723  mov     edx, 30h ; '0'; unsigned __int64
0x18001a728  mov     rcx, rdi; void *
0x18001a72b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a730  mov     rdi, [rbx+148h]
0x18001a737  or      eax, 0FFFFFFFFh
0x18001a73a  lock xadd [rdi+28h], eax
0x18001a73f  cmp     eax, 1
0x18001a742  jnz     short loc_18001A75F
0x18001a744  test    rdi, rdi
0x18001a747  jz      short loc_18001A75F
0x18001a749  mov     rcx, rdi; lpCriticalSection
0x18001a74c  call    cs:__imp_DeleteCriticalSection
0x18001a752  mov     edx, 30h ; '0'; unsigned __int64
0x18001a757  mov     rcx, rdi; void *
0x18001a75a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a75f  mov     rdi, [rbx+140h]
0x18001a766  or      eax, 0FFFFFFFFh
0x18001a769  lock xadd [rdi+28h], eax
0x18001a76e  cmp     eax, 1
0x18001a771  jnz     short loc_18001A78D
0x18001a773  test    rdi, rdi
0x18001a776  jz      short loc_18001A78D
0x18001a778  mov     rcx, rdi; this
0x18001a77b  call    ??1CMpeg2Stats@@QEAA@XZ; CMpeg2Stats::~CMpeg2Stats(void)
0x18001a780  mov     edx, 2530h; unsigned __int64
0x18001a785  mov     rcx, rdi; void *
0x18001a788  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a78d  mov     rcx, rbx; this
0x18001a790  mov     rbx, [rsp+28h+arg_8]
0x18001a795  add     rsp, 20h
0x18001a799  pop     rdi
0x18001a79a  jmp     ??1CBaseInputPin@@UEAA@XZ; CBaseInputPin::~CBaseInputPin(void)
```
