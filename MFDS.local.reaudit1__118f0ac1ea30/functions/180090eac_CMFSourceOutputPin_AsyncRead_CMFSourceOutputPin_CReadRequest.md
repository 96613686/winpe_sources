# CMFSourceOutputPin::_AsyncRead(CMFSourceOutputPin::CReadRequest *)

- ea: `0x180090eac`
- end: `0x1800913ba`
- name: `?_AsyncRead@CMFSourceOutputPin@@IEAAJPEAVCReadRequest@1@@Z`
- size: `1294`
- prototype: `__int64 __fastcall(CMFSourceOutputPin *__hidden this, IUnknown *punkObject)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180057070`
- `0x1800913c0`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x1800227e0`
- `0x180032a50`
- `0x180051ce4`
- `0x180074160`
- `0x180090eac`
- `0x180091618`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180091270`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180091270`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180091353`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180091353`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180091376`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180091385`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180091376`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180091385`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180090ee1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180090ef7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180090ee1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180090ef7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180090f49`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009101b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800910dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009118c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800912bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180090f49`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009101b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800910dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009118c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800912bf`
- `MFPlat!MFCreateAsyncResult` at `0x180090ff9`
- `MFPlat!MFCreateAsyncResult` at `0x180090ff9`

## string_xrefs

- `0x180090f06`: `CMFSourceOutputPin::_AsyncRead`

## pseudocode

```c
__int64 __fastcall CMFSourceOutputPin::_AsyncRead(CMFSourceOutputPin *this, IUnknown *punkObject)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  CallStackTracing *v5; // rcx
  HRESULT v6; // ebx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  CallStackTracing *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  CallStackTracing *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  CallStackTracing *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  CallStackTracing *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  void *v22; // rcx
  _BYTE v24[8]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v25; // [rsp+38h] [rbp-50h] BYREF
  IMFAsyncResult *ppAsyncResult; // [rsp+40h] [rbp-48h] BYREF
  __int64 v27; // [rsp+48h] [rbp-40h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 296);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 344));
  ppAsyncResult = 0;
  v27 = 0;
  v25 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v24, "CMFSourceOutputPin::_AsyncRead", 2447);
  if ( !punkObject )
  {
    v5 = CallStackTracing::s_wpInstance;
    v6 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v5 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v5);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFSourceOutputPin::_AsyncRead", 2447, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_63;
    v9 = 31;
    goto LABEL_12;
  }
  v6 = MFCreateAsyncResult(punkObject, 0, 0, &ppAsyncResult);
  if ( v6 < 0 )
  {
    v10 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext(v10);
      if ( *((_DWORD *)v12 + 499) != v6 )
        CallStackContext::TraceFailure(v12, "CMFSourceOutputPin::_AsyncRead", 2451, v6);
    }
    if ( !g_wppLevels )
      goto LABEL_63;
    v9 = 32;
    goto LABEL_12;
  }
  v6 = (*((__int64 (__fastcall **)(struct IUnknownVtbl *, _QWORD, struct IUnknownVtbl *, __int64, __int64 *))punkObject[6].lpVtbl->QueryInterface
        + 15))(
         punkObject[6].lpVtbl,
         0,
         punkObject[2].lpVtbl,
         1,
         &v27);
  if ( v6 < 0 )
  {
    v13 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext(v13);
      if ( *((_DWORD *)v15 + 499) != v6 )
        CallStackContext::TraceFailure(v15, "CMFSourceOutputPin::_AsyncRead", 2453, v6);
    }
    if ( !g_wppLevels )
      goto LABEL_63;
    v9 = 33;
    goto LABEL_12;
  }
  v6 = (*((__int64 (__fastcall **)(struct IUnknownVtbl *, __int64 *))punkObject[1].lpVtbl->QueryInterface + 3))(
         punkObject[1].lpVtbl,
         &v25);
  if ( v6 < 0 )
  {
    v16 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v16 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v18 = CallStackTracing::GetThreadRelativeContext(v16);
      if ( *((_DWORD *)v18 + 499) != v6 )
        CallStackContext::TraceFailure(v18, "CMFSourceOutputPin::_AsyncRead", 2457, v6);
    }
    if ( !g_wppLevels )
      goto LABEL_63;
    v9 = 34;
    goto LABEL_12;
  }
  if ( !LODWORD(punkObject[3].lpVtbl)
    || LODWORD(punkObject[3].lpVtbl) > (*((unsigned int (__fastcall **)(struct IUnknownVtbl *))punkObject[1].lpVtbl->QueryInterface
                                        + 4))(punkObject[1].lpVtbl)
    || (*((int (__fastcall **)(struct IUnknownVtbl *))punkObject[1].lpVtbl->QueryInterface + 4))(punkObject[1].lpVtbl) < 0 )
  {
    v6 = -2147418113;
    goto LABEL_63;
  }
  if ( *((_DWORD *)this + 398) )
  {
    *((_DWORD *)this + 398) = 0;
    CMFSourceOutputPin::_EnableBuffering(this, 1);
  }
  ResetEvent(*((HANDLE *)this + 42));
  v6 = (*((__int64 (__fastcall **)(struct IUnknownVtbl *, __int64, _QWORD, char *, IMFAsyncResult *))punkObject[6].lpVtbl->QueryInterface
        + 10))(
         punkObject[6].lpVtbl,
         v25,
         LODWORD(punkObject[3].lpVtbl),
         (char *)this + 280,
         ppAsyncResult);
  if ( v6 < 0 )
  {
    v19 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
      {
        v19 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v19 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext(v19);
      if ( *((_DWORD *)v21 + 499) != v6 )
        CallStackContext::TraceFailure(v21, "CMFSourceOutputPin::_AsyncRead", 2481, v6);
    }
    if ( !g_wppLevels )
      goto LABEL_63;
    v9 = 35;
LABEL_12:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids, this, v6);
LABEL_63:
    v22 = (void *)*((_QWORD *)this + 42);
    *((_DWORD *)this + 394) = 0;
    SetEvent(v22);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v24);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppAsyncResult);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 344));
  LeaveCriticalSection(v2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180090eac  mov     [rsp+arg_10], rbx
0x180090eb1  mov     [rsp+arg_18], rbp
0x180090eb6  push    rsi
0x180090eb7  push    rdi
0x180090eb8  push    r12
0x180090eba  push    r14
0x180090ebc  push    r15
0x180090ebe  sub     rsp, 60h
0x180090ec2  mov     rax, cs:__security_cookie
0x180090ec9  xor     rax, rsp
0x180090ecc  mov     [rsp+88h+var_38], rax
0x180090ed1  lea     rbp, [rcx+128h]
0x180090ed8  mov     rdi, rcx
0x180090edb  mov     rcx, rbp; lpCriticalSection
0x180090ede  mov     rsi, rdx
0x180090ee1  call    cs:__imp_EnterCriticalSection
0x180090ee8  nop     dword ptr [rax+rax+00h]
0x180090eed  lea     r14, [rdi+158h]
0x180090ef4  mov     rcx, r14; lpCriticalSection
0x180090ef7  call    cs:__imp_EnterCriticalSection
0x180090efe  nop     dword ptr [rax+rax+00h]
0x180090f03  xor     r15d, r15d
0x180090f06  lea     r12, aCmfsourceoutpu; "CMFSourceOutputPin::_AsyncRead"
0x180090f0d  mov     rdx, r12; char *
0x180090f10  mov     [rsp+88h+ppAsyncResult], r15
0x180090f15  mov     r8d, 98Fh; int
0x180090f1b  mov     [rsp+88h+var_40], r15
0x180090f20  lea     rcx, [rsp+88h+var_58]; this
0x180090f25  mov     [rsp+88h+var_50], r15
0x180090f2a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180090f2f  test    rsi, rsi
0x180090f32  jnz     loc_180090FEC
0x180090f38  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180090f3f  mov     ebx, 80070057h
0x180090f44  test    rcx, rcx
0x180090f47  jnz     short loc_180090F90
0x180090f49  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180090f50  nop     dword ptr [rax+rax+00h]
0x180090f55  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180090f5c  mov     rcx, rax
0x180090f5f  test    rax, rax
0x180090f62  jz      short loc_180090F82
0x180090f64  mov     rax, [rax]
0x180090f67  mov     edx, 7F0h
0x180090f6c  mov     rax, [rax+8]
0x180090f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090f75  test    eax, eax
0x180090f77  jz      short loc_180090F82
0x180090f79  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180090f80  jmp     short loc_180090F90
0x180090f82  lea     rcx, qword_1800EB130; this
0x180090f89  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180090f90  cmp     [rcx+8], r15b
0x180090f94  jz      short loc_180090FB7
0x180090f96  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180090f9b  cmp     [rax+7CCh], ebx
0x180090fa1  jz      short loc_180090FB7
0x180090fa3  mov     r9d, ebx; int
0x180090fa6  mov     r8d, 98Fh; int
0x180090fac  mov     rdx, r12; char *
0x180090faf  mov     rcx, rax; this
0x180090fb2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180090fb7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180090fbe  jb      loc_180091345
0x180090fc4  mov     edx, 1Fh
0x180090fc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180090fd0  lea     r8, WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids
0x180090fd7  mov     r9, rdi
0x180090fda  mov     dword ptr [rsp+88h+var_68], ebx
0x180090fde  mov     rcx, [rcx+10h]
0x180090fe2  call    WPP_SF_qD
0x180090fe7  jmp     loc_180091345
0x180090fec  lea     r9, [rsp+88h+ppAsyncResult]; ppAsyncResult
0x180090ff1  xor     r8d, r8d; punkState
0x180090ff4  xor     edx, edx; pCallback
0x180090ff6  mov     rcx, rsi; punkObject
0x180090ff9  call    cs:__imp_MFCreateAsyncResult
0x180091000  nop     dword ptr [rax+rax+00h]
0x180091005  mov     ebx, eax
0x180091007  test    eax, eax
0x180091009  jns     loc_1800910A0
0x18009100f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180091016  test    rcx, rcx
0x180091019  jnz     short loc_180091062
0x18009101b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180091022  nop     dword ptr [rax+rax+00h]
0x180091027  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009102e  mov     rcx, rax
0x180091031  test    rax, rax
0x180091034  jz      short loc_180091054
0x180091036  mov     rax, [rax]
0x180091039  mov     edx, 7F0h
0x18009103e  mov     rax, [rax+8]
0x180091042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091047  test    eax, eax
0x180091049  jz      short loc_180091054
0x18009104b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180091052  jmp     short loc_180091062
0x180091054  lea     rcx, qword_1800EB130; this
0x18009105b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180091062  cmp     [rcx+8], r15b
0x180091066  jz      short loc_180091089
0x180091068  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009106d  cmp     [rax+7CCh], ebx
0x180091073  jz      short loc_180091089
0x180091075  mov     r9d, ebx; int
0x180091078  mov     r8d, 993h; int
0x18009107e  mov     rdx, r12; char *
0x180091081  mov     rcx, rax; this
0x180091084  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180091089  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180091090  jb      loc_180091345
0x180091096  mov     edx, 20h ; ' '
0x18009109b  jmp     loc_180090FC9
0x1800910a0  mov     rcx, [rsi+30h]
0x1800910a4  lea     rdx, [rsp+88h+var_40]
0x1800910a9  mov     r8, [rsi+10h]
0x1800910ad  mov     r9d, 1
0x1800910b3  mov     [rsp+88h+var_68], rdx
0x1800910b8  xor     edx, edx
0x1800910ba  mov     rax, [rcx]
0x1800910bd  mov     rax, [rax+78h]
0x1800910c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800910c6  mov     ebx, eax
0x1800910c8  test    eax, eax
0x1800910ca  jns     loc_180091161
0x1800910d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800910d7  test    rcx, rcx
0x1800910da  jnz     short loc_180091123
0x1800910dc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800910e3  nop     dword ptr [rax+rax+00h]
0x1800910e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800910ef  mov     rcx, rax
0x1800910f2  test    rax, rax
0x1800910f5  jz      short loc_180091115
0x1800910f7  mov     rax, [rax]
0x1800910fa  mov     edx, 7F0h
0x1800910ff  mov     rax, [rax+8]
0x180091103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091108  test    eax, eax
0x18009110a  jz      short loc_180091115
0x18009110c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180091113  jmp     short loc_180091123
0x180091115  lea     rcx, qword_1800EB130; this
0x18009111c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180091123  cmp     [rcx+8], r15b
0x180091127  jz      short loc_18009114A
0x180091129  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009112e  cmp     [rax+7CCh], ebx
0x180091134  jz      short loc_18009114A
0x180091136  mov     r9d, ebx; int
0x180091139  mov     r8d, 995h; int
0x18009113f  mov     rdx, r12; char *
0x180091142  mov     rcx, rax; this
0x180091145  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009114a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180091151  jb      loc_180091345
0x180091157  mov     edx, 21h ; '!'
0x18009115c  jmp     loc_180090FC9
0x180091161  mov     rcx, [rsi+8]
0x180091165  lea     rdx, [rsp+88h+var_50]
0x18009116a  mov     rax, [rcx]
0x18009116d  mov     rax, [rax+18h]
0x180091171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091176  mov     ebx, eax
0x180091178  test    eax, eax
0x18009117a  jns     loc_180091211
0x180091180  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180091187  test    rcx, rcx
0x18009118a  jnz     short loc_1800911D3
0x18009118c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180091193  nop     dword ptr [rax+rax+00h]
0x180091198  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009119f  mov     rcx, rax
0x1800911a2  test    rax, rax
0x1800911a5  jz      short loc_1800911C5
0x1800911a7  mov     rax, [rax]
0x1800911aa  mov     edx, 7F0h
0x1800911af  mov     rax, [rax+8]
0x1800911b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800911b8  test    eax, eax
0x1800911ba  jz      short loc_1800911C5
0x1800911bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800911c3  jmp     short loc_1800911D3
0x1800911c5  lea     rcx, qword_1800EB130; this
0x1800911cc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800911d3  cmp     [rcx+8], r15b
0x1800911d7  jz      short loc_1800911FA
0x1800911d9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800911de  cmp     [rax+7CCh], ebx
0x1800911e4  jz      short loc_1800911FA
0x1800911e6  mov     r9d, ebx; int
0x1800911e9  mov     r8d, 999h; int
0x1800911ef  mov     rdx, r12; char *
0x1800911f2  mov     rcx, rax; this
0x1800911f5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800911fa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180091201  jb      loc_180091345
0x180091207  mov     edx, 22h ; '"'
0x18009120c  jmp     loc_180090FC9
0x180091211  cmp     [rsi+18h], r15d
0x180091215  jz      loc_180091340
0x18009121b  mov     rcx, [rsi+8]
0x18009121f  mov     rax, [rcx]
0x180091222  mov     rax, [rax+20h]
0x180091226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009122b  cmp     [rsi+18h], eax
0x18009122e  ja      loc_180091340
0x180091234  mov     rcx, [rsi+8]
0x180091238  mov     rax, [rcx]
0x18009123b  mov     rax, [rax+20h]
0x18009123f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091244  test    eax, eax
0x180091246  js      loc_180091340
0x18009124c  cmp     [rdi+638h], r15d
0x180091253  jz      short loc_180091269
0x180091255  mov     edx, 1; int
0x18009125a  mov     [rdi+638h], r15d
0x180091261  mov     rcx, rdi; this
0x180091264  call    ?_EnableBuffering@CMFSourceOutputPin@@IEAAJH@Z; CMFSourceOutputPin::_EnableBuffering(int)
0x180091269  mov     rcx, [rdi+150h]; hEvent
0x180091270  call    cs:__imp_ResetEvent
0x180091277  nop     dword ptr [rax+rax+00h]
0x18009127c  mov     r10, [rsi+30h]
0x180091280  lea     r9, [rdi+118h]
0x180091287  mov     rcx, [rsp+88h+ppAsyncResult]
0x18009128c  mov     r8d, [rsi+18h]
0x180091290  mov     rdx, [rsp+88h+var_50]
0x180091295  mov     rax, [r10]
0x180091298  mov     [rsp+88h+var_68], rcx
0x18009129d  mov     rcx, r10
0x1800912a0  mov     rax, [rax+50h]
0x1800912a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800912a9  mov     ebx, eax
0x1800912ab  test    eax, eax
0x1800912ad  jns     loc_18009135F
0x1800912b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800912ba  test    rcx, rcx
0x1800912bd  jnz     short loc_180091306
0x1800912bf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800912c6  nop     dword ptr [rax+rax+00h]
0x1800912cb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800912d2  mov     rcx, rax
0x1800912d5  test    rax, rax
0x1800912d8  jz      short loc_1800912F8
0x1800912da  mov     rax, [rax]
0x1800912dd  mov     edx, 7F0h
0x1800912e2  mov     rax, [rax+8]
0x1800912e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800912eb  test    eax, eax
0x1800912ed  jz      short loc_1800912F8
0x1800912ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800912f6  jmp     short loc_180091306
0x1800912f8  lea     rcx, qword_1800EB130; this
0x1800912ff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180091306  cmp     [rcx+8], r15b
0x18009130a  jz      short loc_18009132D
0x18009130c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180091311  cmp     [rax+7CCh], ebx
0x180091317  jz      short loc_18009132D
0x180091319  mov     r9d, ebx; int
0x18009131c  mov     r8d, 9B1h; int
0x180091322  mov     rdx, r12; char *
0x180091325  mov     rcx, rax; this
0x180091328  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009132d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180091334  jb      short loc_180091345
0x180091336  mov     edx, 23h ; '#'
0x18009133b  jmp     loc_180090FC9
0x180091340  mov     ebx, 8000FFFFh
0x180091345  mov     rcx, [rdi+150h]; hEvent
0x18009134c  mov     [rdi+628h], r15d
0x180091353  call    cs:__imp_SetEvent
0x18009135a  nop     dword ptr [rax+rax+00h]
0x18009135f  lea     rcx, [rsp+88h+var_58]; this
0x180091364  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180091369  lea     rcx, [rsp+88h+ppAsyncResult]; void *
0x18009136e  call    ??1?$CComPtrBase@UIMediaSeeking@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(void)
0x180091373  mov     rcx, r14; lpCriticalSection
0x180091376  call    cs:__imp_LeaveCriticalSection
0x18009137d  nop     dword ptr [rax+rax+00h]
0x180091382  mov     rcx, rbp; lpCriticalSection
0x180091385  call    cs:__imp_LeaveCriticalSection
0x18009138c  nop     dword ptr [rax+rax+00h]
0x180091391  mov     eax, ebx
0x180091393  mov     rcx, [rsp+88h+var_38]
0x180091398  xor     rcx, rsp; StackCookie
0x18009139b  call    __security_check_cookie
0x1800913a0  lea     r11, [rsp+88h+var_28]
0x1800913a5  mov     rbx, [r11+40h]
0x1800913a9  mov     rbp, [r11+48h]
0x1800913ad  mov     rsp, r11
0x1800913b0  pop     r15
0x1800913b2  pop     r14
0x1800913b4  pop     r12
0x1800913b6  pop     rdi
0x1800913b7  pop     rsi
0x1800913b8  retn
```
