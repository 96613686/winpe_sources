# CMFSourceOutputPin::~CMFSourceOutputPin(void)

- ea: `0x180022ea8`
- end: `0x180023145`
- name: `??1CMFSourceOutputPin@@UEAA@XZ`
- size: `669`
- prototype: `void __fastcall(CMFSourceOutputPin *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002262c`
- `0x18008b5dc`

## callees

- `0x1800227e0`
- `0x180022ea8`
- `0x18002314c`
- `0x180023170`
- `0x18008ff60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023107`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023126`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023107`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023126`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002309b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800230e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002309b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800230e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002306c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800230b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002306c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800230b6`

## pseudocode

```c
void __fastcall CMFSourceOutputPin::~CMFSourceOutputPin(CMFSourceOutputPin *this)
{
  _QWORD *v2; // rcx
  CMFSourceOutputPin::CReadRequest *v3; // r8
  __int64 v4; // rdx
  __int64 v5; // rdx
  _QWORD *v6; // rcx
  CMFSourceOutputPin::CReadRequest *v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rdx
  CMFSourceOutputPin::CReadRequest *v10; // rcx
  HANDLE ProcessHeap; // rax
  _QWORD *v12; // r8
  void *v13; // rbp
  _QWORD *v14; // rdi
  HANDLE v15; // rax
  _QWORD *v16; // r8
  void *v17; // rbp
  _QWORD *v18; // rdi

  *(_QWORD *)this = &CMFSourceOutputPin::`vftable'{for `IAsyncReader'};
  *((_QWORD *)this + 1) = &CMFSourceOutputPin::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 4) = &CMFSourceOutputPin::`vftable'{for `IPin'};
  *((_QWORD *)this + 5) = &CMFSourceOutputPin::`vftable'{for `IQualityControl'};
  *((_QWORD *)this + 28) = &CMFSourceOutputPin::`vftable'{for `CMFSourceBufferingSupport'};
  while ( 1 )
  {
    v2 = (_QWORD *)*((_QWORD *)this + 48);
    if ( !v2 )
      break;
    if ( *((_QWORD **)this + 50) == v2 )
      *((_QWORD *)this + 50) = 0;
    v3 = (CMFSourceOutputPin::CReadRequest *)v2[1];
    if ( v2 == *((_QWORD **)this + 49) )
      *((_QWORD *)this + 49) = v2[3];
    *((_QWORD *)this + 48) = v2[2];
    v4 = v2[2];
    if ( v4 )
      *(_QWORD *)(v4 + 24) = v2[3];
    v5 = v2[3];
    if ( v5 )
      *(_QWORD *)(v5 + 16) = v2[2];
    v2[2] = *((_QWORD *)this + 52);
    *((_QWORD *)this + 52) = v2;
    --*((_DWORD *)this + 102);
    if ( v3 )
      CMFSourceOutputPin::CReadRequest::Release(v3);
  }
  while ( 1 )
  {
    v6 = (_QWORD *)*((_QWORD *)this + 120);
    if ( !v6 )
      break;
    if ( *((_QWORD **)this + 122) == v6 )
      *((_QWORD *)this + 122) = 0;
    v7 = (CMFSourceOutputPin::CReadRequest *)v6[1];
    if ( v6 == *((_QWORD **)this + 121) )
      *((_QWORD *)this + 121) = v6[3];
    *((_QWORD *)this + 120) = v6[2];
    v8 = v6[2];
    if ( v8 )
      *(_QWORD *)(v8 + 24) = v6[3];
    v9 = v6[3];
    if ( v9 )
      *(_QWORD *)(v9 + 16) = v6[2];
    v6[2] = *((_QWORD *)this + 124);
    *((_QWORD *)this + 124) = v6;
    --*((_DWORD *)this + 246);
    if ( v7 )
      CMFSourceOutputPin::CReadRequest::Release(v7);
  }
  v10 = (CMFSourceOutputPin::CReadRequest *)*((_QWORD *)this + 200);
  if ( v10 )
  {
    CMFSourceOutputPin::CReadRequest::Release(v10);
    *((_QWORD *)this + 200) = 0;
  }
  CAMEvent::~CAMEvent((CMFSourceOutputPin *)((char *)this + 1560));
  CAMEvent::~CAMEvent((CMFSourceOutputPin *)((char *)this + 1552));
  CAMEvent::~CAMEvent((CMFSourceOutputPin *)((char *)this + 1544));
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>((char *)this + 1536);
  ProcessHeap = GetProcessHeap();
  v12 = (_QWORD *)*((_QWORD *)this + 125);
  v13 = ProcessHeap;
  if ( v12 )
  {
    do
    {
      v14 = (_QWORD *)*v12;
      if ( v12 != (_QWORD *)((char *)this + 1016) )
        HeapFree(v13, 0, v12);
      *((_QWORD *)this + 125) = v14;
      v12 = v14;
    }
    while ( v14 );
  }
  v15 = GetProcessHeap();
  v16 = (_QWORD *)*((_QWORD *)this + 53);
  v17 = v15;
  if ( v16 )
  {
    do
    {
      v18 = (_QWORD *)*v16;
      if ( v16 != (_QWORD *)((char *)this + 440) )
        HeapFree(v17, 0, v16);
      *((_QWORD *)this + 53) = v18;
      v16 = v18;
    }
    while ( v18 );
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 344));
  CAMEvent::~CAMEvent((CMFSourceOutputPin *)((char *)this + 336));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
  CBasePin::~CBasePin((CMFSourceOutputPin *)((char *)this + 8));
}

```

## disassembly

```asm
0x180022ea8  push    rbx
0x180022eaa  push    rbp
0x180022eab  push    rsi
0x180022eac  push    rdi
0x180022ead  push    r14
0x180022eaf  sub     rsp, 20h
0x180022eb3  lea     rax, ??_7CMFSourceOutputPin@@6BIAsyncReader@@@; const CMFSourceOutputPin::`vftable'{for `IAsyncReader'}
0x180022eba  mov     rbx, rcx
0x180022ebd  mov     [rcx], rax
0x180022ec0  or      edi, 0FFFFFFFFh
0x180022ec3  lea     rax, ??_7CMFSourceOutputPin@@6BCUnknown@@@; const CMFSourceOutputPin::`vftable'{for `CUnknown'}
0x180022eca  mov     [rcx+8], rax
0x180022ece  lea     rax, ??_7CMFSourceOutputPin@@6BIPin@@@; const CMFSourceOutputPin::`vftable'{for `IPin'}
0x180022ed5  mov     [rcx+20h], rax
0x180022ed9  lea     rax, ??_7CMFSourceOutputPin@@6BIQualityControl@@@; const CMFSourceOutputPin::`vftable'{for `IQualityControl'}
0x180022ee0  mov     [rcx+28h], rax
0x180022ee4  lea     rax, ??_7CMFSourceOutputPin@@6BCMFSourceBufferingSupport@@@; const CMFSourceOutputPin::`vftable'{for `CMFSourceBufferingSupport'}
0x180022eeb  mov     [rcx+0E0h], rax
0x180022ef2  mov     rcx, [rbx+180h]
0x180022ef9  test    rcx, rcx
0x180022efc  jz      loc_180022F89
0x180022f02  cmp     [rbx+190h], rcx
0x180022f09  jnz     short loc_180022F16
0x180022f0b  mov     qword ptr [rbx+190h], 0
0x180022f16  mov     r8, [rcx+8]
0x180022f1a  cmp     rcx, [rbx+188h]
0x180022f21  jnz     short loc_180022F2E
0x180022f23  mov     rax, [rcx+18h]
0x180022f27  mov     [rbx+188h], rax
0x180022f2e  mov     rax, [rcx+10h]
0x180022f32  mov     [rbx+180h], rax
0x180022f39  mov     rdx, [rcx+10h]
0x180022f3d  test    rdx, rdx
0x180022f40  jz      short loc_180022F4A
0x180022f42  mov     rax, [rcx+18h]
0x180022f46  mov     [rdx+18h], rax
0x180022f4a  mov     rdx, [rcx+18h]
0x180022f4e  test    rdx, rdx
0x180022f51  jz      short loc_180022F5B
0x180022f53  mov     rax, [rcx+10h]
0x180022f57  mov     [rdx+10h], rax
0x180022f5b  mov     rax, [rbx+1A0h]
0x180022f62  mov     [rcx+10h], rax
0x180022f66  mov     [rbx+1A0h], rcx
0x180022f6d  add     [rbx+198h], edi
0x180022f73  test    r8, r8
0x180022f76  jz      loc_180022EF2
0x180022f7c  mov     rcx, r8; this
0x180022f7f  call    ?Release@CReadRequest@CMFSourceOutputPin@@UEAAKXZ; CMFSourceOutputPin::CReadRequest::Release(void)
0x180022f84  jmp     loc_180022EF2
0x180022f89  mov     rcx, [rbx+3C0h]
0x180022f90  test    rcx, rcx
0x180022f93  jz      loc_180023020
0x180022f99  cmp     [rbx+3D0h], rcx
0x180022fa0  jnz     short loc_180022FAD
0x180022fa2  mov     qword ptr [rbx+3D0h], 0
0x180022fad  mov     r8, [rcx+8]
0x180022fb1  cmp     rcx, [rbx+3C8h]
0x180022fb8  jnz     short loc_180022FC5
0x180022fba  mov     rax, [rcx+18h]
0x180022fbe  mov     [rbx+3C8h], rax
0x180022fc5  mov     rax, [rcx+10h]
0x180022fc9  mov     [rbx+3C0h], rax
0x180022fd0  mov     rdx, [rcx+10h]
0x180022fd4  test    rdx, rdx
0x180022fd7  jz      short loc_180022FE1
0x180022fd9  mov     rax, [rcx+18h]
0x180022fdd  mov     [rdx+18h], rax
0x180022fe1  mov     rdx, [rcx+18h]
0x180022fe5  test    rdx, rdx
0x180022fe8  jz      short loc_180022FF2
0x180022fea  mov     rax, [rcx+10h]
0x180022fee  mov     [rdx+10h], rax
0x180022ff2  mov     rax, [rbx+3E0h]
0x180022ff9  mov     [rcx+10h], rax
0x180022ffd  mov     [rbx+3E0h], rcx
0x180023004  add     [rbx+3D8h], edi
0x18002300a  test    r8, r8
0x18002300d  jz      loc_180022F89
0x180023013  mov     rcx, r8; this
0x180023016  call    ?Release@CReadRequest@CMFSourceOutputPin@@UEAAKXZ; CMFSourceOutputPin::CReadRequest::Release(void)
0x18002301b  jmp     loc_180022F89
0x180023020  mov     rcx, [rbx+640h]; this
0x180023027  test    rcx, rcx
0x18002302a  jz      short loc_18002303C
0x18002302c  call    ?Release@CReadRequest@CMFSourceOutputPin@@UEAAKXZ; CMFSourceOutputPin::CReadRequest::Release(void)
0x180023031  mov     qword ptr [rbx+640h], 0
0x18002303c  lea     rcx, [rbx+618h]; this
0x180023043  call    ??1CAMEvent@@QEAA@XZ; CAMEvent::~CAMEvent(void)
0x180023048  lea     rcx, [rbx+610h]; this
0x18002304f  call    ??1CAMEvent@@QEAA@XZ; CAMEvent::~CAMEvent(void)
0x180023054  lea     rcx, [rbx+608h]; this
0x18002305b  call    ??1CAMEvent@@QEAA@XZ; CAMEvent::~CAMEvent(void)
0x180023060  lea     rcx, [rbx+600h]; void *
0x180023067  call    ??1?$CComPtrBase@UIMediaSeeking@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(void)
0x18002306c  call    cs:__imp_GetProcessHeap
0x180023073  nop     dword ptr [rax+rax+00h]
0x180023078  mov     r8, [rbx+3E8h]; lpMem
0x18002307f  mov     rbp, rax
0x180023082  test    r8, r8
0x180023085  jz      short loc_1800230B6
0x180023087  lea     rsi, [rbx+3F8h]
0x18002308e  mov     rdi, [r8]
0x180023091  cmp     r8, rsi
0x180023094  jz      short loc_1800230A7
0x180023096  xor     edx, edx; dwFlags
0x180023098  mov     rcx, rbp; hHeap
0x18002309b  call    cs:__imp_HeapFree
0x1800230a2  nop     dword ptr [rax+rax+00h]
0x1800230a7  mov     [rbx+3E8h], rdi
0x1800230ae  mov     r8, rdi
0x1800230b1  test    rdi, rdi
0x1800230b4  jnz     short loc_18002308E
0x1800230b6  call    cs:__imp_GetProcessHeap
0x1800230bd  nop     dword ptr [rax+rax+00h]
0x1800230c2  mov     r8, [rbx+1A8h]; lpMem
0x1800230c9  mov     rbp, rax
0x1800230cc  test    r8, r8
0x1800230cf  jz      short loc_180023100
0x1800230d1  lea     rsi, [rbx+1B8h]
0x1800230d8  mov     rdi, [r8]
0x1800230db  cmp     r8, rsi
0x1800230de  jz      short loc_1800230F1
0x1800230e0  xor     edx, edx; dwFlags
0x1800230e2  mov     rcx, rbp; hHeap
0x1800230e5  call    cs:__imp_HeapFree
0x1800230ec  nop     dword ptr [rax+rax+00h]
0x1800230f1  mov     [rbx+1A8h], rdi
0x1800230f8  mov     r8, rdi
0x1800230fb  test    rdi, rdi
0x1800230fe  jnz     short loc_1800230D8
0x180023100  lea     rcx, [rbx+158h]; lpCriticalSection
0x180023107  call    cs:__imp_DeleteCriticalSection
0x18002310e  nop     dword ptr [rax+rax+00h]
0x180023113  lea     rcx, [rbx+150h]; this
0x18002311a  call    ??1CAMEvent@@QEAA@XZ; CAMEvent::~CAMEvent(void)
0x18002311f  lea     rcx, [rbx+128h]; lpCriticalSection
0x180023126  call    cs:__imp_DeleteCriticalSection
0x18002312d  nop     dword ptr [rax+rax+00h]
0x180023132  lea     rcx, [rbx+8]; this
0x180023136  add     rsp, 20h
0x18002313a  pop     r14
0x18002313c  pop     rdi
0x18002313d  pop     rsi
0x18002313e  pop     rbp
0x18002313f  pop     rbx
0x180023140  jmp     ??1CBasePin@@UEAA@XZ; CBasePin::~CBasePin(void)
```
