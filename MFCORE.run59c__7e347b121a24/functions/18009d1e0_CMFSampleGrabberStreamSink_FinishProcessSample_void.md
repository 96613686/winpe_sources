# CMFSampleGrabberStreamSink::FinishProcessSample(void)

- ea: `0x18009d1e0`
- end: `0x18009e097`
- name: `?FinishProcessSample@CMFSampleGrabberStreamSink@@IEAAJXZ`
- size: `3767`
- prototype: `__int64 __fastcall(CMFSampleGrabberStreamSink *__hidden this)`
- caller_count: `4`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18009e0a0`
- `0x18009f020`
- `0x18009f2f0`
- `0x180210730`

## callees

- `0x18001616c`
- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x18009cac8`
- `0x18009d1e0`
- `0x18009efc4`
- `0x1800ec0e0`
- `0x180258480`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009d537`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009d58b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009d7a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009de05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009d537`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009d58b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009d7a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009de05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009d218`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009d524`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009d218`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009d524`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009d9e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009da9a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009db6c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009dc6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009dd85`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009d9e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009da9a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009db6c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009dc6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009dd85`
- `MFPlat!MFCreateAttributes` at `0x18009df9f`
- `MFPlat!MFCreateAttributes` at `0x18009df9f`

## string_xrefs

- `0x18009d2fb`: `CMFSampleGrabberStreamSink::FinishProcessSample`
- `0x18009d807`: `CMFSampleGrabberStreamSink::FinishProcessSample`
- `0x18009de9a`: `CMFSampleGrabberStreamSink::FinishProcessSample`
- `0x18009dedb`: `CMFSampleGrabberStreamSink::FinishProcessSample`
- `0x18009e039`: `CMFSampleGrabberStreamSink::FinishProcessSample`

## pseudocode

```c
__int64 __fastcall CMFSampleGrabberStreamSink::FinishProcessSample(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // r15
  __int64 *SpinCount; // rcx
  ULONG_PTR v4; // rax
  __int64 v5; // rbx
  CallStackTracing *v6; // rcx
  struct CallStackContext *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8
  HRESULT v12; // r12d
  ULONG_PTR v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int RecursionCount; // eax
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // r15
  __int64 v18; // r14
  __int64 *OwningThread; // rdi
  __int64 *LockSemaphore; // rsi
  __int64 v21; // rax
  __int64 *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r8
  UINT32 v25; // edi
  CallStackTracing *v27; // rcx
  CallStackTracing *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 *v32; // rcx
  CallStackTracing *v33; // rcx
  __int64 v34; // rdx
  CallStackTracing *v35; // rcx
  CallStackTracing *v36; // rcx
  CallStackTracing *v37; // rax
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  __int64 v44; // rdx
  struct CallStackContext *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  struct CallStackContext *v50; // rax
  struct CallStackContext *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v57; // rdx
  __int64 v58; // r8
  int v59; // eax
  int v60; // [rsp+20h] [rbp-B9h]
  char v61[8]; // [rsp+50h] [rbp-89h] BYREF
  __int64 v62; // [rsp+58h] [rbp-81h] BYREF
  __int64 v63; // [rsp+60h] [rbp-79h] BYREF
  __int64 v64; // [rsp+68h] [rbp-71h] BYREF
  UINT32 cInitialSize; // [rsp+70h] [rbp-69h] BYREF
  __int64 v66; // [rsp+78h] [rbp-61h] BYREF
  int v67; // [rsp+80h] [rbp-59h] BYREF
  unsigned int v68; // [rsp+84h] [rbp-55h] BYREF
  __int64 v69; // [rsp+88h] [rbp-51h] BYREF
  __int64 v70; // [rsp+90h] [rbp-49h] BYREF
  __int64 v71; // [rsp+98h] [rbp-41h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v73; // [rsp+A8h] [rbp-31h] BYREF
  __int64 *v74; // [rsp+B0h] [rbp-29h] BYREF
  __int64 *v75; // [rsp+B8h] [rbp-21h] BYREF
  __int64 v76; // [rsp+C0h] [rbp-19h] BYREF
  PRTL_CRITICAL_SECTION_DEBUG v77; // [rsp+C8h] [rbp-11h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+D0h] [rbp-9h]
  GUID v79; // [rsp+D8h] [rbp-1h] BYREF

  v1 = this + 13;
  lpCriticalSection = this + 13;
  EnterCriticalSection(this + 13);
  SpinCount = (__int64 *)this[25].SpinCount;
  v69 = 0;
  if ( !SpinCount )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v61,
      "CMFSampleGrabberStreamSink::FinishProcessSample",
      954);
    v32 = (__int64 *)CallStackTracing::s_wpInstance;
    v12 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31);
      CallStackTracing::s_wpInstance = v37;
      if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
      {
        v32 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v32 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v32 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFSampleGrabberStreamSink::FinishProcessSample",
          954,
          -2147418113);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        85,
        &WPP_9e0691ee672e3c34414a5076d2e5426e_Traceguids,
        this,
        -2147418113);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v61);
    goto LABEL_96;
  }
  v4 = SpinCount[1];
  v5 = *SpinCount;
  v69 = *SpinCount;
  this[25].SpinCount = v4;
  if ( v4 )
    *(_QWORD *)(v4 + 16) = 0;
  else
    this[26].DebugInfo = 0;
  SpinCount[1] = *(_QWORD *)&this[15].LockCount;
  *(_QWORD *)&this[15].LockCount = SpinCount;
  --this[26].LockCount;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v5)(v5, &GUID_c40a00f2_b93a_4d80_ae8c_5a1c634f58e4, &v62);
  (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v5)(v5, &GUID_a6fdf644_50ab_4cb8_b4d8_656cb597b6ca, &v64);
  (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v5)(v5, &GUID_df598932_f10c_4e39_bba2_c308f101daa3, &v63);
  if ( v64 )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v61,
      "CMFSampleGrabberStreamSink::FinishProcessSample",
      967);
    if ( (unsigned __int8)byte_1803CECEA >= 0x10u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 86, &WPP_9e0691ee672e3c34414a5076d2e5426e_Traceguids);
    v38 = (__int64 *)CallStackTracing::s_wpInstance;
    v12 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v57, v58);
      CallStackTracing::s_wpInstance = v39;
      if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
      {
        v38 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v38 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v38 + 8) )
    {
      v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
      if ( *((_DWORD *)v40 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v40, "CMFSampleGrabberStreamSink::FinishProcessSample", 969, -2147418113);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        87,
        &WPP_9e0691ee672e3c34414a5076d2e5426e_Traceguids,
        this,
        -2147418113);
    goto LABEL_139;
  }
  if ( v62 )
  {
    v6 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v6 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v7 = CallStackTracing::GetThreadRelativeContext(v6);
      v8 = *((unsigned int *)v7 + 497);
      if ( (unsigned int)v8 < *((_DWORD *)v7 + 498) )
      {
        v9 = 2 * v8;
        *((_QWORD *)v7 + v9) = "CMFSampleGrabberStreamSink::FinishProcessSample";
        *((_DWORD *)v7 + 2 * v9 + 2) = 974;
      }
      ++*((_DWORD *)v7 + 497);
    }
    if ( (unsigned __int8)byte_1803CECEA >= 0x10u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 88, &WPP_9e0691ee672e3c34414a5076d2e5426e_Traceguids);
    v71 = 0x7FFFFFFFFFFFFFFFLL;
    v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v62 + 280LL))(v62, &v71);
    if ( v12 < 0 )
    {
      v36 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v36 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v36 + 8) )
      {
        v41 = CallStackTracing::GetThreadRelativeContext(v36);
        if ( *((_DWORD *)v41 + 499) != v12 )
          CallStackContext::TraceFailure(v41, "CMFSampleGrabberStreamSink::FinishProcessSample", 980, v12);
      }
      if ( !g_wppLevels )
        goto LABEL_76;
      v34 = 89;
    }
    else
    {
      if ( v71 == 0x7FFFFFFFFFFFFFFFLL )
      {
        v42 = (__int64 *)CallStackTracing::s_wpInstance;
        v12 = -2147418113;
        if ( !CallStackTracing::s_wpInstance )
        {
          v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11);
          CallStackTracing::s_wpInstance = v43;
          if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
          {
            v42 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v42 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v42 + 8) )
        {
          v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
          if ( *((_DWORD *)v45 + 499) != -2147418113 )
            CallStackContext::TraceFailure(v45, "CMFSampleGrabberStreamSink::FinishProcessSample", 983, -2147418113);
        }
        if ( !g_wppLevels )
          goto LABEL_139;
        v44 = 90;
        v60 = -2147418113;
LABEL_138:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v44, &WPP_9e0691ee672e3c34414a5076d2e5426e_Traceguids, this, v60);
LABEL_139:
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v61);
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v64);
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v63);
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v62);
LABEL_96:
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v69);
LABEL_84:
        LeaveCriticalSection(v1);
        return (unsigned int)v12;
      }
      v70 = 0x7FFFFFFFFFFFFFFFLL;
      if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v62 + 296LL))(v62, &v70) < 0 )
        v70 = 0x7FFFFFFFFFFFFFFFLL;
      v68 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v62 + 264LL))(v62, &v68);
      if ( v12 >= 0 )
      {
        v13 = this[12].SpinCount;
        v79 = GUID_00000000_0000_0000_0000_000000000000;
        v12 = (*(__int64 (__fastcall **)(ULONG_PTR, GUID *))(*(_QWORD *)v13 + 264LL))(v13, &v79);
        if ( v12 >= 0 )
        {
          v66 = 0;
          v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v62 + 328LL))(v62, &v66);
          if ( v12 < 0 )
          {
            v27 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v27 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v27 + 8) )
            {
              v50 = CallStackTracing::GetThreadRelativeContext(v27);
              if ( *((_DWORD *)v50 + 499) != v12 )
                CallStackContext::TraceFailure(v50, "CMFSampleGrabberStreamSink::FinishProcessSample", 1016, v12);
            }
            if ( !g_wppLevels )
              goto LABEL_74;
            v29 = 93;
            goto LABEL_90;
          }
          if ( (unsigned __int8)byte_1803CECEA >= 8u )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              94,
              &WPP_9e0691ee672e3c34414a5076d2e5426e_Traceguids,
              this,
              this[12].RecursionCount);
          RecursionCount = this[12].RecursionCount;
          if ( RecursionCount < LODWORD(this[11].SpinCount) )
          {
            this[12].RecursionCount = RecursionCount + 1;
            v12 = QueueSimpleEvent(
                    (struct CMFMediaEventGenerator *)((unsigned __int64)&this[2].LockSemaphore & -(__int64)(this != 0)),
                    0x131u,
                    0);
            if ( v12 < 0 )
            {
              v28 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::InitInstance();
                v28 = CallStackTracing::s_wpInstance;
              }
              if ( *((_BYTE *)v28 + 8) )
              {
                v51 = CallStackTracing::GetThreadRelativeContext(v28);
                if ( *((_DWORD *)v51 + 499) != v12 )
                  CallStackContext::TraceFailure(v51, "CMFSampleGrabberStreamSink::FinishProcessSample", 1031, v12);
              }
              if ( !g_wppLevels )
                goto LABEL_74;
              v29 = 95;
              goto LABEL_90;
            }
            if ( (unsigned __int8)byte_1803CECEA >= 8u )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 12),
                96,
                &WPP_9e0691ee672e3c34414a5076d2e5426e_Traceguids,
                this,
                this[12].RecursionCount);
          }
          v73 = 0;
          v67 = 0;
          if ( !this[11].OwningThread && !this[11].LockSemaphore )
          {
            v12 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, int *))(*(_QWORD *)v66 + 24LL))(
                    v66,
                    &v73,
                    0,
                    &v67);
            if ( v12 < 0 )
            {
              v35 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::InitInstance();
                v35 = CallStackTracing::s_wpInstance;
              }
              if ( *((_BYTE *)v35 + 8) )
              {
                v52 = CallStackTracing::GetThreadRelativeContext(v35);
                if ( *((_DWORD *)v52 + 499) != v12 )
                  CallStackContext::TraceFailure(v52, "CMFSampleGrabberStreamSink::FinishProcessSample", 1045, v12);
              }
              if ( !g_wppLevels )
                goto LABEL_74;
              v29 = 97;
LABEL_90:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v29,
                &WPP_9e0691ee672e3c34414a5076d2e5426e_Traceguids,
                this,
                v12);
LABEL_74:
              if ( v66 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
              goto LABEL_76;
            }
          }
          DebugInfo = this[11].DebugInfo;
          v77 = DebugInfo;
          if ( DebugInfo )
            (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)&DebugInfo->Type + 8LL))(DebugInfo);
          v18 = *(_QWORD *)&this[11].LockCount;
          v76 = v18;
          if ( v18 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
          OwningThread = (__int64 *)this[11].OwningThread;
          v75 = OwningThread;
          if ( OwningThread )
            (*(void (__fastcall **)(__int64 *))(*OwningThread + 8))(OwningThread);
          LockSemaphore = (__int64 *)this[11].LockSemaphore;
          v74 = LockSemaphore;
          if ( LockSemaphore )
            (*(void (__fastcall **)(__int64 *))(*LockSemaphore + 8))(LockSemaphore);
          EnterCriticalSection(this + 14);
          LeaveCriticalSection(this + 13);
          if ( v18 )
          {
            cInitialSize = 0;
            v59 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v62 + 240LL))(v62, &cInitialSize);
            ppMFAttributes = 0;
            v12 = v59;
            if ( v59 >= 0 )
            {
              v12 = MFCreateAttributes(&ppMFAttributes, cInitialSize);
              if ( v12 >= 0 )
              {
                v12 = (*(__int64 (__fastcall **)(__int64, IMFAttributes *))(*(_QWORD *)v62 + 256LL))(
                        v62,
                        ppMFAttributes);
                if ( v12 >= 0 )
                  v12 = (*(__int64 (__fastcall **)(__int64, GUID *, _QWORD, __int64, __int64, __int64, int, IMFAttributes *))(*(_QWORD *)v18 + 88LL))(
                          v18,
                          &v79,
                          v68,
                          v71,
                          v70,
                          v73,
                          v67,
                          ppMFAttributes);
              }
            }
            ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppMFAttributes);
          }
          else
          {
            if ( OwningThread )
            {
              v21 = *OwningThread;
              v22 = OwningThread;
            }
            else
            {
              if ( !LockSemaphore )
              {
                v12 = (*(__int64 (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG, GUID *, _QWORD, __int64, __int64, __int64, int))(*(_QWORD *)&DebugInfo->Type + 72LL))(
                        DebugInfo,
                        &v79,
                        v68,
                        v71,
                        v70,
                        v73,
                        v67);
                goto LABEL_68;
              }
              v21 = *LockSemaphore;
              v22 = LockSemaphore;
            }
            v12 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v21 + 96))(v22, v62);
          }
          if ( OwningThread )
          {
LABEL_42:
            if ( v12 < 0 )
            {
              v53 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24);
                CallStackTracing::s_wpInstance = v54;
                if ( v54
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
                {
                  v53 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v53 = &qword_1803CE250;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                }
              }
              if ( *((_BYTE *)v53 + 8) )
              {
                v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
                if ( *((_DWORD *)v55 + 499) != v12 )
                  CallStackContext::TraceFailure(v55, "CMFSampleGrabberStreamSink::FinishProcessSample", 1136, v12);
              }
              if ( g_wppLevels )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  98,
                  &WPP_9e0691ee672e3c34414a5076d2e5426e_Traceguids,
                  this,
                  v12);
              LeaveCriticalSection(this + 14);
              ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v74);
              ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v75);
              ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v76);
              ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v77);
              ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v66);
              CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v61);
              ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v64);
              ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v63);
              ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v62);
              ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v69);
              return (unsigned int)v12;
            }
            cInitialSize = 0;
            LeaveCriticalSection(this + 14);
            if ( LockSemaphore )
              (*(void (__fastcall **)(__int64 *))(*LockSemaphore + 16))(LockSemaphore);
            if ( OwningThread )
              (*(void (__fastcall **)(__int64 *))(*OwningThread + 16))(OwningThread);
            if ( v18 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            if ( DebugInfo )
              (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)&DebugInfo->Type + 16LL))(DebugInfo);
            if ( v66 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
            CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v61);
            v25 = cInitialSize;
            v1 = lpCriticalSection;
            goto LABEL_54;
          }
LABEL_68:
          if ( !LockSemaphore )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 32LL))(v66);
          goto LABEL_42;
        }
        v47 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15);
          CallStackTracing::s_wpInstance = v48;
          if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
          {
            v47 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v47 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v47 + 8) )
        {
          v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
          if ( *((_DWORD *)v49 + 499) != v12 )
            CallStackContext::TraceFailure(v49, "CMFSampleGrabberStreamSink::FinishProcessSample", 1008, v12);
        }
        if ( !g_wppLevels )
          goto LABEL_139;
        v44 = 92;
        v60 = v12;
        goto LABEL_138;
      }
      v33 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v33 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v33 + 8) )
      {
        v46 = CallStackTracing::GetThreadRelativeContext(v33);
        if ( *((_DWORD *)v46 + 499) != v12 )
          CallStackContext::TraceFailure(v46, "CMFSampleGrabberStreamSink::FinishProcessSample", 1002, v12);
      }
      if ( !g_wppLevels )
        goto LABEL_76;
      v34 = 91;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v34, &WPP_9e0691ee672e3c34414a5076d2e5426e_Traceguids, this, v12);
LABEL_76:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v61);
    if ( v64 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    if ( v63 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    if ( v62 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    goto LABEL_84;
  }
  v12 = 0;
  v25 = 1;
  if ( !v63 )
    goto LABEL_60;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v61,
    "CMFSampleGrabberStreamSink::FinishProcessSample",
    1141);
  if ( (unsigned __int8)byte_1803CECEA >= 0x10u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 99, &WPP_9e0691ee672e3c34414a5076d2e5426e_Traceguids);
  v12 = (*(__int64 (__fastcall **)(HANDLE, __int64))(*(_QWORD *)this[11].LockSemaphore + 104LL))(
          this[11].LockSemaphore,
          v63);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v61);
LABEL_54:
  if ( v64 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
  if ( v63 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
  if ( v62 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
LABEL_60:
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v25 )
    goto LABEL_84;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18009d1e0  push    rbp
0x18009d1e2  push    rbx
0x18009d1e3  push    rsi
0x18009d1e4  push    rdi
0x18009d1e5  push    r12
0x18009d1e7  push    r13
0x18009d1e9  push    r14
0x18009d1eb  push    r15
0x18009d1ed  lea     rbp, [rsp-1Fh]
0x18009d1f2  sub     rsp, 0F8h
0x18009d1f9  mov     rax, cs:__security_cookie
0x18009d200  xor     rax, rsp
0x18009d203  mov     [rbp+57h+var_48], rax
0x18009d207  lea     r15, [rcx+208h]
0x18009d20e  mov     r13, rcx
0x18009d211  mov     rcx, r15; lpCriticalSection
0x18009d214  mov     [rbp+57h+lpCriticalSection], r15
0x18009d218  call    cs:__imp_EnterCriticalSection
0x18009d21f  nop     dword ptr [rax+rax+00h]
0x18009d224  mov     rcx, [r13+408h]
0x18009d22b  xor     r14d, r14d
0x18009d22e  mov     [rbp+57h+var_A8], r14
0x18009d232  test    rcx, rcx
0x18009d235  jz      loc_18009D802
0x18009d23b  mov     rax, [rcx+8]
0x18009d23f  mov     rbx, [rcx]
0x18009d242  mov     [rbp+57h+var_A8], rbx
0x18009d246  mov     [r13+408h], rax
0x18009d24d  test    rax, rax
0x18009d250  jnz     loc_18009D69F
0x18009d256  mov     [r13+410h], r14
0x18009d25d  mov     rax, [r13+260h]
0x18009d264  lea     r8, [rsp+130h+var_D8]
0x18009d269  mov     [rcx+8], rax
0x18009d26d  lea     rdx, _GUID_c40a00f2_b93a_4d80_ae8c_5a1c634f58e4
0x18009d274  mov     [r13+260h], rcx
0x18009d27b  mov     rcx, rbx
0x18009d27e  dec     dword ptr [r13+418h]
0x18009d285  mov     [rsp+130h+var_D8], r14
0x18009d28a  mov     [rbp+57h+var_D0], r14
0x18009d28e  mov     [rbp+57h+var_C8], r14
0x18009d292  mov     rax, [rbx]
0x18009d295  mov     rax, [rax]
0x18009d298  call    cs:__guard_dispatch_icall_fptr
0x18009d29e  mov     rax, [rbx]
0x18009d2a1  lea     r8, [rbp+57h+var_C8]
0x18009d2a5  lea     rdx, _GUID_a6fdf644_50ab_4cb8_b4d8_656cb597b6ca
0x18009d2ac  mov     rcx, rbx
0x18009d2af  mov     rax, [rax]
0x18009d2b2  call    cs:__guard_dispatch_icall_fptr
0x18009d2b8  mov     rax, [rbx]
0x18009d2bb  lea     r8, [rbp+57h+var_D0]
0x18009d2bf  lea     rdx, _GUID_df598932_f10c_4e39_bba2_c308f101daa3
0x18009d2c6  mov     rcx, rbx
0x18009d2c9  mov     rax, [rax]
0x18009d2cc  call    cs:__guard_dispatch_icall_fptr
0x18009d2d2  cmp     [rbp+57h+var_C8], r14
0x18009d2d6  jnz     loc_18009DEDB
0x18009d2dc  cmp     [rsp+130h+var_D8], r14
0x18009d2e1  jz      loc_18009E021
0x18009d2e7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18009d2ee  test    rcx, rcx
0x18009d2f1  jz      loc_18009D9D0
0x18009d2f7  cmp     byte ptr [rcx+8], 0
0x18009d2fb  lea     r14, aCmfsamplegrabb_64; "CMFSampleGrabberStreamSink::FinishProce"...
0x18009d302  mov     edi, 1
0x18009d307  jz      short loc_18009D331
0x18009d309  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009d30e  mov     ecx, [rax+7C4h]
0x18009d314  cmp     ecx, [rax+7C8h]
0x18009d31a  jnb     short loc_18009D32B
0x18009d31c  add     rcx, rcx
0x18009d31f  mov     [rax+rcx*8], r14
0x18009d323  mov     dword ptr [rax+rcx*8+8], 3CEh
0x18009d32b  add     [rax+7C4h], edi
0x18009d331  cmp     cs:byte_1803CECEA, 10h
0x18009d338  lea     rsi, WPP_9e0691ee672e3c34414a5076d2e5426e_Traceguids
0x18009d33f  jnb     loc_18009D924
0x18009d345  mov     rcx, [rsp+130h+var_D8]
0x18009d34a  lea     rdx, [rbp+57h+var_98]
0x18009d34e  mov     rax, 7FFFFFFFFFFFFFFFh
0x18009d358  mov     [rbp+57h+var_98], rax
0x18009d35c  mov     rax, [rcx]
0x18009d35f  mov     rax, [rax+118h]
0x18009d366  call    cs:__guard_dispatch_icall_fptr
0x18009d36c  mov     r12d, eax
0x18009d36f  test    eax, eax
0x18009d371  js      loc_18009D941
0x18009d377  mov     r12, 7FFFFFFFFFFFFFFFh
0x18009d381  cmp     [rbp+57h+var_98], r12
0x18009d385  jz      loc_18009DB58
0x18009d38b  mov     rcx, [rsp+130h+var_D8]
0x18009d390  lea     rdx, [rbp+57h+var_A0]
0x18009d394  mov     [rbp+57h+var_A0], r12
0x18009d398  mov     rax, [rcx]
0x18009d39b  mov     rax, [rax+128h]
0x18009d3a2  call    cs:__guard_dispatch_icall_fptr
0x18009d3a8  test    eax, eax
0x18009d3aa  js      loc_18009D696
0x18009d3b0  mov     rcx, [rsp+130h+var_D8]
0x18009d3b5  lea     rdx, [rbp+57h+var_AC]
0x18009d3b9  mov     [rbp+57h+var_AC], 0
0x18009d3c0  mov     rax, [rcx]
0x18009d3c3  mov     rax, [rax+108h]
0x18009d3ca  call    cs:__guard_dispatch_icall_fptr
0x18009d3d0  mov     r12d, eax
0x18009d3d3  test    eax, eax
0x18009d3d5  js      loc_18009D884
0x18009d3db  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18009d3e2  mov     rcx, [r13+200h]
0x18009d3e9  lea     rdx, [rbp+57h+var_58]
0x18009d3ed  movdqu  [rbp+57h+var_58], xmm0
0x18009d3f2  mov     rax, [rcx]
0x18009d3f5  mov     rax, [rax+108h]
0x18009d3fc  call    cs:__guard_dispatch_icall_fptr
0x18009d402  mov     r12d, eax
0x18009d405  test    eax, eax
0x18009d407  js      loc_18009DC5E
0x18009d40d  mov     rcx, [rsp+130h+var_D8]
0x18009d412  lea     rdx, [rbp+57h+var_B8]
0x18009d416  mov     [rbp+57h+var_B8], 0
0x18009d41e  mov     rax, [rcx]
0x18009d421  mov     rax, [rax+148h]
0x18009d428  call    cs:__guard_dispatch_icall_fptr
0x18009d42e  mov     r12d, eax
0x18009d431  test    eax, eax
0x18009d433  js      loc_18009D70F
0x18009d439  cmp     cs:byte_1803CECEA, 8
0x18009d440  jnb     loc_18009D97A
0x18009d446  mov     eax, [r13+1ECh]
0x18009d44d  cmp     eax, [r13+1D8h]
0x18009d454  jnb     short loc_18009D494
0x18009d456  inc     eax
0x18009d458  lea     rdx, [r13+68h]
0x18009d45c  mov     [r13+1ECh], eax
0x18009d463  mov     rax, r13
0x18009d466  neg     rax
0x18009d469  sbb     rcx, rcx
0x18009d46c  xor     r8d, r8d; int
0x18009d46f  and     rcx, rdx; this
0x18009d472  mov     edx, 131h; met
0x18009d477  call    ?QueueSimpleEvent@@YAJPEAVCMFMediaEventGenerator@@KJ@Z; QueueSimpleEvent(CMFMediaEventGenerator *,ulong,long)
0x18009d47c  mov     r12d, eax
0x18009d47f  test    eax, eax
0x18009d481  js      loc_18009D7B6
0x18009d487  cmp     cs:byte_1803CECEA, 8
0x18009d48e  jnb     loc_18009D9A5
0x18009d494  xor     r12d, r12d
0x18009d497  mov     [rbp+57h+var_88], r12
0x18009d49b  mov     [rbp+57h+var_B0], r12d
0x18009d49f  cmp     [r13+1C8h], r12
0x18009d4a6  jnz     short loc_18009D4B5
0x18009d4a8  cmp     [r13+1D0h], r12
0x18009d4af  jz      loc_18009D8D0
0x18009d4b5  mov     r15, [r13+1B8h]
0x18009d4bc  mov     [rbp+57h+var_68], r15
0x18009d4c0  test    r15, r15
0x18009d4c3  jz      short loc_18009D4D5
0x18009d4c5  mov     rax, [r15]
0x18009d4c8  mov     rcx, r15
0x18009d4cb  mov     rax, [rax+8]
0x18009d4cf  call    cs:__guard_dispatch_icall_fptr
0x18009d4d5  mov     r14, [r13+1C0h]
0x18009d4dc  mov     [rbp+57h+var_70], r14
0x18009d4e0  test    r14, r14
0x18009d4e3  jnz     loc_18009DF42
0x18009d4e9  mov     rdi, [r13+1C8h]
0x18009d4f0  mov     [rbp+57h+var_78], rdi
0x18009d4f4  test    rdi, rdi
0x18009d4f7  jnz     loc_18009DF57
0x18009d4fd  mov     rsi, [r13+1D0h]
0x18009d504  mov     [rbp+57h+var_80], rsi
0x18009d508  test    rsi, rsi
0x18009d50b  jz      short loc_18009D51D
0x18009d50d  mov     rax, [rsi]
0x18009d510  mov     rcx, rsi
0x18009d513  mov     rax, [rax+8]
0x18009d517  call    cs:__guard_dispatch_icall_fptr
0x18009d51d  lea     rcx, [r13+230h]; lpCriticalSection
0x18009d524  call    cs:__imp_EnterCriticalSection
0x18009d52b  nop     dword ptr [rax+rax+00h]
0x18009d530  lea     rcx, [r13+208h]; lpCriticalSection
0x18009d537  call    cs:__imp_LeaveCriticalSection
0x18009d53e  nop     dword ptr [rax+rax+00h]
0x18009d543  test    r14, r14
0x18009d546  jnz     loc_18009DF6C
0x18009d54c  test    rdi, rdi
0x18009d54f  jz      loc_18009D6A8
0x18009d555  mov     rax, [rdi]
0x18009d558  mov     rcx, rdi
0x18009d55b  mov     rdx, [rsp+130h+var_D8]
0x18009d560  mov     rax, [rax+60h]
0x18009d564  call    cs:__guard_dispatch_icall_fptr
0x18009d56a  mov     r12d, eax
0x18009d56d  test    rdi, rdi
0x18009d570  jz      loc_18009D6F0
0x18009d576  test    r12d, r12d
0x18009d579  js      loc_18009DD79
0x18009d57f  xor     eax, eax
0x18009d581  lea     rcx, [r13+230h]; lpCriticalSection
0x18009d588  mov     [rbp+57h+cInitialSize], eax
0x18009d58b  call    cs:__imp_LeaveCriticalSection
0x18009d592  nop     dword ptr [rax+rax+00h]
0x18009d597  test    rsi, rsi
0x18009d59a  jz      short loc_18009D5AC
0x18009d59c  mov     rax, [rsi]
0x18009d59f  mov     rcx, rsi
0x18009d5a2  mov     rax, [rax+10h]
0x18009d5a6  call    cs:__guard_dispatch_icall_fptr
0x18009d5ac  test    rdi, rdi
0x18009d5af  jz      short loc_18009D5C1
0x18009d5b1  mov     rax, [rdi]
0x18009d5b4  mov     rcx, rdi
0x18009d5b7  mov     rax, [rax+10h]
0x18009d5bb  call    cs:__guard_dispatch_icall_fptr
0x18009d5c1  test    r14, r14
0x18009d5c4  jz      short loc_18009D5D6
0x18009d5c6  mov     rax, [r14]
0x18009d5c9  mov     rcx, r14
0x18009d5cc  mov     rax, [rax+10h]
0x18009d5d0  call    cs:__guard_dispatch_icall_fptr
0x18009d5d6  test    r15, r15
0x18009d5d9  jz      short loc_18009D5EB
0x18009d5db  mov     rax, [r15]
0x18009d5de  mov     rcx, r15
0x18009d5e1  mov     rax, [rax+10h]
0x18009d5e5  call    cs:__guard_dispatch_icall_fptr
0x18009d5eb  mov     rcx, [rbp+57h+var_B8]
0x18009d5ef  test    rcx, rcx
0x18009d5f2  jz      short loc_18009D601
0x18009d5f4  mov     rax, [rcx]
0x18009d5f7  mov     rax, [rax+10h]
0x18009d5fb  call    cs:__guard_dispatch_icall_fptr
0x18009d601  lea     rcx, [rsp+130h+var_E0]; this
0x18009d606  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009d60b  mov     edi, [rbp+57h+cInitialSize]
0x18009d60e  mov     r15, [rbp+57h+lpCriticalSection]
0x18009d612  mov     rcx, [rbp+57h+var_C8]
0x18009d616  test    rcx, rcx
0x18009d619  jz      short loc_18009D628
0x18009d61b  mov     rax, [rcx]
0x18009d61e  mov     rax, [rax+10h]
0x18009d622  call    cs:__guard_dispatch_icall_fptr
0x18009d628  mov     rcx, [rbp+57h+var_D0]
0x18009d62c  test    rcx, rcx
0x18009d62f  jz      short loc_18009D63E
0x18009d631  mov     rax, [rcx]
0x18009d634  mov     rax, [rax+10h]
0x18009d638  call    cs:__guard_dispatch_icall_fptr
0x18009d63e  mov     rcx, [rsp+130h+var_D8]
0x18009d643  test    rcx, rcx
0x18009d646  jz      short loc_18009D655
0x18009d648  mov     rax, [rcx]
0x18009d64b  mov     rax, [rax+10h]
0x18009d64f  call    cs:__guard_dispatch_icall_fptr
0x18009d655  test    rbx, rbx
0x18009d658  jz      short loc_18009D66A
0x18009d65a  mov     rax, [rbx]
0x18009d65d  mov     rcx, rbx
0x18009d660  mov     rax, [rax+10h]
0x18009d664  call    cs:__guard_dispatch_icall_fptr
0x18009d66a  test    edi, edi
0x18009d66c  jnz     loc_18009D7A2
0x18009d672  mov     eax, r12d
0x18009d675  mov     rcx, [rbp+57h+var_48]
0x18009d679  xor     rcx, rsp; StackCookie
0x18009d67c  call    __security_check_cookie
0x18009d681  add     rsp, 0F8h
0x18009d688  pop     r15
0x18009d68a  pop     r14
0x18009d68c  pop     r13
0x18009d68e  pop     r12
0x18009d690  pop     rdi
0x18009d691  pop     rsi
0x18009d692  pop     rbx
0x18009d693  pop     rbp
0x18009d694  retn
0x18009d696  mov     [rbp+57h+var_A0], r12
0x18009d69a  jmp     loc_18009D3B0
0x18009d69f  mov     [rax+10h], r14
0x18009d6a3  jmp     loc_18009D25D
0x18009d6a8  test    rsi, rsi
0x18009d6ab  jz      short loc_18009D6B8
0x18009d6ad  mov     rax, [rsi]
0x18009d6b0  mov     rcx, rsi
0x18009d6b3  jmp     loc_18009D55B
0x18009d6b8  mov     ecx, [rbp+57h+var_B0]
0x18009d6bb  mov     rdx, [rbp+57h+var_88]
0x18009d6bf  mov     rax, [r15]
0x18009d6c2  mov     r10, [rbp+57h+var_A0]
0x18009d6c6  mov     r9, [rbp+57h+var_98]
0x18009d6ca  mov     r8d, [rbp+57h+var_AC]
0x18009d6ce  mov     rax, [rax+48h]
0x18009d6d2  mov     [rsp+130h+var_100], ecx
0x18009d6d6  mov     rcx, r15
0x18009d6d9  mov     [rsp+130h+var_108], rdx
0x18009d6de  lea     rdx, [rbp+57h+var_58]
0x18009d6e2  mov     [rsp+130h+var_110], r10
0x18009d6e7  call    cs:__guard_dispatch_icall_fptr
0x18009d6ed  mov     r12d, eax
  ... truncated ...
```
