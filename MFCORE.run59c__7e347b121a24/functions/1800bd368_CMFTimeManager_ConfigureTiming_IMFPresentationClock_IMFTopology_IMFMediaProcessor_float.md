# CMFTimeManager::ConfigureTiming(IMFPresentationClock *,IMFTopology *,IMFMediaProcessor *,float)

- ea: `0x1800bd368`
- end: `0x1800bdd1d`
- name: `?ConfigureTiming@CMFTimeManager@@QEAAJPEAUIMFPresentationClock@@PEAUIMFTopology@@PEAUIMFMediaProcessor@@M@Z`
- size: `2485`
- prototype: `__int64 __usercall@<rax>(CMFTimeManager *__hidden this@<rcx>, struct IMFPresentationClock *@<rdx>, struct IMFTopology *@<r8>, struct IMFMediaProcessor *@<r9>, float)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800bd1dc`

## callees

- `0x18001616c`
- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x18005ebe0`
- `0x180063f00`
- `0x18006b388`
- `0x1800717b4`
- `0x180074744`
- `0x1800bbfbc`
- `0x1800bc278`
- `0x1800bc408`
- `0x1800bc778`
- `0x1800bcc40`
- `0x1800bd368`
- `0x1800bdd24`
- `0x1800be5d0`
- `0x1800bee30`
- `0x1800bf288`
- `0x1800cf200`
- `0x1800ec0e0`
- `0x18013b2a8`
- `0x1801ca6d4`
- `0x180296a90`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bd510`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bd56c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bd510`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bd56c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bd392`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bd392`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd599`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd62d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd6c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd793`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd845`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd8dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd975`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bda0d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bdaa5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd599`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd62d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd6c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd793`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd845`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd8dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bd975`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bda0d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bdaa5`

## string_xrefs

- `0x1800bd39e`: `CMFTimeManager::ConfigureTiming`
- `0x1800bd73d`: `CMFTimeManager::ConfigureTiming`
- `0x1800bd768`: `CMFTimeManager::ConfigureTiming`
- `0x1800bd822`: `CMFTimeManager::ConfigureTiming`
- `0x1800bd8ba`: `CMFTimeManager::ConfigureTiming`
- `0x1800bd952`: `CMFTimeManager::ConfigureTiming`
- `0x1800bd9ea`: `CMFTimeManager::ConfigureTiming`
- `0x1800bda82`: `CMFTimeManager::ConfigureTiming`
- `0x1800bdb34`: `CMFTimeManager::ConfigureTiming`

## pseudocode

```c
__int64 __fastcall CMFTimeManager::ConfigureTiming(
        IUnknown **this,
        IUnknown *a2,
        struct IMFTopology *a3,
        struct IMFMediaProcessor *a4,
        float a5)
{
  struct _RTL_CRITICAL_SECTION *v5; // r12
  __int64 v10; // rdx
  int RatelessTimeSource; // ebx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  unsigned int v17; // ebx
  IUnknown *v18; // r14
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // r8
  CallStackTracing *v30; // rcx
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  __int64 v33; // rdx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  __int64 v40; // rdx
  struct CallStackContext *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  __int64 v48; // rdx
  struct CallStackContext *v49; // rax
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  __int64 *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  __int64 *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  CMFTimeManager *v62; // [rsp+20h] [rbp-10h]
  LPVOID ppvObject; // [rsp+70h] [rbp+40h] BYREF
  IUnknown *punkObject; // [rsp+78h] [rbp+48h] BYREF

  v5 = (struct _RTL_CRITICAL_SECTION *)(this + 3);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 3));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&ppvObject, "CMFTimeManager::ConfigureTiming", 264);
  if ( a2 && a3 )
  {
    LODWORD(ppvObject) = 5;
    punkObject = 0;
    CMFTimeManager::Reset((CMFTimeManager *)this, 1);
    this[13] = a2;
    ((void (__fastcall *)(IUnknown *))a2->lpVtbl->AddRef)(a2);
    RatelessTimeSource = CMFTimeManager::BuildMediaSourceList((CMFTimeManager *)this, a3);
    if ( RatelessTimeSource < 0 )
    {
      v31 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v12);
        CallStackTracing::s_wpInstance = v32;
        if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
        {
          v31 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v31 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v31 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != RatelessTimeSource )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CMFTimeManager::ConfigureTiming",
            283,
            RatelessTimeSource);
      }
      if ( !g_wppLevels )
        goto LABEL_20;
      v33 = 12;
      goto LABEL_66;
    }
    RatelessTimeSource = CMFTimeManager::BuildMediaSinkList((CMFTimeManager *)this, a3, 0);
    if ( RatelessTimeSource < 0 )
    {
      v35 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14);
        CallStackTracing::s_wpInstance = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v35 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
        if ( *((_DWORD *)v37 + 499) != RatelessTimeSource )
          CallStackContext::TraceFailure(v37, "CMFTimeManager::ConfigureTiming", 286, RatelessTimeSource);
      }
      if ( !g_wppLevels )
        goto LABEL_20;
      v33 = 13;
      goto LABEL_66;
    }
    if ( a5 == 0.0 )
    {
      if ( (unsigned __int8)byte_1803CECE9 >= 8u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, &WPP_8fcbadda05503f555d8aab8603d64240_Traceguids, this);
      RatelessTimeSource = CMFTimeManager::GetRatelessTimeSource(
                             (CMFTimeManager *)this,
                             (struct IMFPresentationTimeSource **)&punkObject);
      if ( RatelessTimeSource >= 0 )
      {
        v17 = 2;
        goto LABEL_9;
      }
      v38 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16);
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
        v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
        if ( *((_DWORD *)v41 + 499) != RatelessTimeSource )
          CallStackContext::TraceFailure(v41, "CMFTimeManager::ConfigureTiming", 296, RatelessTimeSource);
      }
      if ( !g_wppLevels )
      {
LABEL_25:
        v18 = punkObject;
        goto LABEL_18;
      }
      v40 = 15;
    }
    else
    {
      if ( this[10] )
      {
        LODWORD(ppvObject) = 0;
        punkObject = 0;
        if ( (unsigned __int8)byte_1803CECE9 >= 8u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 16, &WPP_8fcbadda05503f555d8aab8603d64240_Traceguids, this);
        v18 = this[10];
        ((void (__fastcall *)(IUnknown *))v18->lpVtbl->AddRef)(v18);
        v17 = 4;
        ComSmartPtr<IUnknown>::Release(this + 11);
        CMFTimeManager::GetTopologyTimeSource(
          (CMFTimeManager *)this,
          (struct IMFPresentationTimeSource **)&punkObject,
          (enum CMFTimeManager::TIMESOURCE_TYPE *)&ppvObject);
        if ( punkObject )
        {
          ppvObject = 0;
          if ( MFGetService(
                 punkObject,
                 &MF_CLOCK_RATE_MATCH_SERVICE,
                 &GUID_828e7c7e_84f2_4b45_8cee_5bb3d827fcf5,
                 &ppvObject) < 0 )
          {
            if ( g_wppLevels >= 2u )
            {
              v62 = (CMFTimeManager *)this;
              WPP_SF_sqD(*((_QWORD *)WPP_GLOBAL_Control + 2));
            }
          }
          else
          {
            if ( g_wppLevels >= 2u )
              WPP_SF_sq(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                17,
                (unsigned int)&WPP_8fcbadda05503f555d8aab8603d64240_Traceguids,
                0,
                (char)this);
            ComSmartPtr<IKsControl>::operator=(this + 11, &punkObject);
          }
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppvObject);
        }
        else if ( g_wppLevels >= 2u )
        {
          WPP_SF_sq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            (unsigned int)&WPP_8fcbadda05503f555d8aab8603d64240_Traceguids,
            0,
            (char)this);
        }
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&punkObject);
        v5 = (struct _RTL_CRITICAL_SECTION *)(this + 3);
        goto LABEL_10;
      }
      RatelessTimeSource = CMFTimeManager::GetTopologyTimeSource(
                             (CMFTimeManager *)this,
                             (struct IMFPresentationTimeSource **)&punkObject,
                             (enum CMFTimeManager::TIMESOURCE_TYPE *)&ppvObject);
      if ( RatelessTimeSource >= 0 )
      {
        v17 = (unsigned int)ppvObject;
LABEL_9:
        v18 = punkObject;
LABEL_10:
        if ( (unsigned __int8)byte_1803CECE9 >= 8u )
          WPP_SF_qqD(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            21,
            &WPP_8fcbadda05503f555d8aab8603d64240_Traceguids,
            this,
            v18,
            v17);
        if ( v18 )
        {
          LOBYTE(v62) = 1;
          RatelessTimeSource = CMFTimeManager::SetNewTimeSourceOnClock(this, v18, v17, this[13], v62);
          if ( RatelessTimeSource < 0 )
          {
            v46 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20);
              CallStackTracing::s_wpInstance = v47;
              if ( v47
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
              {
                v46 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v46 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v46 + 8) )
            {
              v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
              if ( *((_DWORD *)v49 + 499) != RatelessTimeSource )
                CallStackContext::TraceFailure(v49, "CMFTimeManager::ConfigureTiming", 371, RatelessTimeSource);
            }
            if ( !g_wppLevels )
              goto LABEL_18;
            v48 = 23;
          }
          else
          {
            RatelessTimeSource = CMFTimeManager::BuildMediaSinkList((CMFTimeManager *)this, a3, 1);
            if ( RatelessTimeSource < 0 )
            {
              v50 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22);
                CallStackTracing::s_wpInstance = v51;
                if ( v51
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
                {
                  v50 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v50 = &qword_1803CE250;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                }
              }
              if ( *((_BYTE *)v50 + 8) )
              {
                v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
                if ( *((_DWORD *)v52 + 499) != RatelessTimeSource )
                  CallStackContext::TraceFailure(v52, "CMFTimeManager::ConfigureTiming", 380, RatelessTimeSource);
              }
              if ( !g_wppLevels )
                goto LABEL_18;
              v48 = 24;
            }
            else
            {
              RatelessTimeSource = CMFTimeManager::PassPresentationClockToSources((CMFTimeManager *)this);
              if ( RatelessTimeSource < 0 )
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
                  if ( *((_DWORD *)v55 + 499) != RatelessTimeSource )
                    CallStackContext::TraceFailure(v55, "CMFTimeManager::ConfigureTiming", 386, RatelessTimeSource);
                }
                if ( !g_wppLevels )
                  goto LABEL_18;
                v48 = 25;
              }
              else
              {
                RatelessTimeSource = CMFTimeManager::PassPresentationClockToSinks((CMFTimeManager *)this);
                if ( RatelessTimeSource < 0 )
                {
                  v56 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26);
                    CallStackTracing::s_wpInstance = v57;
                    if ( v57
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
                    {
                      v56 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v56 = &qword_1803CE250;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                    }
                  }
                  if ( *((_BYTE *)v56 + 8) )
                  {
                    v58 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v56);
                    if ( *((_DWORD *)v58 + 499) != RatelessTimeSource )
                      CallStackContext::TraceFailure(v58, "CMFTimeManager::ConfigureTiming", 392, RatelessTimeSource);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_18;
                  v48 = 26;
                }
                else
                {
                  CMFTimeManager::PassPresentationClockToTransforms((CMFTimeManager *)this, a3);
                  RatelessTimeSource = CMFTimeManager::SetupDriftPrevention((CMFTimeManager *)this, a4);
                  if ( RatelessTimeSource >= 0 )
                    goto LABEL_18;
                  v59 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28);
                    CallStackTracing::s_wpInstance = v60;
                    if ( v60
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
                    {
                      v59 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v59 = &qword_1803CE250;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                    }
                  }
                  if ( *((_BYTE *)v59 + 8) )
                  {
                    v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
                    if ( *((_DWORD *)v61 + 499) != RatelessTimeSource )
                      CallStackContext::TraceFailure(v61, "CMFTimeManager::ConfigureTiming", 402, RatelessTimeSource);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_18;
                  v48 = 27;
                }
              }
            }
          }
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v48,
            &WPP_8fcbadda05503f555d8aab8603d64240_Traceguids,
            this,
            RatelessTimeSource);
LABEL_18:
          if ( v18 )
            ((void (__fastcall *)(IUnknown *))v18->lpVtbl->Release)(v18);
          goto LABEL_20;
        }
        v43 = (__int64 *)CallStackTracing::s_wpInstance;
        RatelessTimeSource = -1072875845;
        if ( !CallStackTracing::s_wpInstance )
        {
          v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16);
          CallStackTracing::s_wpInstance = v44;
          if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
          {
            v43 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v43 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v43 + 8) )
        {
          v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
          if ( *((_DWORD *)v45 + 499) != -1072875845 )
            CallStackContext::TraceFailure(v45, "CMFTimeManager::ConfigureTiming", 364, -1072875845);
        }
        if ( !g_wppLevels )
          goto LABEL_20;
        v33 = 22;
LABEL_66:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v33,
          &WPP_8fcbadda05503f555d8aab8603d64240_Traceguids,
          this,
          RatelessTimeSource);
LABEL_20:
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&ppvObject);
        LeaveCriticalSection(v5);
        return (unsigned int)RatelessTimeSource;
      }
      v30 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v30 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v30 + 8) )
      {
        v42 = CallStackTracing::GetThreadRelativeContext(v30);
        if ( *((_DWORD *)v42 + 499) != RatelessTimeSource )
          CallStackContext::TraceFailure(v42, "CMFTimeManager::ConfigureTiming", 354, RatelessTimeSource);
      }
      if ( !g_wppLevels )
        goto LABEL_25;
      v40 = 20;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v40,
      &WPP_8fcbadda05503f555d8aab8603d64240_Traceguids,
      this,
      RatelessTimeSource);
    goto LABEL_25;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&ppvObject);
  LeaveCriticalSection(v5);
  return 3222091451LL;
}

```

## disassembly

```asm
0x1800bd368  mov     [rsp-38h+arg_10], rbx
0x1800bd36d  push    rbp
0x1800bd36e  push    rsi
0x1800bd36f  push    rdi
0x1800bd370  push    r12
0x1800bd372  push    r13
0x1800bd374  push    r14
0x1800bd376  push    r15
0x1800bd378  mov     rbp, rsp
0x1800bd37b  sub     rsp, 30h
0x1800bd37f  lea     r12, [rcx+18h]
0x1800bd383  mov     rdi, rcx
0x1800bd386  mov     rcx, r12; lpCriticalSection
0x1800bd389  mov     r13, r9
0x1800bd38c  mov     r15, r8
0x1800bd38f  mov     rbx, rdx
0x1800bd392  call    cs:__imp_EnterCriticalSection
0x1800bd399  nop     dword ptr [rax+rax+00h]
0x1800bd39e  lea     rsi, aCmftimemanager_24; "CMFTimeManager::ConfigureTiming"
0x1800bd3a5  mov     r8d, 108h; int
0x1800bd3ab  mov     rdx, rsi; char *
0x1800bd3ae  lea     rcx, [rbp+ppvObject]; this
0x1800bd3b2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800bd3b7  xor     r14d, r14d
0x1800bd3ba  test    rbx, rbx
0x1800bd3bd  jz      loc_1800BD560
0x1800bd3c3  test    r15, r15
0x1800bd3c6  jz      loc_1800BD560
0x1800bd3cc  lea     edx, [r14+1]; int
0x1800bd3d0  mov     dword ptr [rbp+ppvObject], 5
0x1800bd3d7  mov     rcx, rdi; this
0x1800bd3da  mov     [rbp+punkObject], r14
0x1800bd3de  call    ?Reset@CMFTimeManager@@QEAAXH@Z; CMFTimeManager::Reset(int)
0x1800bd3e3  mov     [rdi+68h], rbx
0x1800bd3e7  mov     rcx, rbx
0x1800bd3ea  mov     rax, [rbx]
0x1800bd3ed  mov     rax, [rax+8]
0x1800bd3f1  call    cs:__guard_dispatch_icall_fptr
0x1800bd3f7  mov     rdx, r15; struct IMFTopology *
0x1800bd3fa  mov     rcx, rdi; this
0x1800bd3fd  call    ?BuildMediaSourceList@CMFTimeManager@@IEAAJPEAUIMFTopology@@@Z; CMFTimeManager::BuildMediaSourceList(IMFTopology *)
0x1800bd402  mov     ebx, eax
0x1800bd404  test    eax, eax
0x1800bd406  js      loc_1800BD58D
0x1800bd40c  xor     r8d, r8d; int
0x1800bd40f  mov     rdx, r15; struct IMFTopology *
0x1800bd412  mov     rcx, rdi; this
0x1800bd415  call    ?BuildMediaSinkList@CMFTimeManager@@IEAAJPEAUIMFTopology@@H@Z; CMFTimeManager::BuildMediaSinkList(IMFTopology *,int)
0x1800bd41a  mov     ebx, eax
0x1800bd41c  test    eax, eax
0x1800bd41e  js      loc_1800BD621
0x1800bd424  xorps   xmm0, xmm0
0x1800bd427  lea     rsi, WPP_8fcbadda05503f555d8aab8603d64240_Traceguids
0x1800bd42e  ucomiss xmm0, [rbp+arg_20]
0x1800bd432  jp      short loc_1800BD43A
0x1800bd434  jz      loc_1800BDB4B
0x1800bd43a  cmp     [rdi+50h], r14
0x1800bd43e  jnz     loc_1800BDBB3
0x1800bd444  lea     r8, [rbp+ppvObject]; enum CMFTimeManager::TIMESOURCE_TYPE *
0x1800bd448  mov     rcx, rdi; this
0x1800bd44b  lea     rdx, [rbp+punkObject]; struct IMFPresentationTimeSource **
0x1800bd44f  call    ?GetTopologyTimeSource@CMFTimeManager@@IEAAJPEAPEAUIMFPresentationTimeSource@@PEAW4TIMESOURCE_TYPE@1@@Z; CMFTimeManager::GetTopologyTimeSource(IMFPresentationTimeSource * *,CMFTimeManager::TIMESOURCE_TYPE *)
0x1800bd454  mov     ebx, eax
0x1800bd456  test    eax, eax
0x1800bd458  js      loc_1800BD537
0x1800bd45e  mov     ebx, dword ptr [rbp+ppvObject]
0x1800bd461  mov     r14, [rbp+punkObject]
0x1800bd465  cmp     cs:byte_1803CECE9, 8
0x1800bd46c  jnb     loc_1800BDCDF
0x1800bd472  test    r14, r14
0x1800bd475  jz      loc_1800BD782
0x1800bd47b  mov     r9, [rdi+68h]
0x1800bd47f  mov     r8d, ebx
0x1800bd482  mov     rdx, r14
0x1800bd485  mov     byte ptr [rsp+30h+var_10], 1
0x1800bd48a  mov     rcx, rdi
0x1800bd48d  call    ?SetNewTimeSourceOnClock@CMFTimeManager@@IEAAJPEAUIMFPresentationTimeSource@@W4TIMESOURCE_TYPE@1@PEAUIMFPresentationClock@@_N@Z; CMFTimeManager::SetNewTimeSourceOnClock(IMFPresentationTimeSource *,CMFTimeManager::TIMESOURCE_TYPE,IMFPresentationClock *,bool)
0x1800bd492  mov     ebx, eax
0x1800bd494  test    eax, eax
0x1800bd496  js      loc_1800BD839
0x1800bd49c  mov     r8d, 1; int
0x1800bd4a2  mov     rdx, r15; struct IMFTopology *
0x1800bd4a5  mov     rcx, rdi; this
0x1800bd4a8  call    ?BuildMediaSinkList@CMFTimeManager@@IEAAJPEAUIMFTopology@@H@Z; CMFTimeManager::BuildMediaSinkList(IMFTopology *,int)
0x1800bd4ad  mov     ebx, eax
0x1800bd4af  test    eax, eax
0x1800bd4b1  js      loc_1800BD8D1
0x1800bd4b7  mov     rcx, rdi; this
0x1800bd4ba  call    ?PassPresentationClockToSources@CMFTimeManager@@IEAAJXZ; CMFTimeManager::PassPresentationClockToSources(void)
0x1800bd4bf  mov     ebx, eax
0x1800bd4c1  test    eax, eax
0x1800bd4c3  js      loc_1800BD969
0x1800bd4c9  mov     rcx, rdi; this
0x1800bd4cc  call    ?PassPresentationClockToSinks@CMFTimeManager@@IEAAJXZ; CMFTimeManager::PassPresentationClockToSinks(void)
0x1800bd4d1  mov     ebx, eax
0x1800bd4d3  test    eax, eax
0x1800bd4d5  js      loc_1800BDA01
0x1800bd4db  mov     rdx, r15; struct IMFTopology *
0x1800bd4de  mov     rcx, rdi; this
0x1800bd4e1  call    ?PassPresentationClockToTransforms@CMFTimeManager@@IEAAJPEAUIMFTopology@@@Z; CMFTimeManager::PassPresentationClockToTransforms(IMFTopology *)
0x1800bd4e6  mov     rdx, r13; struct IMFMediaProcessor *
0x1800bd4e9  mov     rcx, rdi; this
0x1800bd4ec  call    ?SetupDriftPrevention@CMFTimeManager@@IEAAJPEAUIMFMediaProcessor@@@Z; CMFTimeManager::SetupDriftPrevention(IMFMediaProcessor *)
0x1800bd4f1  mov     ebx, eax
0x1800bd4f3  test    eax, eax
0x1800bd4f5  js      loc_1800BDA99
0x1800bd4fb  test    r14, r14
0x1800bd4fe  jnz     loc_1800BDD08
0x1800bd504  lea     rcx, [rbp+ppvObject]; this
0x1800bd508  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800bd50d  mov     rcx, r12; lpCriticalSection
0x1800bd510  call    cs:__imp_LeaveCriticalSection
0x1800bd517  nop     dword ptr [rax+rax+00h]
0x1800bd51c  mov     eax, ebx
0x1800bd51e  mov     rbx, [rsp+30h+arg_10]
0x1800bd526  add     rsp, 30h
0x1800bd52a  pop     r15
0x1800bd52c  pop     r14
0x1800bd52e  pop     r13
0x1800bd530  pop     r12
0x1800bd532  pop     rdi
0x1800bd533  pop     rsi
0x1800bd534  pop     rbp
0x1800bd535  retn
0x1800bd537  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800bd53e  test    rcx, rcx
0x1800bd541  jz      short loc_1800BD57F
0x1800bd543  cmp     [rcx+8], r14b
0x1800bd547  jnz     loc_1800BD754
0x1800bd54d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bd554  jnb     loc_1800BDB8F
0x1800bd55a  mov     r14, [rbp+punkObject]
0x1800bd55e  jmp     short loc_1800BD4FB
0x1800bd560  lea     rcx, [rbp+ppvObject]; this
0x1800bd564  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800bd569  mov     rcx, r12; lpCriticalSection
0x1800bd56c  call    cs:__imp_LeaveCriticalSection
0x1800bd573  nop     dword ptr [rax+rax+00h]
0x1800bd578  mov     eax, 0C00D36BBh
0x1800bd57d  jmp     short loc_1800BD51E
0x1800bd57f  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800bd584  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd58b  jmp     short loc_1800BD543
0x1800bd58d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd594  test    rcx, rcx
0x1800bd597  jnz     short loc_1800BD5D1
0x1800bd599  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bd5a0  nop     dword ptr [rax+rax+00h]
0x1800bd5a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd5ac  mov     rcx, rax
0x1800bd5af  test    rax, rax
0x1800bd5b2  jz      short loc_1800BD5EE
0x1800bd5b4  mov     rax, [rax]
0x1800bd5b7  mov     edx, 7F0h
0x1800bd5bc  mov     rax, [rax+8]
0x1800bd5c0  call    cs:__guard_dispatch_icall_fptr
0x1800bd5c6  test    eax, eax
0x1800bd5c8  jz      short loc_1800BD5EE
0x1800bd5ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800bd5d1  cmp     [rcx+8], r14b
0x1800bd5d5  jnz     short loc_1800BD5FE
0x1800bd5d7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bd5de  jb      loc_1800BD504
0x1800bd5e4  mov     edx, 0Ch
0x1800bd5e9  jmp     loc_1800BD67D
0x1800bd5ee  lea     rcx, qword_1803CE250
0x1800bd5f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd5fc  jmp     short loc_1800BD5D1
0x1800bd5fe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bd603  cmp     [rax+7CCh], ebx
0x1800bd609  jz      short loc_1800BD5D7
0x1800bd60b  mov     r9d, ebx; int
0x1800bd60e  mov     r8d, 11Bh; int
0x1800bd614  mov     rdx, rsi; char *
0x1800bd617  mov     rcx, rax; this
0x1800bd61a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bd61f  jmp     short loc_1800BD5D7
0x1800bd621  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd628  test    rcx, rcx
0x1800bd62b  jnz     short loc_1800BD665
0x1800bd62d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bd634  nop     dword ptr [rax+rax+00h]
0x1800bd639  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd640  mov     rcx, rax
0x1800bd643  test    rax, rax
0x1800bd646  jz      short loc_1800BD689
0x1800bd648  mov     rax, [rax]
0x1800bd64b  mov     edx, 7F0h
0x1800bd650  mov     rax, [rax+8]
0x1800bd654  call    cs:__guard_dispatch_icall_fptr
0x1800bd65a  test    eax, eax
0x1800bd65c  jz      short loc_1800BD689
0x1800bd65e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800bd665  cmp     [rcx+8], r14b
0x1800bd669  jnz     short loc_1800BD699
0x1800bd66b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bd672  jb      loc_1800BD504
0x1800bd678  mov     edx, 0Dh
0x1800bd67d  lea     r8, WPP_8fcbadda05503f555d8aab8603d64240_Traceguids
0x1800bd684  jmp     loc_1800BD7E6
0x1800bd689  lea     rcx, qword_1803CE250
0x1800bd690  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd697  jmp     short loc_1800BD665
0x1800bd699  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bd69e  cmp     [rax+7CCh], ebx
0x1800bd6a4  jz      short loc_1800BD66B
0x1800bd6a6  mov     r9d, ebx; int
0x1800bd6a9  mov     r8d, 11Eh; int
0x1800bd6af  mov     rdx, rsi; char *
0x1800bd6b2  mov     rcx, rax; this
0x1800bd6b5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bd6ba  jmp     short loc_1800BD66B
0x1800bd6bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd6c3  test    rcx, rcx
0x1800bd6c6  jnz     short loc_1800BD700
0x1800bd6c8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bd6cf  nop     dword ptr [rax+rax+00h]
0x1800bd6d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd6db  mov     rcx, rax
0x1800bd6de  test    rax, rax
0x1800bd6e1  jz      short loc_1800BD71D
0x1800bd6e3  mov     rax, [rax]
0x1800bd6e6  mov     edx, 7F0h
0x1800bd6eb  mov     rax, [rax+8]
0x1800bd6ef  call    cs:__guard_dispatch_icall_fptr
0x1800bd6f5  test    eax, eax
0x1800bd6f7  jz      short loc_1800BD71D
0x1800bd6f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800bd700  cmp     [rcx+8], r14b
0x1800bd704  jnz     short loc_1800BD72D
0x1800bd706  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bd70d  jb      loc_1800BD55A
0x1800bd713  mov     edx, 0Fh
0x1800bd718  jmp     loc_1800BDB94
0x1800bd71d  lea     rcx, qword_1803CE250
0x1800bd724  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd72b  jmp     short loc_1800BD700
0x1800bd72d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bd732  cmp     [rax+7CCh], ebx
0x1800bd738  jz      short loc_1800BD706
0x1800bd73a  mov     r9d, ebx; int
0x1800bd73d  lea     rdx, aCmftimemanager_24; "CMFTimeManager::ConfigureTiming"
0x1800bd744  mov     r8d, 128h; int
0x1800bd74a  mov     rcx, rax; this
0x1800bd74d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bd752  jmp     short loc_1800BD706
0x1800bd754  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bd759  cmp     [rax+7CCh], ebx
0x1800bd75f  jz      loc_1800BD54D
0x1800bd765  mov     r9d, ebx; int
0x1800bd768  lea     rdx, aCmftimemanager_24; "CMFTimeManager::ConfigureTiming"
0x1800bd76f  mov     r8d, 162h; int
0x1800bd775  mov     rcx, rax; this
0x1800bd778  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bd77d  jmp     loc_1800BD54D
0x1800bd782  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd789  mov     ebx, 0C00D36BBh
0x1800bd78e  test    rcx, rcx
0x1800bd791  jnz     short loc_1800BD7CB
0x1800bd793  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bd79a  nop     dword ptr [rax+rax+00h]
0x1800bd79f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd7a6  mov     rcx, rax
0x1800bd7a9  test    rax, rax
0x1800bd7ac  jz      short loc_1800BD802
0x1800bd7ae  mov     rax, [rax]
0x1800bd7b1  mov     edx, 7F0h
0x1800bd7b6  mov     rax, [rax+8]
0x1800bd7ba  call    cs:__guard_dispatch_icall_fptr
0x1800bd7c0  test    eax, eax
0x1800bd7c2  jz      short loc_1800BD802
0x1800bd7c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800bd7cb  cmp     byte ptr [rcx+8], 0
0x1800bd7cf  jnz     short loc_1800BD812
0x1800bd7d1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bd7d8  jb      loc_1800BD504
0x1800bd7de  mov     edx, 16h
0x1800bd7e3  mov     r8, rsi
0x1800bd7e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd7ed  mov     r9, rdi
0x1800bd7f0  mov     dword ptr [rsp+30h+var_10], ebx
0x1800bd7f4  mov     rcx, [rcx+10h]
0x1800bd7f8  call    WPP_SF_qD
0x1800bd7fd  jmp     loc_1800BD504
0x1800bd802  lea     rcx, qword_1803CE250
0x1800bd809  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd810  jmp     short loc_1800BD7CB
0x1800bd812  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bd817  cmp     [rax+7CCh], ebx
0x1800bd81d  jz      short loc_1800BD7D1
0x1800bd81f  mov     r9d, ebx; int
0x1800bd822  lea     rdx, aCmftimemanager_24; "CMFTimeManager::ConfigureTiming"
0x1800bd829  mov     r8d, 16Ch; int
0x1800bd82f  mov     rcx, rax; this
0x1800bd832  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bd837  jmp     short loc_1800BD7D1
0x1800bd839  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bd840  test    rcx, rcx
0x1800bd843  jnz     short loc_1800BD87D
0x1800bd845  call    cs:__imp_MFGetCallStackTracingWeakReference
  ... truncated ...
```
