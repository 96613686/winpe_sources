# CMFSourceMPEG2TSPin::_SyncRead(__int64 const &,ulong,uchar *)

- ea: `0x180065880`
- end: `0x180065bea`
- name: `?_SyncRead@CMFSourceMPEG2TSPin@@IEAAJAEB_JKPEAE@Z`
- size: `874`
- prototype: `__int64 __fastcall(CMFSourceMPEG2TSPin *__hidden this, const __int64 *, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180038720`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x1800227e0`
- `0x180032a50`
- `0x180051ce4`
- `0x180065880`
- `0x180074160`
- `0x180091594`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180065aaa`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180065aaa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006592c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800659fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065b12`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006592c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800659fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065b12`
- `MFPlat!MFCreateAsyncResult` at `0x18006590a`
- `MFPlat!MFCreateAsyncResult` at `0x18006590a`

## string_xrefs

- `0x1800658a4`: `CMFSourceMPEG2TSPin::_SyncRead`
- `0x180065989`: `CMFSourceMPEG2TSPin::_SyncRead`
- `0x180065a57`: `CMFSourceMPEG2TSPin::_SyncRead`
- `0x180065b6f`: `CMFSourceMPEG2TSPin::_SyncRead`

## pseudocode

```c
__int64 __fastcall CMFSourceMPEG2TSPin::_SyncRead(
        CMFSourceMPEG2TSPin *this,
        const __int64 *a2,
        unsigned int a3,
        unsigned __int8 *a4)
{
  HRESULT v8; // ebx
  __int64 v9; // rcx
  CallStackTracing *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rdx
  CallStackTracing *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rax
  IMFAsyncResult *v18; // r10
  CallStackTracing *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  _BYTE v23[8]; // [rsp+30h] [rbp-48h] BYREF
  IMFAsyncResult *ppAsyncResult; // [rsp+38h] [rbp-40h] BYREF
  __int64 v25; // [rsp+40h] [rbp-38h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v23, "CMFSourceMPEG2TSPin::_SyncRead", 4572);
  ppAsyncResult = 0;
  v25 = 0;
  if ( !a4 )
  {
    v8 = -2147024809;
LABEL_41:
    *((_DWORD *)this + 134) = 0;
    goto LABEL_42;
  }
  v9 = *((_QWORD *)this + 56);
  if ( *(_DWORD *)(v9 + 208) )
  {
    v8 = -2147467259;
    goto LABEL_41;
  }
  v8 = MFCreateAsyncResult(*(IUnknown **)(v9 + 216), 0, 0, &ppAsyncResult);
  if ( v8 < 0 )
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFSourceMPEG2TSPin::_SyncRead", 4597, v8);
    }
    if ( !g_wppLevels )
      goto LABEL_41;
    v13 = 81;
    goto LABEL_40;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int64 *))(**(_QWORD **)(*((_QWORD *)this + 56)
                                                                                           + 216LL)
                                                                             + 120LL))(
         *(_QWORD *)(*((_QWORD *)this + 56) + 216LL),
         0,
         *a2,
         1,
         &v25);
  if ( v8 < 0 )
  {
    v14 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v14 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v14 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      v16 = CallStackTracing::GetThreadRelativeContext(v14);
      if ( *((_DWORD *)v16 + 499) != v8 )
        CallStackContext::TraceFailure(v16, "CMFSourceMPEG2TSPin::_SyncRead", 4600, v8);
    }
    if ( !g_wppLevels )
      goto LABEL_41;
    v13 = 82;
    goto LABEL_40;
  }
  if ( *((_DWORD *)this + 138) )
  {
    *((_DWORD *)this + 138) = 0;
    CMFSourceMPEG2TSPin::_EnableBuffering(this, 1);
  }
  ResetEvent(*((HANDLE *)this + 66));
  v17 = *((_QWORD *)this + 56);
  v18 = ppAsyncResult;
  *(_QWORD *)((char *)this + 540) = 0;
  *((_DWORD *)this + 134) = 1;
  v8 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, char *, IMFAsyncResult *))(**(_QWORD **)(v17 + 216)
                                                                                              + 80LL))(
         *(_QWORD *)(v17 + 216),
         a4,
         a3,
         (char *)this + 432,
         v18);
  if ( v8 < 0 )
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
      if ( *((_DWORD *)v21 + 499) != v8 )
        CallStackContext::TraceFailure(v21, "CMFSourceMPEG2TSPin::_SyncRead", 4616, v8);
    }
    if ( !g_wppLevels )
      goto LABEL_41;
    v13 = 83;
LABEL_40:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids, this, v8);
    goto LABEL_41;
  }
LABEL_42:
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppAsyncResult);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v23);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180065880  push    rbx
0x180065882  push    rbp
0x180065883  push    rdi
0x180065884  push    r14
0x180065886  push    r15
0x180065888  sub     rsp, 50h
0x18006588c  mov     rax, cs:__security_cookie
0x180065893  xor     rax, rsp
0x180065896  mov     [rsp+78h+var_30], rax
0x18006589b  mov     r15d, r8d
0x18006589e  mov     r14, rdx
0x1800658a1  mov     rdi, rcx
0x1800658a4  lea     rdx, aCmfsourcempeg2_7; "CMFSourceMPEG2TSPin::_SyncRead"
0x1800658ab  mov     r8d, 11DCh; int
0x1800658b1  lea     rcx, [rsp+78h+var_48]; this
0x1800658b6  mov     rbp, r9
0x1800658b9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800658be  mov     [rsp+78h+ppAsyncResult], 0
0x1800658c7  mov     [rsp+78h+var_38], 0
0x1800658d0  test    rbp, rbp
0x1800658d3  jnz     short loc_1800658DF
0x1800658d5  mov     ebx, 80070057h
0x1800658da  jmp     loc_180065BB0
0x1800658df  mov     rcx, [rdi+1C0h]
0x1800658e6  cmp     dword ptr [rcx+0D0h], 0
0x1800658ed  jz      short loc_1800658F9
0x1800658ef  mov     ebx, 80004005h
0x1800658f4  jmp     loc_180065BB0
0x1800658f9  mov     rcx, [rcx+0D8h]; punkObject
0x180065900  lea     r9, [rsp+78h+ppAsyncResult]; ppAsyncResult
0x180065905  xor     r8d, r8d; punkState
0x180065908  xor     edx, edx; pCallback
0x18006590a  call    cs:__imp_MFCreateAsyncResult
0x180065911  nop     dword ptr [rax+rax+00h]
0x180065916  mov     ebx, eax
0x180065918  test    eax, eax
0x18006591a  jns     loc_1800659B5
0x180065920  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065927  test    rcx, rcx
0x18006592a  jnz     short loc_180065973
0x18006592c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180065933  nop     dword ptr [rax+rax+00h]
0x180065938  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006593f  mov     rcx, rax
0x180065942  test    rax, rax
0x180065945  jz      short loc_180065965
0x180065947  mov     rax, [rax]
0x18006594a  mov     edx, 7F0h
0x18006594f  mov     rax, [rax+8]
0x180065953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065958  test    eax, eax
0x18006595a  jz      short loc_180065965
0x18006595c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065963  jmp     short loc_180065973
0x180065965  lea     rcx, qword_1800EB130; this
0x18006596c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180065973  cmp     byte ptr [rcx+8], 0
0x180065977  jz      short loc_18006599E
0x180065979  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006597e  cmp     [rax+7CCh], ebx
0x180065984  jz      short loc_18006599E
0x180065986  mov     r9d, ebx; int
0x180065989  lea     rdx, aCmfsourcempeg2_7; "CMFSourceMPEG2TSPin::_SyncRead"
0x180065990  mov     r8d, 11F5h; int
0x180065996  mov     rcx, rax; this
0x180065999  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006599e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800659a5  jb      loc_180065BB0
0x1800659ab  mov     edx, 51h ; 'Q'
0x1800659b0  jmp     loc_180065B92
0x1800659b5  mov     rax, [rdi+1C0h]
0x1800659bc  lea     rdx, [rsp+78h+var_38]
0x1800659c1  mov     r8, [r14]
0x1800659c4  mov     r9d, 1
0x1800659ca  mov     [rsp+78h+var_58], rdx
0x1800659cf  xor     edx, edx
0x1800659d1  mov     rcx, [rax+0D8h]
0x1800659d8  mov     rax, [rcx]
0x1800659db  mov     rax, [rax+78h]
0x1800659df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800659e4  mov     ebx, eax
0x1800659e6  test    eax, eax
0x1800659e8  jns     loc_180065A83
0x1800659ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800659f5  test    rcx, rcx
0x1800659f8  jnz     short loc_180065A41
0x1800659fa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180065a01  nop     dword ptr [rax+rax+00h]
0x180065a06  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180065a0d  mov     rcx, rax
0x180065a10  test    rax, rax
0x180065a13  jz      short loc_180065A33
0x180065a15  mov     rax, [rax]
0x180065a18  mov     edx, 7F0h
0x180065a1d  mov     rax, [rax+8]
0x180065a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065a26  test    eax, eax
0x180065a28  jz      short loc_180065A33
0x180065a2a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065a31  jmp     short loc_180065A41
0x180065a33  lea     rcx, qword_1800EB130; this
0x180065a3a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180065a41  cmp     byte ptr [rcx+8], 0
0x180065a45  jz      short loc_180065A6C
0x180065a47  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180065a4c  cmp     [rax+7CCh], ebx
0x180065a52  jz      short loc_180065A6C
0x180065a54  mov     r9d, ebx; int
0x180065a57  lea     rdx, aCmfsourcempeg2_7; "CMFSourceMPEG2TSPin::_SyncRead"
0x180065a5e  mov     r8d, 11F8h; int
0x180065a64  mov     rcx, rax; this
0x180065a67  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180065a6c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065a73  jb      loc_180065BB0
0x180065a79  mov     edx, 52h ; 'R'
0x180065a7e  jmp     loc_180065B92
0x180065a83  cmp     dword ptr [rdi+228h], 0
0x180065a8a  jz      short loc_180065AA3
0x180065a8c  mov     edx, 1; int
0x180065a91  mov     dword ptr [rdi+228h], 0
0x180065a9b  mov     rcx, rdi; this
0x180065a9e  call    ?_EnableBuffering@CMFSourceMPEG2TSPin@@IEAAJH@Z; CMFSourceMPEG2TSPin::_EnableBuffering(int)
0x180065aa3  mov     rcx, [rdi+210h]; hEvent
0x180065aaa  call    cs:__imp_ResetEvent
0x180065ab1  nop     dword ptr [rax+rax+00h]
0x180065ab6  mov     rax, [rdi+1C0h]
0x180065abd  lea     r9, [rdi+1B0h]
0x180065ac4  mov     r10, [rsp+78h+ppAsyncResult]
0x180065ac9  mov     r8d, r15d
0x180065acc  mov     qword ptr [rdi+21Ch], 0
0x180065ad7  mov     rdx, rbp
0x180065ada  mov     dword ptr [rdi+218h], 1
0x180065ae4  mov     rcx, [rax+0D8h]
0x180065aeb  mov     [rsp+78h+var_58], r10
0x180065af0  mov     rax, [rcx]
0x180065af3  mov     rax, [rax+50h]
0x180065af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065afc  mov     ebx, eax
0x180065afe  test    eax, eax
0x180065b00  jns     loc_180065BBA
0x180065b06  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065b0d  test    rcx, rcx
0x180065b10  jnz     short loc_180065B59
0x180065b12  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180065b19  nop     dword ptr [rax+rax+00h]
0x180065b1e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180065b25  mov     rcx, rax
0x180065b28  test    rax, rax
0x180065b2b  jz      short loc_180065B4B
0x180065b2d  mov     rax, [rax]
0x180065b30  mov     edx, 7F0h
0x180065b35  mov     rax, [rax+8]
0x180065b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065b3e  test    eax, eax
0x180065b40  jz      short loc_180065B4B
0x180065b42  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065b49  jmp     short loc_180065B59
0x180065b4b  lea     rcx, qword_1800EB130; this
0x180065b52  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180065b59  cmp     byte ptr [rcx+8], 0
0x180065b5d  jz      short loc_180065B84
0x180065b5f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180065b64  cmp     [rax+7CCh], ebx
0x180065b6a  jz      short loc_180065B84
0x180065b6c  mov     r9d, ebx; int
0x180065b6f  lea     rdx, aCmfsourcempeg2_7; "CMFSourceMPEG2TSPin::_SyncRead"
0x180065b76  mov     r8d, 1208h; int
0x180065b7c  mov     rcx, rax; this
0x180065b7f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180065b84  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065b8b  jb      short loc_180065BB0
0x180065b8d  mov     edx, 53h ; 'S'
0x180065b92  mov     rcx, cs:WPP_GLOBAL_Control
0x180065b99  lea     r8, WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids
0x180065ba0  mov     r9, rdi
0x180065ba3  mov     dword ptr [rsp+78h+var_58], ebx
0x180065ba7  mov     rcx, [rcx+10h]
0x180065bab  call    WPP_SF_qD
0x180065bb0  mov     dword ptr [rdi+218h], 0
0x180065bba  lea     rcx, [rsp+78h+ppAsyncResult]; void *
0x180065bbf  call    ??1?$CComPtrBase@UIMediaSeeking@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(void)
0x180065bc4  lea     rcx, [rsp+78h+var_48]; this
0x180065bc9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180065bce  mov     eax, ebx
0x180065bd0  mov     rcx, [rsp+78h+var_30]
0x180065bd5  xor     rcx, rsp; StackCookie
0x180065bd8  call    __security_check_cookie
0x180065bdd  add     rsp, 50h
0x180065be1  pop     r15
0x180065be3  pop     r14
0x180065be5  pop     rdi
0x180065be6  pop     rbp
0x180065be7  pop     rbx
0x180065be8  retn
```
