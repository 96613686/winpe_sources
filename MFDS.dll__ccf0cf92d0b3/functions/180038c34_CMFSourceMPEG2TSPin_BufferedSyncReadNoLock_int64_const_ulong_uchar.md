# CMFSourceMPEG2TSPin::_BufferedSyncReadNoLock(__int64 const &,ulong,uchar *)

- ea: `0x180038c34`
- end: `0x1800394c7`
- name: `?_BufferedSyncReadNoLock@CMFSourceMPEG2TSPin@@IEAAJAEB_JKPEAE@Z`
- size: `2195`
- prototype: `__int64 __fastcall(CMFSourceMPEG2TSPin *this, unsigned __int64 *, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180038720`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x1800227e0`
- `0x180032a50`
- `0x1800381d8`
- `0x180038c34`
- `0x180051ce4`
- `0x180074160`
- `0x180074a12`
- `0x180091594`
- `0x1800928c8`
- `0x18009290c`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180038dba`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180039102`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180038dba`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180039102`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038e6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003949b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038e6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003949b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038c70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038e87`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038c70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038e87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039049`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800391f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039285`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003933d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039403`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039049`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800391f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039285`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003933d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039403`
- `MFPlat!MFCreateAsyncResult` at `0x180038deb`
- `MFPlat!MFCreateAsyncResult` at `0x180038fca`
- `MFPlat!MFCreateAsyncResult` at `0x180038deb`
- `MFPlat!MFCreateAsyncResult` at `0x180038fca`

## string_xrefs

- `0x180038d1c`: `CMFSourceMPEG2TSPin::_BufferedSyncReadNoLock`
- `0x180038e99`: `CMFSourceMPEG2TSPin::_BufferedSyncReadNoLock`
- `0x180038fe7`: `CMFSourceMPEG2TSPin::_BufferedSyncReadNoLock`
- `0x1800390a6`: `CMFSourceMPEG2TSPin::_BufferedSyncReadNoLock`
- `0x18003917f`: `CMFSourceMPEG2TSPin::_BufferedSyncReadNoLock`
- `0x18003924d`: `CMFSourceMPEG2TSPin::_BufferedSyncReadNoLock`
- `0x1800392e2`: `CMFSourceMPEG2TSPin::_BufferedSyncReadNoLock`
- `0x18003939a`: `CMFSourceMPEG2TSPin::_BufferedSyncReadNoLock`
- `0x180039460`: `CMFSourceMPEG2TSPin::_BufferedSyncReadNoLock`

## pseudocode

```c
__int64 __fastcall CMFSourceMPEG2TSPin::_BufferedSyncReadNoLock(
        CMFSourceMPEG2TSPin *this,
        unsigned __int64 *a2,
        unsigned int a3,
        unsigned __int8 *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  unsigned __int64 v6; // r15
  HRESULT v9; // esi
  int v10; // r13d
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned __int64 v16; // rax
  CAMEvent *v17; // r14
  void *v18; // rcx
  __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  const void *v21; // rdx
  unsigned int v22; // r12d
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // rax
  __int64 v25; // rcx
  HRESULT v26; // esi
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v41; // rdx
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  char v46[8]; // [rsp+30h] [rbp-38h] BYREF
  void *v47; // [rsp+38h] [rbp-30h]
  IMFAsyncResult *ppAsyncResult; // [rsp+40h] [rbp-28h] BYREF
  __int64 v49; // [rsp+48h] [rbp-20h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 488);
  v47 = a4;
  v6 = a3;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  v49 = 0;
  if ( !a4 )
  {
    v9 = -2147024809;
    goto LABEL_99;
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 56) + 208LL) )
  {
    v9 = -2147467259;
    goto LABEL_99;
  }
  v9 = 0;
  if ( *((_DWORD *)this + 138) )
  {
    *((_DWORD *)this + 138) = 0;
    CMFSourceMPEG2TSPin::_EnableBuffering(this, 1);
  }
  v10 = 0;
  while ( 1 )
  {
    v11 = *a2;
    v12 = *((_QWORD *)this + 75);
    if ( *a2 >= v12 )
    {
      v13 = *((unsigned int *)this + 152);
      if ( v11 < v13 + v12 && v12 + v13 - v11 >= v6 )
        break;
    }
    if ( v10 )
    {
      *((_DWORD *)this + 136) = 0;
      v9 = 1;
      goto LABEL_99;
    }
    if ( *((_DWORD *)this + 153) )
    {
      v17 = (CMFSourceMPEG2TSPin *)((char *)this + 528);
    }
    else
    {
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)v46,
        "CMFSourceMPEG2TSPin::_BufferedSyncReadNoLock",
        4428);
      if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
        WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 17), v14, v15, *a2);
      *((_QWORD *)this + 77) = *a2;
      v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, __int64, __int64 *))(**(_QWORD **)(*((_QWORD *)this + 56) + 216LL)
                                                                                           + 120LL))(
             *(_QWORD *)(*((_QWORD *)this + 56) + 216LL),
             0,
             *a2,
             1,
             &v49);
      if ( v9 < 0 )
      {
        v38 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v39;
          if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
          {
            v38 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v38 = &qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v38 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CMFSourceMPEG2TSPin::_BufferedSyncReadNoLock",
              4430,
              v9);
        }
        if ( g_wppLevels )
        {
          v41 = 72;
          goto LABEL_85;
        }
LABEL_86:
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v46);
        goto LABEL_99;
      }
      *((_QWORD *)this + 74) = *((_QWORD *)this + 73);
      v16 = *a2;
      *((_DWORD *)this + 152) = 0;
      v17 = (CMFSourceMPEG2TSPin *)((char *)this + 528);
      v18 = (void *)*((_QWORD *)this + 66);
      *((_QWORD *)this + 75) = v16;
      ResetEvent(v18);
      v19 = *((_QWORD *)this + 56);
      *((_DWORD *)this + 135) = 0;
      ppAsyncResult = 0;
      v9 = MFCreateAsyncResult(*(IUnknown **)(v19 + 216), 0, 0, &ppAsyncResult);
      if ( v9 < 0 )
      {
        v35 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v36;
          if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
          {
            v35 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v35 = &qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v35 + 8) )
        {
          v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
          if ( *((_DWORD *)v37 + 499) != v9 )
            CallStackContext::TraceFailure(v37, "CMFSourceMPEG2TSPin::_BufferedSyncReadNoLock", 4439, v9);
        }
        if ( g_wppLevels )
        {
          v34 = 73;
LABEL_73:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v34,
            &WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids,
            this,
            v9);
        }
LABEL_74:
        ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppAsyncResult);
        goto LABEL_86;
      }
      v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, char *, IMFAsyncResult *))(**(_QWORD **)(*((_QWORD *)this + 56) + 216LL)
                                                                                        + 80LL))(
             *(_QWORD *)(*((_QWORD *)this + 56) + 216LL),
             *((_QWORD *)this + 74),
             0x10000,
             (char *)this + 560,
             ppAsyncResult);
      if ( v9 < 0 )
      {
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
          if ( *((_DWORD *)v33 + 499) != v9 )
            CallStackContext::TraceFailure(v33, "CMFSourceMPEG2TSPin::_BufferedSyncReadNoLock", 4441, v9);
        }
        if ( g_wppLevels )
        {
          v34 = 74;
          goto LABEL_73;
        }
        goto LABEL_74;
      }
      *((_DWORD *)this + 153) = 1;
      v10 = 1;
      ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppAsyncResult);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v46);
    }
    LeaveCriticalSection(v4);
    CAMEvent::Wait(v17, 0xFFFFFFFF);
    EnterCriticalSection(v4);
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v46,
      "CMFSourceMPEG2TSPin::_BufferedSyncReadNoLock",
      4450);
    v9 = *((_DWORD *)this + 135);
    if ( v9 < 0 )
    {
      v42 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v43;
        if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
        {
          v42 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v42 = &qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v42 + 8) )
      {
        v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
        if ( *((_DWORD *)v44 + 499) != v9 )
          CallStackContext::TraceFailure(v44, "CMFSourceMPEG2TSPin::_BufferedSyncReadNoLock", 4450, v9);
      }
      if ( g_wppLevels )
      {
        v41 = 75;
LABEL_85:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v41, &WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids, this, v9);
      }
      goto LABEL_86;
    }
    if ( *(_DWORD *)(*((_QWORD *)this + 56) + 208LL) )
    {
      *((_DWORD *)this + 136) = 0;
      v9 = 1;
      goto LABEL_86;
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v46);
  }
  v20 = v11 - v12 + *((_QWORD *)this + 74);
  v21 = (const void *)(v20 - 0x20000);
  if ( v20 <= *((_QWORD *)this + 73) + 0x20000LL )
    v21 = (const void *)v20;
  v22 = *((_DWORD *)this + 146) - (_DWORD)v21 + 0x20000;
  if ( v22 > (unsigned int)v6 )
    v22 = v6;
  memcpy_0(v47, v21, v22);
  if ( (_DWORD)v6 != v22 )
    memcpy_0((char *)v47 + v22, *((const void **)this + 73), (unsigned int)v6 - v22);
  *((_QWORD *)this + 74) += v6;
  v23 = *((_QWORD *)this + 74);
  v24 = *((_QWORD *)this + 73) + 0x20000LL;
  *((_DWORD *)this + 136) = v6;
  if ( v23 >= v24 )
    *((_QWORD *)this + 74) = v23 - 0x20000;
  *((_DWORD *)this + 152) -= v6;
  *((_QWORD *)this + 75) += v6;
  if ( *((_QWORD *)this + 76) <= 0x10000u )
  {
    v25 = *((_QWORD *)this + 56);
    ppAsyncResult = 0;
    v26 = MFCreateAsyncResult(*(IUnknown **)(v25 + 216), 0, 0, &ppAsyncResult);
    if ( v26 >= 0 )
    {
      *((_QWORD *)this + 77) += 0x10000LL;
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)v46,
        "CMFSourceMPEG2TSPin::_BufferedSyncReadNoLock",
        4530);
      v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int64 *))(**(_QWORD **)(*((_QWORD *)this + 56)
                                                                                               + 216LL)
                                                                                 + 120LL))(
             *(_QWORD *)(*((_QWORD *)this + 56) + 216LL),
             0,
             *((_QWORD *)this + 77),
             1,
             &v49);
      if ( v9 < 0 )
      {
        v27 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v28;
          if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
          {
            v27 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v27 = &qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v27 + 8) )
        {
          v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
          if ( *((_DWORD *)v29 + 499) != v9 )
            CallStackContext::TraceFailure(v29, "CMFSourceMPEG2TSPin::_BufferedSyncReadNoLock", 4530, v9);
        }
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids, this, v9);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v46);
        ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppAsyncResult);
        goto LABEL_99;
      }
      ResetEvent(*((HANDLE *)this + 66));
      v30 = *((_QWORD *)this + 73);
      if ( *((_QWORD *)this + 74) < (unsigned __int64)(v30 + 0x10000) )
        v30 += 0x10000;
      v26 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, char *, IMFAsyncResult *))(**(_QWORD **)(*((_QWORD *)this + 56) + 216LL)
                                                                                          + 80LL))(
              *(_QWORD *)(*((_QWORD *)this + 56) + 216LL),
              v30,
              0x10000,
              (char *)this + 560,
              ppAsyncResult);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v46);
      if ( v26 >= 0 )
        *((_DWORD *)this + 153) = 1;
    }
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v46,
      "CMFSourceMPEG2TSPin::_BufferedSyncReadNoLock",
      4552);
    if ( (unsigned __int8)byte_1800EACCB >= 8u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        80,
        &WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids,
        (unsigned int)v26);
    v9 = 0;
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v46);
    if ( ppAsyncResult )
      ((void (__fastcall *)(IMFAsyncResult *))ppAsyncResult->lpVtbl->Release)(ppAsyncResult);
  }
LABEL_99:
  LeaveCriticalSection(v4);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180038c34  push    rbp
0x180038c36  push    rbx
0x180038c37  push    rsi
0x180038c38  push    rdi
0x180038c39  push    r12
0x180038c3b  push    r13
0x180038c3d  push    r14
0x180038c3f  push    r15
0x180038c41  mov     rbp, rsp
0x180038c44  sub     rsp, 68h
0x180038c48  mov     rax, cs:__security_cookie
0x180038c4f  xor     rax, rsp
0x180038c52  mov     [rbp+var_18], rax
0x180038c56  lea     rbx, [rcx+1E8h]
0x180038c5d  mov     [rbp+var_30], r9
0x180038c61  mov     rdi, rcx
0x180038c64  mov     r15d, r8d
0x180038c67  mov     rcx, rbx; lpCriticalSection
0x180038c6a  mov     rsi, r9
0x180038c6d  mov     r12, rdx
0x180038c70  call    cs:__imp_EnterCriticalSection
0x180038c77  nop     dword ptr [rax+rax+00h]
0x180038c7c  xor     r14d, r14d
0x180038c7f  mov     [rbp+var_20], r14
0x180038c83  test    rsi, rsi
0x180038c86  jnz     short loc_180038C92
0x180038c88  mov     esi, 80070057h
0x180038c8d  jmp     loc_180039498
0x180038c92  mov     rax, [rdi+1C0h]
0x180038c99  cmp     [rax+0D0h], r14d
0x180038ca0  jz      short loc_180038CAC
0x180038ca2  mov     esi, 80004005h
0x180038ca7  jmp     loc_180039498
0x180038cac  mov     esi, r14d
0x180038caf  cmp     [rdi+228h], r14d
0x180038cb6  jz      short loc_180038CCC
0x180038cb8  mov     edx, 1; int
0x180038cbd  mov     [rdi+228h], r14d
0x180038cc4  mov     rcx, rdi; this
0x180038cc7  call    ?_EnableBuffering@CMFSourceMPEG2TSPin@@IEAAJH@Z; CMFSourceMPEG2TSPin::_EnableBuffering(int)
0x180038ccc  mov     r13d, r14d
0x180038ccf  mov     rdx, [r12]
0x180038cd3  mov     r8, [rdi+258h]
0x180038cda  cmp     rdx, r8
0x180038cdd  jb      short loc_180038D00
0x180038cdf  mov     ecx, [rdi+260h]
0x180038ce5  lea     rax, [rcx+r8]
0x180038ce9  cmp     rdx, rax
0x180038cec  jnb     short loc_180038D00
0x180038cee  sub     rcx, rdx
0x180038cf1  add     rcx, r8
0x180038cf4  cmp     rcx, r15
0x180038cf7  jnb     loc_180038EDC
0x180038cfd  xor     r14d, r14d
0x180038d00  test    r13d, r13d
0x180038d03  jnz     loc_18003948C
0x180038d09  cmp     [rdi+264h], r14d
0x180038d10  jnz     loc_180038E63
0x180038d16  mov     r8d, 114Ch; int
0x180038d1c  lea     rdx, aCmfsourcempeg2_2; "CMFSourceMPEG2TSPin::_BufferedSyncReadN"...
0x180038d23  lea     rcx, [rbp+var_38]; this
0x180038d27  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180038d2c  cmp     cs:byte_1800EACCB, 20h ; ' '
0x180038d33  jb      short loc_180038D4C
0x180038d35  mov     rcx, cs:WPP_GLOBAL_Control
0x180038d3c  mov     r9, [r12]
0x180038d40  mov     rcx, [rcx+88h]
0x180038d47  call    WPP_SF_I
0x180038d4c  mov     rax, [r12]
0x180038d50  lea     rdx, [rbp+var_20]
0x180038d54  mov     [rdi+268h], rax
0x180038d5b  mov     r9d, 1
0x180038d61  mov     rax, [rdi+1C0h]
0x180038d68  mov     r8, [r12]
0x180038d6c  mov     [rsp+68h+var_48], rdx
0x180038d71  xor     edx, edx
0x180038d73  mov     rcx, [rax+0D8h]
0x180038d7a  mov     rax, [rcx]
0x180038d7d  mov     rax, [rax+78h]
0x180038d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d86  mov     esi, eax
0x180038d88  test    eax, eax
0x180038d8a  js      loc_180039331
0x180038d90  mov     rax, [rdi+248h]
0x180038d97  mov     [rdi+250h], rax
0x180038d9e  mov     rax, [r12]
0x180038da2  mov     [rdi+260h], r14d
0x180038da9  lea     r14, [rdi+210h]
0x180038db0  mov     rcx, [r14]; hEvent
0x180038db3  mov     [rdi+258h], rax
0x180038dba  call    cs:__imp_ResetEvent
0x180038dc1  nop     dword ptr [rax+rax+00h]
0x180038dc6  mov     rcx, [rdi+1C0h]
0x180038dcd  lea     r9, [rbp+ppAsyncResult]; ppAsyncResult
0x180038dd1  xor     r13d, r13d
0x180038dd4  xor     r8d, r8d; punkState
0x180038dd7  mov     [rdi+21Ch], r13d
0x180038dde  xor     edx, edx; pCallback
0x180038de0  mov     [rbp+ppAsyncResult], r13
0x180038de4  mov     rcx, [rcx+0D8h]; punkObject
0x180038deb  call    cs:__imp_MFCreateAsyncResult
0x180038df2  nop     dword ptr [rax+rax+00h]
0x180038df7  mov     esi, eax
0x180038df9  test    eax, eax
0x180038dfb  js      loc_180039279
0x180038e01  mov     rax, [rdi+1C0h]
0x180038e08  lea     r9, [rdi+230h]
0x180038e0f  mov     rdx, [rbp+ppAsyncResult]
0x180038e13  mov     r8d, 10000h
0x180038e19  mov     [rsp+68h+var_48], rdx
0x180038e1e  mov     rdx, [rdi+250h]
0x180038e25  mov     rcx, [rax+0D8h]
0x180038e2c  mov     rax, [rcx]
0x180038e2f  mov     rax, [rax+50h]
0x180038e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e38  mov     esi, eax
0x180038e3a  test    eax, eax
0x180038e3c  js      loc_1800391E4
0x180038e42  lea     eax, [r13+1]
0x180038e46  lea     rcx, [rbp+ppAsyncResult]; void *
0x180038e4a  mov     [rdi+264h], eax
0x180038e50  mov     r13d, eax
0x180038e53  call    ??1?$CComPtrBase@UIMediaSeeking@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(void)
0x180038e58  lea     rcx, [rbp+var_38]; this
0x180038e5c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180038e61  jmp     short loc_180038E6A
0x180038e63  lea     r14, [rdi+210h]
0x180038e6a  mov     rcx, rbx; lpCriticalSection
0x180038e6d  call    cs:__imp_LeaveCriticalSection
0x180038e74  nop     dword ptr [rax+rax+00h]
0x180038e79  or      edx, 0FFFFFFFFh; unsigned int
0x180038e7c  mov     rcx, r14; this
0x180038e7f  call    ?Wait@CAMEvent@@QEAAHK@Z; CAMEvent::Wait(ulong)
0x180038e84  mov     rcx, rbx; lpCriticalSection
0x180038e87  call    cs:__imp_EnterCriticalSection
0x180038e8e  nop     dword ptr [rax+rax+00h]
0x180038e93  mov     r8d, 1162h; int
0x180038e99  lea     rdx, aCmfsourcempeg2_2; "CMFSourceMPEG2TSPin::_BufferedSyncReadN"...
0x180038ea0  lea     rcx, [rbp+var_38]; this
0x180038ea4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180038ea9  mov     esi, [rdi+21Ch]
0x180038eaf  xor     r14d, r14d
0x180038eb2  test    esi, esi
0x180038eb4  js      loc_1800393F7
0x180038eba  mov     rax, [rdi+1C0h]
0x180038ec1  lea     rcx, [rbp+var_38]; this
0x180038ec5  cmp     [rax+0D0h], r14d
0x180038ecc  jnz     loc_1800393E9
0x180038ed2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180038ed7  jmp     loc_180038CCF
0x180038edc  mov     rcx, [rdi+250h]
0x180038ee3  sub     rdx, r8
0x180038ee6  mov     rax, [rdi+248h]
0x180038eed  add     rcx, rdx
0x180038ef0  mov     r12d, [rdi+248h]
0x180038ef7  add     rax, 20000h
0x180038efd  cmp     rcx, rax
0x180038f00  lea     rdx, [rcx-20000h]
0x180038f07  cmovbe  rdx, rcx; Src
0x180038f0b  mov     rcx, [rbp+var_30]; void *
0x180038f0f  sub     r12d, edx
0x180038f12  add     r12d, 20000h
0x180038f19  cmp     r12d, r15d
0x180038f1c  cmova   r12d, r15d
0x180038f20  mov     r8d, r12d; Size
0x180038f23  mov     r13d, r12d
0x180038f26  call    memcpy_0
0x180038f2b  cmp     r15d, r12d
0x180038f2e  jz      short loc_180038F49
0x180038f30  mov     rcx, [rbp+var_30]
0x180038f34  mov     r8d, r15d
0x180038f37  mov     rdx, [rdi+248h]; Src
0x180038f3e  sub     r8d, r12d; Size
0x180038f41  add     rcx, r13; void *
0x180038f44  call    memcpy_0
0x180038f49  add     [rdi+250h], r15
0x180038f50  mov     rax, [rdi+248h]
0x180038f57  mov     rcx, [rdi+250h]
0x180038f5e  add     rax, 20000h
0x180038f64  mov     [rdi+220h], r15d
0x180038f6b  cmp     rcx, rax
0x180038f6e  jb      short loc_180038F7E
0x180038f70  lea     rax, [rcx-20000h]
0x180038f77  mov     [rdi+250h], rax
0x180038f7e  sub     [rdi+260h], r15d
0x180038f85  xor     r13d, r13d
0x180038f88  add     [rdi+258h], r15
0x180038f8f  cmp     [rdi+264h], r13d
0x180038f96  jnz     loc_180039498
0x180038f9c  mov     r15d, 10000h
0x180038fa2  cmp     [rdi+260h], r15d
0x180038fa9  ja      loc_180039498
0x180038faf  mov     rcx, [rdi+1C0h]
0x180038fb6  lea     r9, [rbp+ppAsyncResult]; ppAsyncResult
0x180038fba  mov     [rbp+ppAsyncResult], r13
0x180038fbe  xor     r8d, r8d; punkState
0x180038fc1  xor     edx, edx; pCallback
0x180038fc3  mov     rcx, [rcx+0D8h]; punkObject
0x180038fca  call    cs:__imp_MFCreateAsyncResult
0x180038fd1  nop     dword ptr [rax+rax+00h]
0x180038fd6  mov     esi, eax
0x180038fd8  test    eax, eax
0x180038fda  js      loc_180039179
0x180038fe0  add     [rdi+268h], r15
0x180038fe7  lea     rdx, aCmfsourcempeg2_2; "CMFSourceMPEG2TSPin::_BufferedSyncReadN"...
0x180038fee  mov     r12d, 11B2h
0x180038ff4  lea     rcx, [rbp+var_38]; this
0x180038ff8  mov     r8d, r12d; int
0x180038ffb  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180039000  mov     rax, [rdi+1C0h]
0x180039007  lea     rdx, [rbp+var_20]
0x18003900b  mov     r8, [rdi+268h]
0x180039012  lea     r14d, [r13+1]
0x180039016  mov     [rsp+68h+var_48], rdx
0x18003901b  mov     r9d, r14d
0x18003901e  xor     edx, edx
0x180039020  mov     rcx, [rax+0D8h]
0x180039027  mov     rax, [rcx]
0x18003902a  mov     rax, [rax+78h]
0x18003902e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039033  mov     esi, eax
0x180039035  test    eax, eax
0x180039037  jns     loc_1800390FB
0x18003903d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039044  test    rcx, rcx
0x180039047  jnz     short loc_180039090
0x180039049  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039050  nop     dword ptr [rax+rax+00h]
0x180039055  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003905c  mov     rcx, rax
0x18003905f  test    rax, rax
0x180039062  jz      short loc_180039082
0x180039064  mov     rax, [rax]
0x180039067  mov     edx, 7F0h
0x18003906c  mov     rax, [rax+8]
0x180039070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039075  test    eax, eax
0x180039077  jz      short loc_180039082
0x180039079  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039080  jmp     short loc_180039090
0x180039082  lea     rcx, qword_1800EB130; this
0x180039089  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180039090  cmp     [rcx+8], r13b
0x180039094  jz      short loc_1800390B8
0x180039096  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003909b  cmp     [rax+7CCh], esi
0x1800390a1  jz      short loc_1800390B8
0x1800390a3  mov     r9d, esi; int
0x1800390a6  lea     rdx, aCmfsourcempeg2_2; "CMFSourceMPEG2TSPin::_BufferedSyncReadN"...
0x1800390ad  mov     r8d, r12d; int
0x1800390b0  mov     rcx, rax; this
0x1800390b3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800390b8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800390bf  jb      short loc_1800390E4
0x1800390c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800390c8  lea     r8, WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids
0x1800390cf  mov     edx, 4Fh ; 'O'
0x1800390d4  mov     dword ptr [rsp+68h+var_48], esi
0x1800390d8  mov     r9, rdi
0x1800390db  mov     rcx, [rcx+10h]
0x1800390df  call    WPP_SF_qD
0x1800390e4  lea     rcx, [rbp+var_38]; this
0x1800390e8  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800390ed  lea     rcx, [rbp+ppAsyncResult]; void *
0x1800390f1  call    ??1?$CComPtrBase@UIMediaSeeking@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(void)
0x1800390f6  jmp     loc_180039498
0x1800390fb  mov     rcx, [rdi+210h]; hEvent
0x180039102  call    cs:__imp_ResetEvent
0x180039109  nop     dword ptr [rax+rax+00h]
0x18003910e  mov     rax, [rdi+1C0h]
0x180039115  lea     r9, [rdi+230h]
0x18003911c  mov     rdx, [rdi+248h]
0x180039123  mov     r8d, r15d
0x180039126  mov     r11, [rax+0D8h]
0x18003912d  lea     r10, [rdx+10000h]
0x180039134  mov     rax, [r11]
0x180039137  mov     rax, [rax+50h]
0x18003913b  cmp     [rdi+250h], r10
0x180039142  jb      short loc_18003914F
0x180039144  mov     r10, [rbp+ppAsyncResult]
0x180039148  mov     [rsp+68h+var_48], r10
0x18003914d  jmp     short loc_18003915B
0x18003914f  mov     rcx, [rbp+ppAsyncResult]
0x180039153  mov     rdx, r10
0x180039156  mov     [rsp+68h+var_48], rcx
0x18003915b  mov     rcx, r11
0x18003915e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039163  lea     rcx, [rbp+var_38]; this
0x180039167  mov     esi, eax
0x180039169  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003916e  test    esi, esi
0x180039170  js      short loc_180039179
0x180039172  mov     [rdi+264h], r14d
0x180039179  mov     r8d, 11C8h; int
0x18003917f  lea     rdx, aCmfsourcempeg2_2; "CMFSourceMPEG2TSPin::_BufferedSyncReadN"...
0x180039186  lea     rcx, [rbp+var_38]; this
0x18003918a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003918f  cmp     cs:byte_1800EACCB, 8
0x180039196  jb      short loc_1800391BA
0x180039198  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
