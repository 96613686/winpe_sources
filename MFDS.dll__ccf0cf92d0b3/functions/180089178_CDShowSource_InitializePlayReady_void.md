# CDShowSource::InitializePlayReady(void)

- ea: `0x180089178`
- end: `0x1800897ba`
- name: `?InitializePlayReady@CDShowSource@@IEAAJXZ`
- size: `1602`
- prototype: `__int64 __fastcall(CDShowSource *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180065bf0`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x1800227e0`
- `0x180032570`
- `0x180032988`
- `0x180032a50`
- `0x180051ce4`
- `0x18006d408`
- `0x180073d4c`
- `0x180074160`
- `0x180089178`
- `0x18008ae70`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800895e2`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800895e2`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180089451`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180089451`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180089502`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180089502`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180089765`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180089765`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008924b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089314`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800893c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008947a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089536`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089604`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800896ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008924b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089314`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800893c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008947a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089536`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089604`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800896ca`

## string_xrefs

- `0x180089199`: `CDShowSource::InitializePlayReady`

## pseudocode

```c
__int64 __fastcall CDShowSource::InitializePlayReady(CDShowSource *this)
{
  __int64 *v2; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v4; // ebx
  __int128 *v5; // rax
  __int128 v6; // xmm0
  errno_t v7; // ebx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  rsize_t v17; // rbx
  HGLOBAL v18; // rax
  void *v19; // rdi
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  void *v23; // rax
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  _BYTE v35[4]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int dwBytes[3]; // [rsp+34h] [rbp-44h] BYREF
  LPSTREAM ppstm; // [rsp+40h] [rbp-38h] BYREF
  struct IUnknown *v38; // [rsp+48h] [rbp-30h] BYREF
  void *v39; // [rsp+50h] [rbp-28h] BYREF
  _BYTE v40[16]; // [rsp+58h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v35, "CDShowSource::InitializePlayReady", 961);
  v2 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 137) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 137) + 296LL))(*((_QWORD *)this + 137));
    v5 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 137) + 280LL))(
                       *((_QWORD *)this + 137),
                       v40);
    v2 = (__int64 *)CallStackTracing::s_wpInstance;
    v6 = *v5;
    *((_DWORD *)ThreadRelativeContext + 504) = v4;
    *((_OWORD *)ThreadRelativeContext + 125) = v6;
  }
  v39 = 0;
  memset(dwBytes, 0, sizeof(dwBytes));
  v38 = 0;
  ppstm = 0;
  if ( !*((_DWORD *)this + 259) )
  {
    v7 = -1072860801;
    if ( !v2 )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v2 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v2 = &qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v2 + 8) )
    {
      v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v2);
      if ( *((_DWORD *)v9 + 499) != -1072860801 )
        CallStackContext::TraceFailure(v9, "CDShowSource::InitializePlayReady", 974, -1072860801);
    }
    if ( g_wppLevels )
    {
      v10 = 97;
LABEL_15:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids, this, v7);
      goto LABEL_85;
    }
    goto LABEL_85;
  }
  v7 = CDShowSource::BuildStreamInfo(this, (unsigned __int8 **)&dwBytes[1], dwBytes);
  if ( v7 >= 0 )
  {
    v7 = CGITPtr::Get((CDShowSource *)((char *)this + 1036), &GUID_f70ca1a9_fdc7_4782_b994_adffb1c98606, &v39);
    if ( v7 < 0 )
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)v16 + 499) != v7 )
          CallStackContext::TraceFailure(v16, "CDShowSource::InitializePlayReady", 979, v7);
      }
      if ( g_wppLevels )
      {
        v10 = 99;
        goto LABEL_15;
      }
      goto LABEL_85;
    }
    v17 = dwBytes[0];
    v18 = GlobalAlloc(2u, dwBytes[0]);
    v19 = v18;
    if ( !v18 )
    {
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      v7 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)v22 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v22, "CDShowSource::InitializePlayReady", 983, -2147024882);
      }
      if ( g_wppLevels )
      {
        v10 = 100;
        goto LABEL_15;
      }
      goto LABEL_85;
    }
    v23 = GlobalLock(v18);
    v7 = memcpy_s_0(v23, v17, *(const void *const *)&dwBytes[1], v17);
    if ( v7 >= 0 )
    {
      v7 = CreateStreamOnHGlobal(v19, 0, &ppstm);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(void *, GUID *, LPSTREAM, GUID *, struct IUnknown **))(*(_QWORD *)v39 + 40LL))(
               v39,
               &CLSID_PlayReadyTrustedInput,
               ppstm,
               &IID_IMFTrustedInput,
               &v38);
        if ( v7 >= 0 )
        {
          CGITPtr::Set((CDShowSource *)((char *)this + 1040), &GUID_542612c4_a1b8_4632_b521_de11ea64a0b0, v38);
          goto LABEL_84;
        }
        v31 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v32;
          if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
          {
            v31 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v31 = &qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v31 + 8) )
        {
          v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
          if ( *((_DWORD *)v33 + 499) != v7 )
            CallStackContext::TraceFailure(v33, "CDShowSource::InitializePlayReady", 994, v7);
        }
        if ( !g_wppLevels )
          goto LABEL_84;
        v27 = 103;
      }
      else
      {
        v28 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v29;
          if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
          {
            v28 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v28 = &qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v28 + 8) )
        {
          v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
          if ( *((_DWORD *)v30 + 499) != v7 )
            CallStackContext::TraceFailure(v30, "CDShowSource::InitializePlayReady", 989, v7);
        }
        if ( !g_wppLevels )
          goto LABEL_84;
        v27 = 102;
      }
    }
    else
    {
      v24 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v26 + 499) != v7 )
          CallStackContext::TraceFailure(v26, "CDShowSource::InitializePlayReady", 987, v7);
      }
      if ( !g_wppLevels )
        goto LABEL_84;
      v27 = 101;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, &WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids, this, v7);
LABEL_84:
    GlobalUnlock(v19);
    goto LABEL_85;
  }
  v11 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
    CallStackTracing::s_wpInstance = v12;
    if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v11 = &qword_1800EB130;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
    }
  }
  if ( *((_BYTE *)v11 + 8) )
  {
    v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
    if ( *((_DWORD *)v13 + 499) != v7 )
      CallStackContext::TraceFailure(v13, "CDShowSource::InitializePlayReady", 977, v7);
  }
  if ( g_wppLevels )
  {
    v10 = 98;
    goto LABEL_15;
  }
LABEL_85:
  operator delete(*(void **)&dwBytes[1]);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppstm);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v38);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v39);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v35);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180089178  push    rbp
0x18008917a  push    rbx
0x18008917b  push    rsi
0x18008917c  push    rdi
0x18008917d  push    r14
0x18008917f  push    r15
0x180089181  mov     rbp, rsp
0x180089184  sub     rsp, 78h
0x180089188  mov     rax, cs:__security_cookie
0x18008918f  xor     rax, rsp
0x180089192  mov     [rbp+var_10], rax
0x180089196  mov     rsi, rcx
0x180089199  lea     r15, aCdshowsourceIn; "CDShowSource::InitializePlayReady"
0x1800891a0  mov     rdx, r15; char *
0x1800891a3  lea     rcx, [rbp+var_48]; this
0x1800891a7  mov     r8d, 3C1h; int
0x1800891ad  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800891b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800891b9  xor     r14d, r14d
0x1800891bc  cmp     [rcx+8], r14b
0x1800891c0  jz      short loc_18008921D
0x1800891c2  cmp     [rsi+448h], r14
0x1800891c9  jz      short loc_18008921D
0x1800891cb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800891d0  mov     rcx, [rsi+448h]
0x1800891d7  mov     rdi, rax
0x1800891da  mov     rdx, [rcx]
0x1800891dd  mov     rax, [rdx+128h]
0x1800891e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800891e9  mov     rcx, [rsi+448h]
0x1800891f0  mov     ebx, eax
0x1800891f2  mov     rdx, [rcx]
0x1800891f5  mov     rax, [rdx+118h]
0x1800891fc  lea     rdx, [rbp+var_20]
0x180089200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089205  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008920c  movups  xmm0, xmmword ptr [rax]
0x18008920f  mov     [rdi+7E0h], ebx
0x180089215  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18008921d  lea     rdi, [rsi+40Ch]
0x180089224  mov     [rbp+var_28], r14
0x180089228  mov     qword ptr [rbp+dwBytes+4], r14
0x18008922c  mov     dword ptr [rbp+dwBytes], r14d
0x180089230  mov     [rbp+var_30], r14
0x180089234  mov     [rbp+ppstm], r14
0x180089238  cmp     [rdi], r14d
0x18008923b  jnz     loc_1800892EE
0x180089241  mov     ebx, 0C00D717Fh
0x180089246  test    rcx, rcx
0x180089249  jnz     short loc_180089292
0x18008924b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089252  nop     dword ptr [rax+rax+00h]
0x180089257  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008925e  mov     rcx, rax
0x180089261  test    rax, rax
0x180089264  jz      short loc_180089284
0x180089266  mov     rax, [rax]
0x180089269  mov     edx, 7F0h
0x18008926e  mov     rax, [rax+8]
0x180089272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089277  test    eax, eax
0x180089279  jz      short loc_180089284
0x18008927b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089282  jmp     short loc_180089292
0x180089284  lea     rcx, qword_1800EB130; this
0x18008928b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180089292  cmp     [rcx+8], r14b
0x180089296  jz      short loc_1800892B9
0x180089298  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008929d  cmp     [rax+7CCh], ebx
0x1800892a3  jz      short loc_1800892B9
0x1800892a5  mov     r9d, ebx; int
0x1800892a8  mov     r8d, 3CEh; int
0x1800892ae  mov     rdx, r15; char *
0x1800892b1  mov     rcx, rax; this
0x1800892b4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800892b9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800892c0  jb      loc_180089771
0x1800892c6  mov     edx, 61h ; 'a'
0x1800892cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800892d2  lea     r8, WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids
0x1800892d9  mov     r9, rsi
0x1800892dc  mov     dword ptr [rsp+78h+var_58], ebx
0x1800892e0  mov     rcx, [rcx+10h]
0x1800892e4  call    WPP_SF_qD
0x1800892e9  jmp     loc_180089771
0x1800892ee  lea     r8, [rbp+dwBytes]; unsigned int *
0x1800892f2  mov     rcx, rsi; this
0x1800892f5  lea     rdx, [rbp+dwBytes+4]; unsigned __int8 **
0x1800892f9  call    ?BuildStreamInfo@CDShowSource@@IEAAJPEAPEAEPEAK@Z; CDShowSource::BuildStreamInfo(uchar * *,ulong *)
0x1800892fe  mov     ebx, eax
0x180089300  test    eax, eax
0x180089302  jns     loc_180089399
0x180089308  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008930f  test    rcx, rcx
0x180089312  jnz     short loc_18008935B
0x180089314  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008931b  nop     dword ptr [rax+rax+00h]
0x180089320  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180089327  mov     rcx, rax
0x18008932a  test    rax, rax
0x18008932d  jz      short loc_18008934D
0x18008932f  mov     rax, [rax]
0x180089332  mov     edx, 7F0h
0x180089337  mov     rax, [rax+8]
0x18008933b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089340  test    eax, eax
0x180089342  jz      short loc_18008934D
0x180089344  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008934b  jmp     short loc_18008935B
0x18008934d  lea     rcx, qword_1800EB130; this
0x180089354  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008935b  cmp     [rcx+8], r14b
0x18008935f  jz      short loc_180089382
0x180089361  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180089366  cmp     [rax+7CCh], ebx
0x18008936c  jz      short loc_180089382
0x18008936e  mov     r9d, ebx; int
0x180089371  mov     r8d, 3D1h; int
0x180089377  mov     rdx, r15; char *
0x18008937a  mov     rcx, rax; this
0x18008937d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180089382  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180089389  jb      loc_180089771
0x18008938f  mov     edx, 62h ; 'b'
0x180089394  jmp     loc_1800892CB
0x180089399  lea     r8, [rbp+var_28]; void **
0x18008939d  mov     rcx, rdi; this
0x1800893a0  lea     rdx, _GUID_f70ca1a9_fdc7_4782_b994_adffb1c98606; struct _GUID *
0x1800893a7  call    ?Get@CGITPtr@@QEAAJAEBU_GUID@@PEAPEAX@Z; CGITPtr::Get(_GUID const &,void * *)
0x1800893ac  mov     ebx, eax
0x1800893ae  test    eax, eax
0x1800893b0  jns     loc_180089447
0x1800893b6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800893bd  test    rcx, rcx
0x1800893c0  jnz     short loc_180089409
0x1800893c2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800893c9  nop     dword ptr [rax+rax+00h]
0x1800893ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800893d5  mov     rcx, rax
0x1800893d8  test    rax, rax
0x1800893db  jz      short loc_1800893FB
0x1800893dd  mov     rax, [rax]
0x1800893e0  mov     edx, 7F0h
0x1800893e5  mov     rax, [rax+8]
0x1800893e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800893ee  test    eax, eax
0x1800893f0  jz      short loc_1800893FB
0x1800893f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800893f9  jmp     short loc_180089409
0x1800893fb  lea     rcx, qword_1800EB130; this
0x180089402  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180089409  cmp     [rcx+8], r14b
0x18008940d  jz      short loc_180089430
0x18008940f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180089414  cmp     [rax+7CCh], ebx
0x18008941a  jz      short loc_180089430
0x18008941c  mov     r9d, ebx; int
0x18008941f  mov     r8d, 3D3h; int
0x180089425  mov     rdx, r15; char *
0x180089428  mov     rcx, rax; this
0x18008942b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180089430  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180089437  jb      loc_180089771
0x18008943d  mov     edx, 63h ; 'c'
0x180089442  jmp     loc_1800892CB
0x180089447  mov     ebx, dword ptr [rbp+dwBytes]
0x18008944a  mov     ecx, 2; uFlags
0x18008944f  mov     edx, ebx; dwBytes
0x180089451  call    cs:__imp_GlobalAlloc
0x180089458  nop     dword ptr [rax+rax+00h]
0x18008945d  mov     rdi, rax
0x180089460  test    rax, rax
0x180089463  jnz     loc_1800894FF
0x180089469  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089470  mov     ebx, 8007000Eh
0x180089475  test    rcx, rcx
0x180089478  jnz     short loc_1800894C1
0x18008947a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089481  nop     dword ptr [rax+rax+00h]
0x180089486  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008948d  mov     rcx, rax
0x180089490  test    rax, rax
0x180089493  jz      short loc_1800894B3
0x180089495  mov     rax, [rax]
0x180089498  mov     edx, 7F0h
0x18008949d  mov     rax, [rax+8]
0x1800894a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800894a6  test    eax, eax
0x1800894a8  jz      short loc_1800894B3
0x1800894aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800894b1  jmp     short loc_1800894C1
0x1800894b3  lea     rcx, qword_1800EB130; this
0x1800894ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800894c1  cmp     [rcx+8], r14b
0x1800894c5  jz      short loc_1800894E8
0x1800894c7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800894cc  cmp     [rax+7CCh], ebx
0x1800894d2  jz      short loc_1800894E8
0x1800894d4  mov     r9d, ebx; int
0x1800894d7  mov     r8d, 3D7h; int
0x1800894dd  mov     rdx, r15; char *
0x1800894e0  mov     rcx, rax; this
0x1800894e3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800894e8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800894ef  jb      loc_180089771
0x1800894f5  mov     edx, 64h ; 'd'
0x1800894fa  jmp     loc_1800892CB
0x1800894ff  mov     rcx, rdi; hMem
0x180089502  call    cs:__imp_GlobalLock
0x180089509  nop     dword ptr [rax+rax+00h]
0x18008950e  mov     r8, qword ptr [rbp+dwBytes+4]; Source
0x180089512  mov     r9, rbx; SourceSize
0x180089515  mov     rcx, rax; Destination
0x180089518  mov     rdx, rbx; DestinationSize
0x18008951b  call    memcpy_s_0
0x180089520  mov     ebx, eax
0x180089522  test    eax, eax
0x180089524  jns     loc_1800895D9
0x18008952a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089531  test    rcx, rcx
0x180089534  jnz     short loc_18008957D
0x180089536  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008953d  nop     dword ptr [rax+rax+00h]
0x180089542  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180089549  mov     rcx, rax
0x18008954c  test    rax, rax
0x18008954f  jz      short loc_18008956F
0x180089551  mov     rax, [rax]
0x180089554  mov     edx, 7F0h
0x180089559  mov     rax, [rax+8]
0x18008955d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089562  test    eax, eax
0x180089564  jz      short loc_18008956F
0x180089566  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008956d  jmp     short loc_18008957D
0x18008956f  lea     rcx, qword_1800EB130; this
0x180089576  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008957d  cmp     [rcx+8], r14b
0x180089581  jz      short loc_1800895A4
0x180089583  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180089588  cmp     [rax+7CCh], ebx
0x18008958e  jz      short loc_1800895A4
0x180089590  mov     r9d, ebx; int
0x180089593  mov     r8d, 3DBh; int
0x180089599  mov     rdx, r15; char *
0x18008959c  mov     rcx, rax; this
0x18008959f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800895a4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800895ab  jb      loc_180089762
0x1800895b1  mov     edx, 65h ; 'e'
0x1800895b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800895bd  lea     r8, WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids
0x1800895c4  mov     r9, rsi
0x1800895c7  mov     dword ptr [rsp+78h+var_58], ebx
0x1800895cb  mov     rcx, [rcx+10h]
0x1800895cf  call    WPP_SF_qD
0x1800895d4  jmp     loc_180089762
0x1800895d9  lea     r8, [rbp+ppstm]; ppstm
0x1800895dd  xor     edx, edx; fDeleteOnRelease
0x1800895df  mov     rcx, rdi; hGlobal
0x1800895e2  call    cs:__imp_CreateStreamOnHGlobal
0x1800895e9  nop     dword ptr [rax+rax+00h]
0x1800895ee  mov     ebx, eax
0x1800895f0  test    eax, eax
0x1800895f2  jns     loc_180089689
0x1800895f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800895ff  test    rcx, rcx
0x180089602  jnz     short loc_18008964B
0x180089604  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008960b  nop     dword ptr [rax+rax+00h]
0x180089610  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180089617  mov     rcx, rax
0x18008961a  test    rax, rax
0x18008961d  jz      short loc_18008963D
0x18008961f  mov     rax, [rax]
0x180089622  mov     edx, 7F0h
0x180089627  mov     rax, [rax+8]
0x18008962b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089630  test    eax, eax
0x180089632  jz      short loc_18008963D
0x180089634  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008963b  jmp     short loc_18008964B
0x18008963d  lea     rcx, qword_1800EB130; this
0x180089644  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008964b  cmp     [rcx+8], r14b
0x18008964f  jz      short loc_180089672
0x180089651  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180089656  cmp     [rax+7CCh], ebx
0x18008965c  jz      short loc_180089672
0x18008965e  mov     r9d, ebx; int
0x180089661  mov     r8d, 3DDh; int
0x180089667  mov     rdx, r15; char *
0x18008966a  mov     rcx, rax; this
0x18008966d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180089672  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180089679  jb      loc_180089762
0x18008967f  mov     edx, 66h ; 'f'
0x180089684  jmp     loc_1800895B6
0x180089689  mov     rcx, [rbp+var_28]
  ... truncated ...
```
