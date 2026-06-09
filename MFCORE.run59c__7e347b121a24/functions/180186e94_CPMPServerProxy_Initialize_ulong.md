# CPMPServerProxy::Initialize(ulong)

- ea: `0x180186e94`
- end: `0x180187f1e`
- name: `?Initialize@CPMPServerProxy@@QEAAJK@Z`
- size: `4234`
- prototype: `__int64 __fastcall(CPMPServerProxy *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `24`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1801b8aec`
- `0x18029bd14`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x18006b388`
- `0x180093088`
- `0x1800ce134`
- `0x1800ce29c`
- `0x1800cf5c8`
- `0x1800ec0e0`
- `0x18012add8`
- `0x18015c3c8`
- `0x180186e94`
- `0x180187f24`
- `0x1801887a4`
- `0x1801887f4`
- `0x1801a145c`
- `0x1802540b8`
- `0x180258480`
- `0x18025ab48`
- `0x18029c4b0`
- `0x18029de40`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801873a4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801873a4`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18018756d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18018756d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18018704e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18018704e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180186f61`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180186f61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801873bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180187646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801873bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180187646`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180187590`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180187590`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180187028`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180187028`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180187039`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180187039`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1801877d6`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1801877d6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1801870d5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1801870d5`
- `MFPlat!MFGetRandomNumber` at `0x1801871b7`
- `MFPlat!MFGetRandomNumber` at `0x1801871b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801870f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801871d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801873eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801874a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801875bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180187675`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180187718`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801877f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801878de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180187991`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180187a4d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180187aff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180187bbc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180187c70`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180187d2d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180187de2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180187e94`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801870f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801871d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801873eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801874a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801875bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180187675`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180187718`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801877f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801878de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180187991`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180187a4d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180187aff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180187bbc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180187c70`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180187d2d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180187de2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180187e94`
- `ext-ms-win-com-ole32-l1-1-0!CreateItemMoniker` at `0x1801878bc`
- `ext-ms-win-com-ole32-l1-1-0!CreateItemMoniker` at `0x1801878bc`
- `ext-ms-win-com-ole32-l1-1-0!GetRunningObjectTable` at `0x18018796f`
- `ext-ms-win-com-ole32-l1-1-0!GetRunningObjectTable` at `0x18018796f`

## pseudocode

```c
__int64 __fastcall CPMPServerProxy::Initialize(CPMPServerProxy *this, unsigned int a2)
{
  HANDLE EventW; // r15
  int RunningObjectTable; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  unsigned __int64 v18; // rcx
  __int64 v19; // r9
  const WCHAR *v20; // rax
  signed int LastError; // eax
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  const unsigned __int16 *v25; // rax
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  void *v30; // rax
  DWORD v31; // eax
  void *v32; // rcx
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  signed int v36; // eax
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  __int64 *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  __int64 *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  __int64 *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  __int64 *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  __int64 *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  __int64 *v67; // rcx
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  __int64 *v70; // rcx
  CallStackTracing *v71; // rax
  struct CallStackContext *v72; // rax
  int bAlertable; // [rsp+20h] [rbp-E0h]
  DWORD ExitCode; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v75[8]; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  struct IUnknown *v77; // [rsp+48h] [rbp-B8h] BYREF
  struct IUnknown *v78; // [rsp+50h] [rbp-B0h] BYREF
  LPRUNNINGOBJECTTABLE pprot; // [rsp+58h] [rbp-A8h] BYREF
  LPMONIKER ppmk; // [rsp+60h] [rbp-A0h] BYREF
  struct IUnknown *v81; // [rsp+68h] [rbp-98h] BYREF
  __int64 v82; // [rsp+70h] [rbp-90h] BYREF
  HANDLE Handles[2]; // [rsp+78h] [rbp-88h] BYREF
  GUID pguid; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v85; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v86; // [rsp+A4h] [rbp-5Ch]
  int v87; // [rsp+ACh] [rbp-54h]
  char *v88; // [rsp+B0h] [rbp-50h]
  char v89; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v90; // [rsp+1C0h] [rbp+C0h] BYREF
  int v91; // [rsp+1C8h] [rbp+C8h]
  int v92; // [rsp+1CCh] [rbp+CCh]
  char *v93; // [rsp+1D0h] [rbp+D0h]
  char v94; // [rsp+1D8h] [rbp+D8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v75, "CPMPServerProxy::Initialize", 2001);
  v91 = 0;
  v77 = 0;
  v78 = 0;
  v81 = 0;
  v82 = 0;
  v90 = v90 & 0xFFFFFFF8 | 1;
  v92 = 128;
  v93 = &v94;
  v86 = HIDWORD(v90);
  v87 = 128;
  v85 = v85 & 0xFFFFFFF8 | 1;
  pv = (LPVOID)HIDWORD(v90);
  v88 = &v89;
  pguid = 0;
  ppmk = (LPMONIKER)HIDWORD(v90);
  pprot = (LPRUNNINGOBJECTTABLE)HIDWORD(v90);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( *((_DWORD *)this + 26) )
  {
    if ( !(unsigned int)CPMPServerProxy::IsProcessAlive(this) )
    {
      if ( (unsigned __int8)byte_1803CECE9 >= 8u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 126, &WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids, this);
      CPMPServerProxy::_TerminatePMPProcess(this);
      *((_DWORD *)this + 28) = 1;
    }
    if ( *((_DWORD *)this + 26) )
    {
      EventW = 0;
      RunningObjectTable = 0;
      if ( (unsigned __int8)byte_1803CECE9 >= 8u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 146, &WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids, this);
      goto LABEL_9;
    }
  }
  RunningObjectTable = CoCreateGuid(&pguid);
  if ( RunningObjectTable < 0 )
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != RunningObjectTable )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CPMPServerProxy::Initialize", 2029, RunningObjectTable);
    }
    if ( g_wppLevels )
    {
      v12 = 127;
LABEL_26:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        &WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids,
        this,
        RunningObjectTable);
      goto LABEL_14;
    }
    goto LABEL_14;
  }
  CMFBaseStringT<unsigned short>::AppendChar(&v85, 47);
  RunningObjectTable = MFGetRandomNumber(&v82, 8u);
  if ( RunningObjectTable >= 0 )
  {
    CMFBaseStringT<unsigned short>::AppendUInt64(&v85, v82, 16);
    CMFBaseStringT<unsigned short>::AppendChar(&v85, 95);
    CMFBaseStringT<unsigned short>::AppendUInt(&v85, (unsigned int)this, 16);
    ExitCode = -1;
    if ( (int)UIntPtrToLong(0xAu, (int *)&ExitCode) >= 0 )
      CMFBaseStringT<unsigned short>::_Append(&v85, L"/PMPServer", ExitCode);
    else
      LODWORD(v86) = -2147024785;
    if ( (unsigned __int8)byte_1803CECE9 >= 8u )
    {
      v16 = CMFBaseStringT<unsigned short>::PContents(&v85);
      WPP_SF_qS(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        129,
        (unsigned int)&WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids,
        (_DWORD)this,
        v16);
    }
    v17 = CMFBaseStringT<unsigned short>::PContents(&v85);
    ExitCode = -1;
    if ( v17 )
    {
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)(v17 + 2 * v18) );
      if ( (int)UIntPtrToLong(v18, (int *)&ExitCode) >= 0 )
        CMFBaseStringT<unsigned short>::_Append(&v90, v19, ExitCode);
      else
        HIDWORD(v90) = -2147024785;
    }
    ExitCode = -1;
    if ( (int)UIntPtrToLong(6u, (int *)&ExitCode) >= 0 )
      CMFBaseStringT<unsigned short>::_Append(&v90, L"/Start", ExitCode);
    else
      HIDWORD(v90) = -2147024785;
    v20 = (const WCHAR *)CMFBaseStringT<unsigned short>::PContents(&v90);
    EventW = CreateEventW(0, 1, 0, v20);
    if ( !EventW )
    {
      LastError = GetLastError();
      RunningObjectTable = LastError;
      if ( LastError > 0 )
        RunningObjectTable = (unsigned __int16)LastError | 0x80070000;
      if ( RunningObjectTable < 0 )
      {
        v22 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v23;
          if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
          {
            v22 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v22 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v22 + 8) )
        {
          v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
          if ( *((_DWORD *)v24 + 499) != RunningObjectTable )
            CallStackContext::TraceFailure(v24, "CPMPServerProxy::Initialize", 2050, RunningObjectTable);
        }
        if ( g_wppLevels )
        {
          v12 = 130;
          goto LABEL_26;
        }
        goto LABEL_14;
      }
    }
    v25 = (const unsigned __int16 *)CMFBaseStringT<unsigned short>::PContents(&v85);
    RunningObjectTable = CPMPServerProxy::StartupPMPProcess(this, v25, a2, &pguid);
    if ( RunningObjectTable < 0 )
    {
      v26 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
        {
          v26 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( *((_DWORD *)v28 + 499) != RunningObjectTable )
          CallStackContext::TraceFailure(v28, "CPMPServerProxy::Initialize", 2058, RunningObjectTable);
      }
      if ( !g_wppLevels )
        goto LABEL_12;
      v29 = 131;
      goto LABEL_77;
    }
    v30 = (void *)*((_QWORD *)this + 10);
    *((_DWORD *)this + 22) = a2;
    Handles[0] = EventW;
    Handles[1] = v30;
    v31 = WaitForMultipleObjectsEx(2u, Handles, 0, 0x4E20u, 0);
    if ( v31 == 1 )
    {
      v32 = (void *)*((_QWORD *)this + 10);
      ExitCode = 0;
      if ( GetExitCodeProcess(v32, &ExitCode) )
      {
        RunningObjectTable = ExitCode;
        if ( (ExitCode & 0x80000000) != 0 )
        {
          v33 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v34;
            if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
            {
              v33 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v33 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v33 + 8) )
          {
            v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
            if ( *((_DWORD *)v35 + 499) != RunningObjectTable )
              CallStackContext::TraceFailure(v35, "CPMPServerProxy::Initialize", 2075, RunningObjectTable);
          }
          if ( !g_wppLevels )
            goto LABEL_12;
          v29 = 132;
          goto LABEL_77;
        }
LABEL_115:
        if ( (unsigned __int8)byte_1803CECE9 >= 8u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 135, &WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids, this);
        RunningObjectTable = StringFromCLSID(&pguid, (LPOLESTR *)&pv);
        if ( RunningObjectTable < 0 )
        {
          v43 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
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
            if ( *((_DWORD *)v45 + 499) != RunningObjectTable )
              CallStackContext::TraceFailure(v45, "CPMPServerProxy::Initialize", 2094, RunningObjectTable);
          }
          if ( !g_wppLevels )
            goto LABEL_12;
          v6 = 136;
          goto LABEL_128;
        }
        if ( (unsigned __int8)IsCreateItemMonikerPresent() && (unsigned __int8)IsCreateItemMonikerPresent() )
        {
          RunningObjectTable = CreateItemMoniker(L"!", (LPCOLESTR)pv, &ppmk);
          if ( RunningObjectTable < 0 )
          {
            v46 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
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
              v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
              if ( *((_DWORD *)v48 + 499) != RunningObjectTable )
                CallStackContext::TraceFailure(v48, "CPMPServerProxy::Initialize", 2098, RunningObjectTable);
            }
            if ( !g_wppLevels )
              goto LABEL_12;
            v6 = 137;
            goto LABEL_128;
          }
          RunningObjectTable = GetRunningObjectTable(0, &pprot);
          if ( RunningObjectTable < 0 )
          {
            v49 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v50;
              if ( v50
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
              {
                v49 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v49 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v49 + 8) )
            {
              v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
              if ( *((_DWORD *)v51 + 499) != RunningObjectTable )
                CallStackContext::TraceFailure(v51, "CPMPServerProxy::Initialize", 2100, RunningObjectTable);
            }
            if ( !g_wppLevels )
              goto LABEL_12;
            v6 = 138;
            goto LABEL_128;
          }
          RunningObjectTable = ((__int64 (__fastcall *)(LPRUNNINGOBJECTTABLE, LPMONIKER, struct IUnknown **))pprot->lpVtbl->GetObjectA)(
                                 pprot,
                                 ppmk,
                                 &v77);
          if ( RunningObjectTable < 0 )
          {
            v52 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v53;
              if ( v53
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
              {
                v52 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v52 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v52 + 8) )
            {
              v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
              if ( *((_DWORD *)v54 + 499) != RunningObjectTable )
                CallStackContext::TraceFailure(v54, "CPMPServerProxy::Initialize", 2102, RunningObjectTable);
            }
            if ( !g_wppLevels )
              goto LABEL_12;
            v6 = 139;
            goto LABEL_128;
          }
        }
        else
        {
          RunningObjectTable = CPMPServerProxy::GetObjectFromMachineGlobalObjectTable(
                                 this,
                                 (const unsigned __int16 *)pv,
                                 &v77);
          if ( RunningObjectTable < 0 )
          {
            v55 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v56;
              if ( v56
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
              {
                v55 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v55 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v55 + 8) )
            {
              v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
              if ( *((_DWORD *)v57 + 499) != RunningObjectTable )
                CallStackContext::TraceFailure(v57, "CPMPServerProxy::Initialize", 2106, RunningObjectTable);
            }
            if ( !g_wppLevels )
              goto LABEL_12;
            v6 = 140;
            goto LABEL_128;
          }
        }
        RunningObjectTable = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v77->lpVtbl->QueryInterface)(
                               v77,
                               &IID_IMFPMPServer,
                               &v78);
        if ( RunningObjectTable >= 0 )
        {
          RunningObjectTable = CGITPtr::Set(
                                 (CPMPServerProxy *)((char *)this + 104),
                                 &GUID_994e23af_1cc2_493c_b9fa_46f1cb040fa4,
                                 v78);
          if ( RunningObjectTable >= 0 )
          {
            RunningObjectTable = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v77->lpVtbl->QueryInterface)(
                                   v77,
                                   &IID_IMFPMPServerInternal,
                                   &v81);
            if ( RunningObjectTable >= 0 )
            {
              RunningObjectTable = CGITPtr::Set(
                                     (CPMPServerProxy *)((char *)this + 108),
                                     &GUID_772ff18d_138b_4257_873c_1b8e0ce1d183,
                                     v81);
              if ( RunningObjectTable >= 0 )
              {
                RunningObjectTable = ((__int64 (__fastcall *)(struct IUnknown *))v78->lpVtbl[1].QueryInterface)(v78);
                if ( RunningObjectTable >= 0 )
                {
LABEL_9:
                  ++*((_DWORD *)this + 18);
                  if ( (unsigned __int8)byte_1803CECE9 < 8u )
                    goto LABEL_12;
                  v6 = 147;
                  bAlertable = *((_DWORD *)this + 18);
                  v7 = *((_QWORD *)WPP_GLOBAL_Control + 7);
                  goto LABEL_11;
                }
                v70 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                  CallStackTracing::s_wpInstance = v71;
                  if ( v71
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
                  {
                    v70 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v70 = &qword_1803CE250;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                  }
                }
                if ( *((_BYTE *)v70 + 8) )
                {
                  v72 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v70);
                  if ( *((_DWORD *)v72 + 499) != RunningObjectTable )
                    CallStackContext::TraceFailure(v72, "CPMPServerProxy::Initialize", 2118, RunningObjectTable);
                }
                if ( !g_wppLevels )
                  goto LABEL_12;
                v6 = 145;
              }
              else
              {
                v67 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                  CallStackTracing::s_wpInstance = v68;
                  if ( v68
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(v68, 2032) )
                  {
                    v67 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v67 = &qword_1803CE250;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                  }
                }
                if ( *((_BYTE *)v67 + 8) )
                {
                  v69 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v67);
                  if ( *((_DWORD *)v69 + 499) != RunningObjectTable )
                    CallStackContext::TraceFailure(v69, "CPMPServerProxy::Initialize", 2116, RunningObjectTable);
                }
                if ( !g_wppLevels )
                  goto LABEL_12;
                v6 = 144;
              }
            }
            else
            {
              v64 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                CallStackTracing::s_wpInstance = v65;
                if ( v65
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
                {
                  v64 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v64 = &qword_1803CE250;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                }
              }
              if ( *((_BYTE *)v64 + 8) )
              {
                v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v64);
                if ( *((_DWORD *)v66 + 499) != RunningObjectTable )
                  CallStackContext::TraceFailure(v66, "CPMPServerProxy::Initialize", 2115, RunningObjectTable);
              }
              if ( !g_wppLevels )
                goto LABEL_12;
              v6 = 143;
            }
          }
          else
          {
            v61 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v62;
              if ( v62
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
              {
                v61 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v61 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v61 + 8) )
            {
              v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
              if ( *((_DWORD *)v63 + 499) != RunningObjectTable )
                CallStackContext::TraceFailure(v63, "CPMPServerProxy::Initialize", 2111, RunningObjectTable);
            }
            if ( !g_wppLevels )
              goto LABEL_12;
            v6 = 142;
          }
        }
        else
        {
          v58 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v59;
            if ( v59 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
            {
              v58 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v58 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v58 + 8) )
          {
            v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
            if ( *((_DWORD *)v60 + 499) != RunningObjectTable )
              CallStackContext::TraceFailure(v60, "CPMPServerProxy::Initialize", 2109, RunningObjectTable);
          }
          if ( !g_wppLevels )
            goto LABEL_12;
          v6 = 141;
        }
LABEL_128:
        bAlertable = RunningObjectTable;
        v7 = *((_QWORD *)WPP_GLOBAL_Control + 2);
LABEL_11:
        WPP_SF_qD(v7, v6, &WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids, this, bAlertable);
        goto LABEL_12;
      }
      v36 = GetLastError();
      RunningObjectTable = v36;
      if ( v36 > 0 )
        RunningObjectTable = (unsigned __int16)v36 | 0x80070000;
      if ( RunningObjectTable >= 0 )
        goto LABEL_115;
      v37 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v38;
        if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
        {
          v37 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v37 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v37 + 8) )
      {
        v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
        if ( *((_DWORD *)v39 + 499) != RunningObjectTable )
          CallStackContext::TraceFailure(v39, "CPMPServerProxy::Initialize", 2079, RunningObjectTable);
      }
      if ( !g_wppLevels )
        goto LABEL_12;
      v29 = 133;
    }
    else
    {
      if ( !v31 )
        goto LABEL_115;
      v40 = (__int64 *)CallStackTracing::s_wpInstance;
      RunningObjectTable = -2147467259;
      if ( !CallStackTracing::s_wpInstance )
      {
        v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v41;
        if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
        {
          v40 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v40 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v40 + 8) )
      {
        v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
        if ( *((_DWORD *)v42 + 499) != -2147467259 )
          CallStackContext::TraceFailure(v42, "CPMPServerProxy::Initialize", 2087, -2147467259);
      }
      if ( !g_wppLevels )
        goto LABEL_12;
      v29 = 134;
    }
LABEL_77:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v29,
      &WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids,
      this,
      RunningObjectTable);
LABEL_12:
    if ( EventW )
      CloseHandle(EventW);
    goto LABEL_14;
  }
  v13 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
    CallStackTracing::s_wpInstance = v14;
    if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
    {
      v13 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v13 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v13 + 8) )
  {
    v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
    if ( *((_DWORD *)v15 + 499) != RunningObjectTable )
      CallStackContext::TraceFailure(v15, "CPMPServerProxy::Initialize", 2034, RunningObjectTable);
  }
  if ( g_wppLevels )
  {
    v12 = 128;
    goto LABEL_26;
  }
LABEL_14:
  CoTaskMemFree(pv);
  pv = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&pprot);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppmk);
  CMFBaseStringT<char>::~CMFBaseStringT<char>(&v85);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v81);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v78);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v77);
  CMFBaseStringT<char>::~CMFBaseStringT<char>(&v90);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v75);
  return (unsigned int)RunningObjectTable;
}

```

## disassembly

```asm
0x180186e94  push    rbp
0x180186e96  push    rbx
0x180186e97  push    rsi
0x180186e98  push    rdi
0x180186e99  push    r12
0x180186e9b  push    r13
0x180186e9d  push    r14
0x180186e9f  push    r15
0x180186ea1  lea     rbp, [rsp-1F8h]
0x180186ea9  sub     rsp, 2F8h
0x180186eb0  mov     rax, cs:__security_cookie
0x180186eb7  xor     rax, rsp
0x180186eba  mov     [rbp+230h+var_50], rax
0x180186ec1  mov     esi, edx
0x180186ec3  mov     rdi, rcx
0x180186ec6  lea     rdx, aCpmpserverprox; "CPMPServerProxy::Initialize"
0x180186ecd  mov     r8d, 7D1h; int
0x180186ed3  lea     rcx, [rsp+330h+var_2F8]; this
0x180186ed8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180186edd  mov     eax, [rbp+230h+var_170]
0x180186ee3  xor     r13d, r13d
0x180186ee6  mov     ecx, 0FFFFFFF9h
0x180186eeb  mov     [rbp+230h+var_16C], r13
0x180186ef2  and     eax, ecx
0x180186ef4  mov     [rsp+330h+var_2E8], r13
0x180186ef9  xorps   xmm0, xmm0
0x180186efc  mov     [rsp+330h+var_2E0], r13
0x180186f01  lea     r15d, [r13+1]
0x180186f05  mov     [rsp+330h+var_2C8], r13
0x180186f0a  or      eax, r15d
0x180186f0d  mov     [rsp+330h+var_2C0], r13
0x180186f12  mov     [rbp+230h+var_170], eax
0x180186f18  lea     edx, [r15+7Fh]
0x180186f1c  lea     rax, [rbp+230h+var_158]
0x180186f23  mov     [rbp+230h+var_164], edx
0x180186f29  mov     [rbp+230h+var_160], rax
0x180186f30  mov     eax, [rbp+230h+var_290]
0x180186f33  and     eax, ecx
0x180186f35  mov     [rbp+230h+var_28C], r13
0x180186f39  or      eax, r15d
0x180186f3c  mov     [rbp+230h+var_284], edx
0x180186f3f  mov     [rbp+230h+var_290], eax
0x180186f42  lea     rcx, [rdi+20h]; lpCriticalSection
0x180186f46  lea     rax, [rbp+230h+var_278]
0x180186f4a  mov     [rsp+330h+pv], r13
0x180186f4f  mov     [rbp+230h+var_280], rax
0x180186f53  movups  xmmword ptr [rbp+230h+pguid.Data1], xmm0
0x180186f57  mov     [rsp+330h+ppmk], r13
0x180186f5c  mov     [rsp+330h+pprot], r13
0x180186f61  call    cs:__imp_EnterCriticalSection
0x180186f68  nop     dword ptr [rax+rax+00h]
0x180186f6d  lea     r14, [rdi+68h]
0x180186f71  cmp     [r14], r13d
0x180186f74  jz      loc_1801870D1
0x180186f7a  mov     rcx, rdi; this
0x180186f7d  call    ?IsProcessAlive@CPMPServerProxy@@QEAAHXZ; CPMPServerProxy::IsProcessAlive(void)
0x180186f82  test    eax, eax
0x180186f84  jnz     short loc_180186FB8
0x180186f86  cmp     cs:byte_1803CECE9, 8
0x180186f8d  jb      short loc_180186FAC
0x180186f8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180186f96  lea     edx, [rax+7Eh]
0x180186f99  mov     r9, rdi
0x180186f9c  lea     r8, WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids
0x180186fa3  mov     rcx, [rcx+38h]
0x180186fa7  call    WPP_SF_q
0x180186fac  mov     rcx, rdi; this
0x180186faf  call    ?_TerminatePMPProcess@CPMPServerProxy@@IEAAJXZ; CPMPServerProxy::_TerminatePMPProcess(void)
0x180186fb4  mov     [rdi+70h], r15d
0x180186fb8  cmp     [r14], r13d
0x180186fbb  jz      loc_1801870D1
0x180186fc1  mov     r15, r13
0x180186fc4  cmp     cs:byte_1803CECE9, 8
0x180186fcb  lea     rsi, WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids
0x180186fd2  mov     ebx, r13d
0x180186fd5  jb      short loc_180186FF2
0x180186fd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180186fde  mov     edx, 92h
0x180186fe3  mov     r9, rdi
0x180186fe6  mov     r8, rsi
0x180186fe9  mov     rcx, [rcx+38h]
0x180186fed  call    WPP_SF_q
0x180186ff2  inc     dword ptr [rdi+48h]
0x180186ff5  mov     eax, [rdi+48h]
0x180186ff8  cmp     cs:byte_1803CECE9, 8
0x180186fff  jb      short loc_180187020
0x180187001  mov     rcx, cs:WPP_GLOBAL_Control
0x180187008  mov     edx, 93h
0x18018700d  mov     [rsp+330h+bAlertable], eax
0x180187011  mov     rcx, [rcx+38h]
0x180187015  mov     r8, rsi
0x180187018  mov     r9, rdi
0x18018701b  call    WPP_SF_qD
0x180187020  test    r15, r15
0x180187023  jz      short loc_180187034
0x180187025  mov     rcx, r15; hObject
0x180187028  call    cs:__imp_CloseHandle
0x18018702f  nop     dword ptr [rax+rax+00h]
0x180187034  mov     rcx, [rsp+330h+pv]; pv
0x180187039  call    cs:__imp_CoTaskMemFree
0x180187040  nop     dword ptr [rax+rax+00h]
0x180187045  lea     rcx, [rdi+20h]; lpCriticalSection
0x180187049  mov     [rsp+330h+pv], r13
0x18018704e  call    cs:__imp_LeaveCriticalSection
0x180187055  nop     dword ptr [rax+rax+00h]
0x18018705a  lea     rcx, [rsp+330h+pprot]
0x18018705f  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180187064  lea     rcx, [rsp+330h+ppmk]
0x180187069  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18018706e  lea     rcx, [rbp+230h+var_290]
0x180187072  call    ??1?$CMFBaseStringT@D@@QEAA@XZ; CMFBaseStringT<char>::~CMFBaseStringT<char>(void)
0x180187077  lea     rcx, [rsp+330h+var_2C8]
0x18018707c  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180187081  lea     rcx, [rsp+330h+var_2E0]
0x180187086  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18018708b  lea     rcx, [rsp+330h+var_2E8]
0x180187090  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180187095  lea     rcx, [rbp+230h+var_170]
0x18018709c  call    ??1?$CMFBaseStringT@D@@QEAA@XZ; CMFBaseStringT<char>::~CMFBaseStringT<char>(void)
0x1801870a1  lea     rcx, [rsp+330h+var_2F8]; this
0x1801870a6  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1801870ab  mov     eax, ebx
0x1801870ad  mov     rcx, [rbp+230h+var_50]
0x1801870b4  xor     rcx, rsp; StackCookie
0x1801870b7  call    __security_check_cookie
0x1801870bc  add     rsp, 2F8h
0x1801870c3  pop     r15
0x1801870c5  pop     r14
0x1801870c7  pop     r13
0x1801870c9  pop     r12
0x1801870cb  pop     rdi
0x1801870cc  pop     rsi
0x1801870cd  pop     rbx
0x1801870ce  pop     rbp
0x1801870cf  retn
0x1801870d1  lea     rcx, [rbp+230h+pguid]; pguid
0x1801870d5  call    cs:__imp_CoCreateGuid
0x1801870dc  nop     dword ptr [rax+rax+00h]
0x1801870e1  mov     ebx, eax
0x1801870e3  test    eax, eax
0x1801870e5  jns     loc_18018719F
0x1801870eb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801870f2  test    rcx, rcx
0x1801870f5  jnz     short loc_18018713F
0x1801870f7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801870fe  nop     dword ptr [rax+rax+00h]
0x180187103  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18018710a  mov     rcx, rax
0x18018710d  test    rax, rax
0x180187110  jz      short loc_180187131
0x180187112  mov     rax, [rax]
0x180187115  mov     edx, 7F0h
0x18018711a  mov     rax, [rax+8]
0x18018711e  call    cs:__guard_dispatch_icall_fptr
0x180187124  test    eax, eax
0x180187126  jz      short loc_180187131
0x180187128  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18018712f  jmp     short loc_18018713F
0x180187131  lea     rcx, qword_1803CE250; this
0x180187138  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18018713f  cmp     [rcx+8], r13b
0x180187143  jz      short loc_18018716A
0x180187145  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18018714a  cmp     [rax+7CCh], ebx
0x180187150  jz      short loc_18018716A
0x180187152  mov     r9d, ebx; int
0x180187155  lea     rdx, aCpmpserverprox; "CPMPServerProxy::Initialize"
0x18018715c  mov     r8d, 7EDh; int
0x180187162  mov     rcx, rax; this
0x180187165  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18018716a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180187171  jb      loc_180187034
0x180187177  mov     edx, 7Fh
0x18018717c  mov     rcx, cs:WPP_GLOBAL_Control
0x180187183  lea     r8, WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids
0x18018718a  mov     r9, rdi
0x18018718d  mov     [rsp+330h+bAlertable], ebx
0x180187191  mov     rcx, [rcx+10h]
0x180187195  call    WPP_SF_qD
0x18018719a  jmp     loc_180187034
0x18018719f  mov     edx, 2Fh ; '/'
0x1801871a4  lea     rcx, [rbp+230h+var_290]
0x1801871a8  call    ?AppendChar@?$CMFBaseStringT@G@@QEAAJG@Z; CMFBaseStringT<ushort>::AppendChar(ushort)
0x1801871ad  mov     edx, 8
0x1801871b2  lea     rcx, [rsp+330h+var_2C0]
0x1801871b7  call    cs:__imp_?MFGetRandomNumber@@YAJPEAXK@Z; MFGetRandomNumber(void *,ulong)
0x1801871be  nop     dword ptr [rax+rax+00h]
0x1801871c3  mov     ebx, eax
0x1801871c5  test    eax, eax
0x1801871c7  jns     loc_180187263
0x1801871cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801871d4  test    rcx, rcx
0x1801871d7  jnz     short loc_180187221
0x1801871d9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801871e0  nop     dword ptr [rax+rax+00h]
0x1801871e5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801871ec  mov     rcx, rax
0x1801871ef  test    rax, rax
0x1801871f2  jz      short loc_180187213
0x1801871f4  mov     rax, [rax]
0x1801871f7  mov     edx, 7F0h
0x1801871fc  mov     rax, [rax+8]
0x180187200  call    cs:__guard_dispatch_icall_fptr
0x180187206  test    eax, eax
0x180187208  jz      short loc_180187213
0x18018720a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180187211  jmp     short loc_180187221
0x180187213  lea     rcx, qword_1803CE250; this
0x18018721a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180187221  cmp     [rcx+8], r13b
0x180187225  jz      short loc_18018724C
0x180187227  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18018722c  cmp     [rax+7CCh], ebx
0x180187232  jz      short loc_18018724C
0x180187234  mov     r9d, ebx; int
0x180187237  lea     rdx, aCpmpserverprox; "CPMPServerProxy::Initialize"
0x18018723e  mov     r8d, 7F2h; int
0x180187244  mov     rcx, rax; this
0x180187247  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18018724c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180187253  jb      loc_180187034
0x180187259  mov     edx, 80h
0x18018725e  jmp     loc_18018717C
0x180187263  mov     rdx, [rsp+330h+var_2C0]
0x180187268  lea     rcx, [rbp+230h+var_290]
0x18018726c  mov     ebx, 10h
0x180187271  mov     r8d, ebx
0x180187274  call    ?AppendUInt64@?$CMFBaseStringT@G@@QEAAJ_KH@Z; CMFBaseStringT<ushort>::AppendUInt64(unsigned __int64,int)
0x180187279  lea     edx, [rbx+4Fh]
0x18018727c  lea     rcx, [rbp+230h+var_290]
0x180187280  call    ?AppendChar@?$CMFBaseStringT@G@@QEAAJG@Z; CMFBaseStringT<ushort>::AppendChar(ushort)
0x180187285  mov     edx, edi
0x180187287  lea     rcx, [rbp+230h+var_290]
0x18018728b  mov     r8d, ebx
0x18018728e  call    ?AppendUInt@?$CMFBaseStringT@G@@QEAAJIH@Z; CMFBaseStringT<ushort>::AppendUInt(uint,int)
0x180187293  lea     rdx, [rsp+330h+ExitCode]; int *
0x180187298  mov     [rsp+330h+ExitCode], 0FFFFFFFFh
0x1801872a0  lea     ecx, [rbx-6]; unsigned __int64
0x1801872a3  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x1801872a8  mov     ebx, 8007006Fh
0x1801872ad  test    eax, eax
0x1801872af  jns     short loc_1801872B6
0x1801872b1  mov     dword ptr [rbp+230h+var_28C], ebx
0x1801872b4  jmp     short loc_1801872CB
0x1801872b6  mov     r8d, [rsp+330h+ExitCode]
0x1801872bb  lea     rdx, aPmpserver; "/PMPServer"
0x1801872c2  lea     rcx, [rbp+230h+var_290]
0x1801872c6  call    ?_Append@?$CMFBaseStringT@G@@IEAAJPEBGJ@Z; CMFBaseStringT<ushort>::_Append(ushort const *,long)
0x1801872cb  cmp     cs:byte_1803CECE9, 8
0x1801872d2  jb      short loc_180187301
0x1801872d4  lea     rcx, [rbp+230h+var_290]
0x1801872d8  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x1801872dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1801872e4  lea     r8, WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids
0x1801872eb  mov     edx, 81h
0x1801872f0  mov     qword ptr [rsp+330h+bAlertable], rax
0x1801872f5  mov     r9, rdi
0x1801872f8  mov     rcx, [rcx+38h]
0x1801872fc  call    WPP_SF_qS
0x180187301  lea     rcx, [rbp+230h+var_290]
0x180187305  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x18018730a  mov     [rsp+330h+ExitCode], 0FFFFFFFFh
0x180187312  mov     r9, rax
0x180187315  test    rax, rax
0x180187318  jz      short loc_180187352
0x18018731a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18018731e  inc     rcx; unsigned __int64
0x180187321  cmp     [rax+rcx*2], r13w
0x180187326  jnz     short loc_18018731E
0x180187328  lea     rdx, [rsp+330h+ExitCode]; int *
0x18018732d  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x180187332  test    eax, eax
0x180187334  jns     short loc_18018733E
0x180187336  mov     dword ptr [rbp+230h+var_16C], ebx
0x18018733c  jmp     short loc_180187352
0x18018733e  mov     r8d, [rsp+330h+ExitCode]
0x180187343  lea     rcx, [rbp+230h+var_170]
0x18018734a  mov     rdx, r9
0x18018734d  call    ?_Append@?$CMFBaseStringT@G@@IEAAJPEBGJ@Z; CMFBaseStringT<ushort>::_Append(ushort const *,long)
0x180187352  lea     rdx, [rsp+330h+ExitCode]; int *
0x180187357  mov     [rsp+330h+ExitCode], 0FFFFFFFFh
0x18018735f  mov     ecx, 6; unsigned __int64
0x180187364  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x180187369  test    eax, eax
0x18018736b  jns     short loc_180187375
0x18018736d  mov     dword ptr [rbp+230h+var_16C], ebx
0x180187373  jmp     short loc_18018738D
0x180187375  mov     r8d, [rsp+330h+ExitCode]
0x18018737a  lea     rdx, aStart_0; "/Start"
0x180187381  lea     rcx, [rbp+230h+var_170]
0x180187388  call    ?_Append@?$CMFBaseStringT@G@@IEAAJPEBGJ@Z; CMFBaseStringT<ushort>::_Append(ushort const *,long)
0x18018738d  lea     rcx, [rbp+230h+var_170]
0x180187394  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x180187399  mov     r9, rax; lpName
0x18018739c  mov     edx, r15d; bManualReset
0x18018739f  xor     ecx, ecx; lpEventAttributes
0x1801873a1  xor     r8d, r8d; bInitialState
0x1801873a4  call    cs:__imp_CreateEventW
0x1801873ab  nop     dword ptr [rax+rax+00h]
0x1801873b0  mov     r15, rax
  ... truncated ...
```
