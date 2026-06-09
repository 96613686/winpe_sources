# ServiceMainImpl(ushort const *,ServiceMainCallback *,ulong,ushort * *)

- ea: `0x180001ea0`
- end: `0x18000273d`
- name: `?ServiceMainImpl@@YAJPEBGPEAUServiceMainCallback@@KPEAPEAG@Z`
- size: `2205`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct ServiceMainCallback *, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002e10`

## callees

- `0x180001ea0`
- `0x180002be4`
- `0x180002d7c`
- `0x1800033d0`
- `0x180006c90`
- `0x180007568`
- `0x18000b280`
- `0x18000b2d4`
- `0x18000cc78`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000227b`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000227b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800020ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800021d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800022bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000232d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800026be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800020ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800021d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800022bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000232d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800026be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000209c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000219f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000228d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000229c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000268c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000209c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000219f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000228d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000229c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000268c`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800024f4`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800024f4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180002228`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180002228`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800025d8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800025d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800020e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800021e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800022a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800026d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800020e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800021e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800022a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800026d1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800022e9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800022e9`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x180002068`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18000216b`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x180002658`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x180002068`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18000216b`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x180002658`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000208d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800020bd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002190`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800021c0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000231c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000267d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800026ad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000208d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800020bd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002190`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800021c0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000231c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000267d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800026ad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000207e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800020af`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002181`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800021b2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000230e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002399`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000266e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000269f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000207e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800020af`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002181`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800021b2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000230e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002399`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000266e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000269f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800020c6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800021c9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002325`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800026b6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800020c6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800021c9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002325`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800026b6`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180001f54`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180001f54`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180001f7a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002026`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002129`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002463`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002536`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002593`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002616`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180001f7a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002026`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002129`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002463`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002536`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002593`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002616`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180001fc3`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180001fc3`
- `api-ms-win-shcore-thread-l1-1-0!SetProcessReference` at `0x18000204c`
- `api-ms-win-shcore-thread-l1-1-0!SetProcessReference` at `0x18000214f`
- `api-ms-win-shcore-thread-l1-1-0!SetProcessReference` at `0x1800022cb`
- `api-ms-win-shcore-thread-l1-1-0!SetProcessReference` at `0x18000263c`
- `api-ms-win-shcore-thread-l1-1-0!SetProcessReference` at `0x18000204c`
- `api-ms-win-shcore-thread-l1-1-0!SetProcessReference` at `0x18000214f`
- `api-ms-win-shcore-thread-l1-1-0!SetProcessReference` at `0x1800022cb`
- `api-ms-win-shcore-thread-l1-1-0!SetProcessReference` at `0x18000263c`

## string_xrefs

- `0x180001f88`: `onecoreuap\enduser\winstore\servicescommon\lib\servicemain.cpp`
- `0x180002034`: `onecoreuap\enduser\winstore\servicescommon\lib\servicemain.cpp`
- `0x180002137`: `onecoreuap\enduser\winstore\servicescommon\lib\servicemain.cpp`
- `0x18000223b`: `onecoreuap\enduser\winstore\servicescommon\lib\servicemain.cpp`
- `0x180002340`: `onecoreuap\enduser\winstore\servicescommon\lib\servicemain.cpp`
- `0x18000236b`: `onecoreuap\enduser\winstore\servicescommon\lib\servicemain.cpp`
- `0x1800023ad`: `onecoreuap\enduser\winstore\servicescommon\lib\servicemain.cpp`
- `0x1800023e4`: `onecoreuap\enduser\winstore\servicescommon\lib\servicemain.cpp`
- `0x180002416`: `onecoreuap\enduser\winstore\servicescommon\lib\servicemain.cpp`
- `0x180002471`: `onecoreuap\enduser\winstore\servicescommon\lib\servicemain.cpp`
- `0x180002494`: `onecoreuap\enduser\winstore\servicescommon\lib\servicemain.cpp`
- `0x180002505`: `onecoreuap\enduser\winstore\servicescommon\lib\servicemain.cpp`
- `0x180002544`: `onecoreuap\enduser\winstore\servicescommon\lib\servicemain.cpp`
- `0x1800025a1`: `onecoreuap\enduser\winstore\servicescommon\lib\servicemain.cpp`
- `0x180002624`: `onecoreuap\enduser\winstore\servicescommon\lib\servicemain.cpp`
- `0x180001ff5`: `onecoreuap\enduser\winstore\servicescommon\lib\commonsettings.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ServiceMainImpl(
        const unsigned __int16 *a1,
        struct ServiceMainCallback *a2,
        __int64 a3,
        unsigned __int16 **a4)
{
  char v5; // al
  const char *v6; // r9
  const unsigned __int16 *v7; // rcx
  signed int LastError; // eax
  signed int v9; // edi
  const char *v10; // r9
  struct _TP_TIMER *v11; // rsi
  DWORD v12; // ebx
  unsigned int v13; // r8d
  const char *v14; // r9
  const char *v15; // r9
  struct _TP_TIMER *v16; // rdi
  DWORD v17; // ebx
  unsigned int v18; // r8d
  const char *v19; // r9
  wil::details *v21; // rcx
  HANDLE Event; // rdi
  HANDLE v23; // rbx
  DWORD v24; // r14d
  unsigned int v25; // r8d
  const char *v26; // r9
  struct _TP_TIMER *v27; // rdi
  const char *v28; // r9
  struct _TP_TIMER *v29; // r14
  DWORD v30; // ebx
  int LastErrorFailHr; // eax
  int v32; // eax
  int v33; // eax
  const char *v34; // r9
  __int32 v35; // eax
  HRESULT v36; // eax
  const char *v37; // r9
  const char *v38; // r9
  const char *v39; // r9
  struct _TP_TIMER *v40; // rsi
  DWORD v41; // ebx
  unsigned int v42; // r8d
  const char *v43; // r9
  int lpdwindex; // [rsp+20h] [rbp-59h]
  int lpdwindexa; // [rsp+20h] [rbp-59h]
  _FILETIME pftDueTime; // [rsp+30h] [rbp-49h] BYREF
  HANDLE pHandles; // [rsp+38h] [rbp-41h] BYREF
  void **Context; // [rsp+40h] [rbp-39h] BYREF
  __int64 v49; // [rsp+48h] [rbp-31h] BYREF
  int v50; // [rsp+50h] [rbp-29h]
  char v51; // [rsp+54h] [rbp-25h]
  unsigned __int8 v52; // [rsp+55h] [rbp-24h]
  HANDLE hObject; // [rsp+58h] [rbp-21h]
  PTP_TIMER pti; // [rsp+60h] [rbp-19h]
  _SERVICE_STATUS ServiceStatus; // [rsp+68h] [rbp-11h] BYREF
  SERVICE_STATUS_HANDLE hServiceStatus; // [rsp+88h] [rbp+Fh]
  struct ServiceMainCallback *v57; // [rsp+90h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v5 = (*(__int64 (__fastcall **)(struct ServiceMainCallback *))(*(_QWORD *)a2 + 8LL))(a2);
  Context = &ProcessRefCount::`vftable';
  v49 = 0;
  v50 = 0;
  v51 = v5;
  v52 = 0;
  hObject = 0;
  pti = 0;
  hServiceStatus = 0;
  v57 = a2;
  ServiceStatus.dwServiceType = 32;
  ServiceStatus.dwCurrentState = 2;
  ServiceStatus.dwControlsAccepted = 1;
  if ( (*(unsigned __int8 (__fastcall **)(struct ServiceMainCallback *))(*(_QWORD *)a2 + 16LL))(a2) )
    ServiceStatus.dwControlsAccepted |= 0x1000u;
  *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
  hServiceStatus = RegisterServiceCtrlHandlerExW(L"LicenseManager", ServiceControlHandler, &Context);
  ServiceStatus.dwCurrentState = 2;
  *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  ++ServiceStatus.dwCheckPoint;
  ServiceStatus.dwWaitHint = 1000;
  if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
    wil::details::in1diag3::Return_GetLastError(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
      v6);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy>::GetImpl'::`2'::impl) )
  {
    pftDueTime.dwLowDateTime = 1;
    if ( !(unsigned int)SetProcessMitigationPolicy(16, &pftDueTime, 4) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      v7 = (const unsigned __int16 *)retaddr;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x46,
          (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\commonsettings.cpp",
          (const char *)(unsigned int)v9,
          lpdwindex);
        ServiceStatus.dwCurrentState = 1;
        ServiceStatus.dwServiceSpecificExitCode = v9;
        ServiceStatus.dwWin32ExitCode = 1066;
        ++ServiceStatus.dwCheckPoint;
        ServiceStatus.dwWaitHint = 0;
        if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
          wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0xC7,
            (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
            v10);
        Context = &ProcessRefCount::`vftable';
        SetProcessReference(0);
        if ( pti )
        {
          _InterlockedExchange((volatile __int32 *)&v49, 0);
          if ( pti && IsThreadpoolTimerSet(pti) )
          {
            SetThreadpoolTimer(pti, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(pti, 1);
          }
          v11 = pti;
          if ( pti )
          {
            v12 = GetLastError();
            SetThreadpoolTimer(v11, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(v11, 1);
            CloseThreadpoolTimer(v11);
            SetLastError(v12);
          }
          pti = 0;
        }
        if ( hObject )
        {
          if ( !CloseHandle(hObject) )
            wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
        }
        return (unsigned int)v9;
      }
    }
  }
  if ( ShouldStoreComponentBeEnabled(v7) )
  {
    v9 = 0;
    (**(void (__fastcall ***)(struct ServiceMainCallback *, SERVICE_STATUS_HANDLE))a2)(a2, hServiceStatus);
    if ( (*(unsigned __int8 (__fastcall **)(struct ServiceMainCallback *))(*(_QWORD *)a2 + 24LL))(a2) )
      v9 = CoInitializeEx(0, 0);
    if ( v9 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x11E,
        (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
        (const char *)(unsigned int)v9,
        lpdwindex);
      (**(void (__fastcall ***)(struct ServiceMainCallback *, _QWORD))a2)(a2, 0);
      ServiceStatus.dwCurrentState = 1;
      ServiceStatus.dwServiceSpecificExitCode = v9;
LABEL_80:
      ServiceStatus.dwWin32ExitCode = 1066;
LABEL_81:
      ++ServiceStatus.dwCheckPoint;
      ServiceStatus.dwWaitHint = 0;
      if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
        wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0xC7,
          (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
          v39);
      Context = &ProcessRefCount::`vftable';
      SetProcessReference(0);
      if ( pti )
      {
        _InterlockedExchange((volatile __int32 *)&v49, 0);
        if ( pti && IsThreadpoolTimerSet(pti) )
        {
          SetThreadpoolTimer(pti, 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(pti, 1);
        }
        v40 = pti;
        if ( pti )
        {
          v41 = GetLastError();
          SetThreadpoolTimer(v40, 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(v40, 1);
          CloseThreadpoolTimer(v40);
          SetLastError(v41);
        }
        pti = 0;
      }
      if ( hObject && !CloseHandle(hObject) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
      return (unsigned int)v9;
    }
    Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
    if ( Event )
    {
      GetLastError();
      v23 = hObject;
      if ( hObject )
      {
        v24 = GetLastError();
        if ( !CloseHandle(v23) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
        SetLastError(v24);
      }
      hObject = Event;
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v21);
      v9 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x25,
          (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
          (const char *)(unsigned int)LastErrorFailHr,
          lpdwindex);
        goto LABEL_53;
      }
    }
    SetProcessReference(&Context);
    if ( v51 )
    {
      v27 = CreateThreadpoolTimer(ProcessRefCount::s_TimerCallback, &Context, 0);
      v29 = pti;
      if ( pti )
      {
        v30 = GetLastError();
        SetThreadpoolTimer(v29, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v29, 1);
        CloseThreadpoolTimer(v29);
        SetLastError(v30);
      }
      pti = v27;
      if ( !v27 )
      {
        v9 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x2C,
               (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
               v28);
        goto LABEL_53;
      }
      pftDueTime = (_FILETIME)-6000000000LL;
      SetThreadpoolTimer(v27, &pftDueTime, 0, 0);
    }
    v9 = 0;
LABEL_53:
    if ( v9 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x121,
        (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
        (const char *)(unsigned int)v9,
        lpdwindex);
      goto LABEL_77;
    }
    v32 = (*(__int64 (__fastcall **)(struct ServiceMainCallback *, _QWORD, _QWORD))(*(_QWORD *)a2 + 32LL))(a2, 0, 0);
    v9 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x124,
        (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
        (const char *)(unsigned int)v32,
        lpdwindex);
LABEL_76:
      (*(void (__fastcall **)(struct ServiceMainCallback *, _QWORD))(*(_QWORD *)a2 + 40LL))(a2, v52);
LABEL_77:
      if ( (*(unsigned __int8 (__fastcall **)(struct ServiceMainCallback *))(*(_QWORD *)a2 + 24LL))(a2) )
        CoUninitialize();
      (**(void (__fastcall ***)(struct ServiceMainCallback *, _QWORD))a2)(a2, 0);
      ServiceStatus.dwCurrentState = 1;
      ServiceStatus.dwServiceSpecificExitCode = v9;
      ServiceStatus.dwWin32ExitCode = 0;
      if ( v9 >= 0 )
        goto LABEL_81;
      goto LABEL_80;
    }
    v33 = (*(__int64 (__fastcall **)(struct ServiceMainCallback *))(*(_QWORD *)a2 + 48LL))(a2);
    v9 = v33;
    if ( v33 >= 0 )
    {
      ServiceStatus.dwCurrentState = 4;
      *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
      ++ServiceStatus.dwCheckPoint;
      ServiceStatus.dwWaitHint = 0;
      if ( SetServiceStatus(hServiceStatus, &ServiceStatus) )
        v9 = 0;
      else
        v9 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0xC7,
               (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
               v34);
      if ( v9 >= 0 )
      {
        if ( Microsoft::WRL::Details::ModuleBase::module_ )
          v35 = (*(__int64 (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                        + 24LL))(Microsoft::WRL::Details::ModuleBase::module_);
        else
          v35 = 0;
        _InterlockedExchange((volatile __int32 *)&v49 + 1, v35);
        pftDueTime.dwLowDateTime = 0;
        pHandles = hObject;
        v36 = CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, &pHandles, (LPDWORD)&pftDueTime);
        if ( v36 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x62,
            (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
            (const char *)(unsigned int)v36,
            lpdwindexa);
        ServiceStatus.dwWin32ExitCode = 0;
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x12B,
          (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
          (const char *)(unsigned int)v9,
          lpdwindex);
        ServiceStatus.dwWin32ExitCode = 1066;
      }
      ServiceStatus.dwCurrentState = 3;
      ServiceStatus.dwServiceSpecificExitCode = v9;
      ++ServiceStatus.dwCheckPoint;
      ServiceStatus.dwWaitHint = 1500;
      if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
        wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0xC7,
          (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
          v37);
      (*(void (__fastcall **)(struct ServiceMainCallback *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, v52);
      ServiceStatus.dwCurrentState = 3;
      ServiceStatus.dwServiceSpecificExitCode = v9;
      ServiceStatus.dwWin32ExitCode = 0;
      if ( v9 >= 0 )
        goto LABEL_74;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x127,
        (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
        (const char *)(unsigned int)v33,
        lpdwindex);
      (*(void (__fastcall **)(struct ServiceMainCallback *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, v52);
      ServiceStatus.dwCurrentState = 3;
      ServiceStatus.dwServiceSpecificExitCode = v9;
    }
    ServiceStatus.dwWin32ExitCode = 1066;
LABEL_74:
    ++ServiceStatus.dwCheckPoint;
    ServiceStatus.dwWaitHint = 1100;
    if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
      wil::details::in1diag3::Return_GetLastError(
        retaddr,
        (void *)0xC7,
        (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
        v38);
    goto LABEL_76;
  }
  ServiceStatus.dwCurrentState = 1;
  ServiceStatus.dwServiceSpecificExitCode = -2147467259;
  ServiceStatus.dwWin32ExitCode = 1066;
  ++ServiceStatus.dwCheckPoint;
  ServiceStatus.dwWaitHint = 0;
  if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
    wil::details::in1diag3::Return_GetLastError(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
      v15);
  Context = &ProcessRefCount::`vftable';
  SetProcessReference(0);
  if ( pti )
  {
    _InterlockedExchange((volatile __int32 *)&v49, 0);
    if ( pti && IsThreadpoolTimerSet(pti) )
    {
      SetThreadpoolTimer(pti, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(pti, 1);
    }
    v16 = pti;
    if ( pti )
    {
      v17 = GetLastError();
      SetThreadpoolTimer(v16, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v16, 1);
      CloseThreadpoolTimer(v16);
      SetLastError(v17);
    }
    pti = 0;
  }
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180001ea0  mov     [rsp-8+arg_0], rbx
0x180001ea5  mov     [rsp-8+arg_10], rsi
0x180001eaa  push    rbp
0x180001eab  push    rdi
0x180001eac  push    r12
0x180001eae  push    r14
0x180001eb0  push    r15
0x180001eb2  lea     rbp, [rsp-37h]
0x180001eb7  sub     rsp, 0B0h
0x180001ebe  mov     rax, cs:__security_cookie
0x180001ec5  xor     rax, rsp
0x180001ec8  mov     [rbp+57h+var_30], rax
0x180001ecc  mov     rsi, rdx
0x180001ecf  mov     rax, [rdx]
0x180001ed2  mov     rcx, rdx
0x180001ed5  mov     rax, [rax+8]
0x180001ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ede  lea     r12, ??_7ProcessRefCount@@6B@; const ProcessRefCount::`vftable'
0x180001ee5  mov     [rbp+57h+Context], r12
0x180001ee9  xor     r15d, r15d
0x180001eec  mov     [rbp+57h+var_88], r15
0x180001ef0  mov     [rbp+57h+var_80], r15d
0x180001ef4  mov     [rbp+57h+var_7C], al
0x180001ef7  mov     [rbp+57h+var_7B], r15b
0x180001efb  mov     [rbp+57h+hObject], r15
0x180001eff  mov     [rbp+57h+pti], r15
0x180001f03  mov     [rbp+57h+hServiceStatus], r15
0x180001f07  mov     [rbp+57h+var_40], rsi
0x180001f0b  mov     [rbp+57h+ServiceStatus.dwServiceType], 20h ; ' '
0x180001f12  mov     [rbp+57h+ServiceStatus.dwCurrentState], 2
0x180001f19  mov     [rbp+57h+ServiceStatus.dwControlsAccepted], 1
0x180001f20  mov     rax, [rsi]
0x180001f23  mov     rcx, rsi
0x180001f26  mov     rax, [rax+10h]
0x180001f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f2f  test    al, al
0x180001f31  jz      short loc_180001F3A
0x180001f33  or      [rbp+57h+ServiceStatus.dwControlsAccepted], 1000h
0x180001f3a  mov     qword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], r15
0x180001f3e  mov     qword ptr [rbp+57h+ServiceStatus.dwCheckPoint], r15
0x180001f42  lea     r8, [rbp+57h+Context]; lpContext
0x180001f46  lea     rdx, ?ServiceControlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x180001f4d  lea     rcx, ServiceName; "LicenseManager"
0x180001f54  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180001f5a  mov     [rbp+57h+hServiceStatus], rax
0x180001f5e  mov     [rbp+57h+ServiceStatus.dwCurrentState], 2
0x180001f65  mov     qword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], r15
0x180001f69  inc     [rbp+57h+ServiceStatus.dwCheckPoint]
0x180001f6c  mov     [rbp+57h+ServiceStatus.dwWaitHint], 3E8h
0x180001f73  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180001f77  mov     rcx, rax; hServiceStatus
0x180001f7a  call    cs:__imp_SetServiceStatus
0x180001f80  test    eax, eax
0x180001f82  jnz     short loc_180001F99
0x180001f84  mov     rcx, [rbp+5Fh]; this
0x180001f88  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\services"...
0x180001f8f  mov     edx, 0C7h; void *
0x180001f94  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180001f99  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy> `wil::Feature<__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy>::GetImpl(void)'::`2'::impl
0x180001fa0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy>::__private_IsEnabled(void)
0x180001fa5  test    al, al
0x180001fa7  jz      loc_1800020F8
0x180001fad  mov     [rbp+57h+pftDueTime.dwLowDateTime], 1
0x180001fb4  mov     r8d, 4
0x180001fba  lea     rdx, [rbp+57h+pftDueTime]
0x180001fbe  mov     ecx, 10h
0x180001fc3  call    cs:__imp_SetProcessMitigationPolicy
0x180001fc9  test    eax, eax
0x180001fcb  jnz     loc_1800020F8
0x180001fd1  call    cs:__imp_GetLastError
0x180001fd7  mov     edi, eax
0x180001fd9  test    eax, eax
0x180001fdb  jle     short loc_180001FE6
0x180001fdd  movzx   edi, ax
0x180001fe0  or      edi, 80070000h
0x180001fe6  mov     rcx, [rbp+5Fh]; this
0x180001fea  test    edi, edi
0x180001fec  jns     loc_1800020F8
0x180001ff2  mov     r9d, edi; char *
0x180001ff5  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\services"...
0x180001ffc  mov     edx, 46h ; 'F'; void *
0x180002001  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180002006  mov     [rbp+57h+ServiceStatus.dwCurrentState], 1
0x18000200d  mov     [rbp+57h+ServiceStatus.dwServiceSpecificExitCode], edi
0x180002010  mov     [rbp+57h+ServiceStatus.dwWin32ExitCode], 42Ah
0x180002017  inc     [rbp+57h+ServiceStatus.dwCheckPoint]
0x18000201a  mov     [rbp+57h+ServiceStatus.dwWaitHint], r15d
0x18000201e  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180002022  mov     rcx, [rbp+57h+hServiceStatus]; hServiceStatus
0x180002026  call    cs:__imp_SetServiceStatus
0x18000202c  test    eax, eax
0x18000202e  jnz     short loc_180002046
0x180002030  mov     rcx, [rbp+5Fh]; this
0x180002034  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\services"...
0x18000203b  mov     edx, 0C7h; void *
0x180002040  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180002045  nop
0x180002046  mov     [rbp+57h+Context], r12
0x18000204a  xor     ecx, ecx
0x18000204c  call    cs:__imp_SetProcessReference
0x180002052  cmp     [rbp+57h+pti], 0
0x180002057  jz      short loc_1800020D8
0x180002059  mov     eax, r15d
0x18000205c  xchg    eax, dword ptr [rbp+57h+var_88]
0x18000205f  mov     rcx, [rbp+57h+pti]; pti
0x180002063  test    rcx, rcx
0x180002066  jz      short loc_180002093
0x180002068  call    cs:__imp_IsThreadpoolTimerSet
0x18000206e  test    eax, eax
0x180002070  jz      short loc_180002093
0x180002072  xor     r9d, r9d; msWindowLength
0x180002075  xor     r8d, r8d; msPeriod
0x180002078  xor     edx, edx; pftDueTime
0x18000207a  mov     rcx, [rbp+57h+pti]; pti
0x18000207e  call    cs:__imp_SetThreadpoolTimer
0x180002084  mov     edx, 1; fCancelPendingCallbacks
0x180002089  mov     rcx, [rbp+57h+pti]; pti
0x18000208d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180002093  mov     rsi, [rbp+57h+pti]
0x180002097  test    rsi, rsi
0x18000209a  jz      short loc_1800020D4
0x18000209c  call    cs:__imp_GetLastError
0x1800020a2  mov     ebx, eax
0x1800020a4  xor     r9d, r9d; msWindowLength
0x1800020a7  xor     r8d, r8d; msPeriod
0x1800020aa  xor     edx, edx; pftDueTime
0x1800020ac  mov     rcx, rsi; pti
0x1800020af  call    cs:__imp_SetThreadpoolTimer
0x1800020b5  mov     edx, 1; fCancelPendingCallbacks
0x1800020ba  mov     rcx, rsi; pti
0x1800020bd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800020c3  mov     rcx, rsi; pti
0x1800020c6  call    cs:__imp_CloseThreadpoolTimer
0x1800020cc  mov     ecx, ebx; dwErrCode
0x1800020ce  call    cs:__imp_SetLastError
0x1800020d4  mov     [rbp+57h+pti], r15
0x1800020d8  mov     rcx, [rbp+57h+hObject]; hObject
0x1800020dc  test    rcx, rcx
0x1800020df  jz      loc_1800026DB
0x1800020e5  call    cs:__imp_CloseHandle
0x1800020eb  test    eax, eax
0x1800020ed  jz      loc_180002714
0x1800020f3  jmp     loc_1800026DB
0x1800020f8  call    ?ShouldStoreComponentBeEnabled@@YA_NPEBG@Z; ShouldStoreComponentBeEnabled(ushort const *)
0x1800020fd  test    al, al
0x1800020ff  jnz     loc_1800021FC
0x180002105  mov     [rbp+57h+ServiceStatus.dwCurrentState], 1
0x18000210c  mov     [rbp+57h+ServiceStatus.dwServiceSpecificExitCode], 80004005h
0x180002113  mov     [rbp+57h+ServiceStatus.dwWin32ExitCode], 42Ah
0x18000211a  inc     [rbp+57h+ServiceStatus.dwCheckPoint]
0x18000211d  mov     [rbp+57h+ServiceStatus.dwWaitHint], r15d
0x180002121  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180002125  mov     rcx, [rbp+57h+hServiceStatus]; hServiceStatus
0x180002129  call    cs:__imp_SetServiceStatus
0x18000212f  test    eax, eax
0x180002131  jnz     short loc_180002149
0x180002133  mov     rcx, [rbp+5Fh]; this
0x180002137  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\services"...
0x18000213e  mov     edx, 0C7h; void *
0x180002143  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180002148  nop
0x180002149  mov     [rbp+57h+Context], r12
0x18000214d  xor     ecx, ecx
0x18000214f  call    cs:__imp_SetProcessReference
0x180002155  cmp     [rbp+57h+pti], 0
0x18000215a  jz      short loc_1800021DB
0x18000215c  mov     eax, r15d
0x18000215f  xchg    eax, dword ptr [rbp+57h+var_88]
0x180002162  mov     rcx, [rbp+57h+pti]; pti
0x180002166  test    rcx, rcx
0x180002169  jz      short loc_180002196
0x18000216b  call    cs:__imp_IsThreadpoolTimerSet
0x180002171  test    eax, eax
0x180002173  jz      short loc_180002196
0x180002175  xor     r9d, r9d; msWindowLength
0x180002178  xor     r8d, r8d; msPeriod
0x18000217b  xor     edx, edx; pftDueTime
0x18000217d  mov     rcx, [rbp+57h+pti]; pti
0x180002181  call    cs:__imp_SetThreadpoolTimer
0x180002187  mov     edx, 1; fCancelPendingCallbacks
0x18000218c  mov     rcx, [rbp+57h+pti]; pti
0x180002190  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180002196  mov     rdi, [rbp+57h+pti]
0x18000219a  test    rdi, rdi
0x18000219d  jz      short loc_1800021D7
0x18000219f  call    cs:__imp_GetLastError
0x1800021a5  mov     ebx, eax
0x1800021a7  xor     r9d, r9d; msWindowLength
0x1800021aa  xor     r8d, r8d; msPeriod
0x1800021ad  xor     edx, edx; pftDueTime
0x1800021af  mov     rcx, rdi; pti
0x1800021b2  call    cs:__imp_SetThreadpoolTimer
0x1800021b8  mov     edx, 1; fCancelPendingCallbacks
0x1800021bd  mov     rcx, rdi; pti
0x1800021c0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800021c6  mov     rcx, rdi; pti
0x1800021c9  call    cs:__imp_CloseThreadpoolTimer
0x1800021cf  mov     ecx, ebx; dwErrCode
0x1800021d1  call    cs:__imp_SetLastError
0x1800021d7  mov     [rbp+57h+pti], r15
0x1800021db  mov     rcx, [rbp+57h+hObject]; hObject
0x1800021df  test    rcx, rcx
0x1800021e2  jz      short loc_1800021F2
0x1800021e4  call    cs:__imp_CloseHandle
0x1800021ea  test    eax, eax
0x1800021ec  jz      loc_180002723
0x1800021f2  mov     eax, 80004005h
0x1800021f7  jmp     loc_1800026DD
0x1800021fc  mov     edi, r15d
0x1800021ff  mov     rax, [rsi]
0x180002202  mov     rdx, [rbp+57h+hServiceStatus]
0x180002206  mov     rcx, rsi
0x180002209  mov     rax, [rax]
0x18000220c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002211  mov     rax, [rsi]
0x180002214  mov     rcx, rsi
0x180002217  mov     rax, [rax+18h]
0x18000221b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002220  test    al, al
0x180002222  jz      short loc_180002230
0x180002224  xor     edx, edx; dwCoInit
0x180002226  xor     ecx, ecx; pvReserved
0x180002228  call    cs:__imp_CoInitializeEx
0x18000222e  mov     edi, eax
0x180002230  mov     rcx, [rbp+5Fh]; this
0x180002234  test    edi, edi
0x180002236  jns     short loc_18000226B
0x180002238  mov     r9d, edi; char *
0x18000223b  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\services"...
0x180002242  mov     edx, 11Eh; void *
0x180002247  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000224c  mov     rdx, [rsi]
0x18000224f  mov     rax, [rdx]
0x180002252  xor     edx, edx
0x180002254  mov     rcx, rsi
0x180002257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000225c  mov     [rbp+57h+ServiceStatus.dwCurrentState], 1
0x180002263  mov     [rbp+57h+ServiceStatus.dwServiceSpecificExitCode], edi
0x180002266  jmp     loc_180002600
0x18000226b  xor     edx, edx; lpName
0x18000226d  xor     ecx, ecx; lpEventAttributes
0x18000226f  mov     r9d, 1F0003h; dwDesiredAccess
0x180002275  mov     r8d, 1; dwFlags
0x18000227b  call    cs:__imp_CreateEventExW
0x180002281  mov     rdi, rax
0x180002284  test    rax, rax
0x180002287  jz      loc_180002355
0x18000228d  call    cs:__imp_GetLastError
0x180002293  mov     rbx, [rbp+57h+hObject]
0x180002297  test    rbx, rbx
0x18000229a  jz      short loc_1800022C3
0x18000229c  call    cs:__imp_GetLastError
0x1800022a2  mov     r14d, eax
0x1800022a5  mov     rcx, rbx; hObject
0x1800022a8  call    cs:__imp_CloseHandle
0x1800022ae  mov     rcx, [rbp+5Fh]; this
0x1800022b2  test    eax, eax
0x1800022b4  jz      loc_180002732
0x1800022ba  mov     ecx, r14d; dwErrCode
0x1800022bd  call    cs:__imp_SetLastError
0x1800022c3  mov     [rbp+57h+hObject], rdi
0x1800022c7  lea     rcx, [rbp+57h+Context]
0x1800022cb  call    cs:__imp_SetProcessReference
0x1800022d1  cmp     [rbp+57h+var_7C], 0
0x1800022d5  jz      loc_18000239F
0x1800022db  xor     r8d, r8d; pcbe
0x1800022de  lea     rdx, [rbp+57h+Context]; pv
0x1800022e2  lea     rcx, ?s_TimerCallback@ProcessRefCount@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800022e9  call    cs:__imp_CreateThreadpoolTimer
0x1800022ef  mov     rdi, rax
0x1800022f2  mov     r14, [rbp+57h+pti]
0x1800022f6  test    r14, r14
0x1800022f9  jz      short loc_180002333
0x1800022fb  call    cs:__imp_GetLastError
0x180002301  mov     ebx, eax
0x180002303  xor     r9d, r9d; msWindowLength
0x180002306  xor     r8d, r8d; msPeriod
0x180002309  xor     edx, edx; pftDueTime
0x18000230b  mov     rcx, r14; pti
0x18000230e  call    cs:__imp_SetThreadpoolTimer
0x180002314  mov     edx, 1; fCancelPendingCallbacks
0x180002319  mov     rcx, r14; pti
0x18000231c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180002322  mov     rcx, r14; pti
0x180002325  call    cs:__imp_CloseThreadpoolTimer
0x18000232b  mov     ecx, ebx; dwErrCode
0x18000232d  call    cs:__imp_SetLastError
0x180002333  mov     [rbp+57h+pti], rdi
0x180002337  test    rdi, rdi
0x18000233a  jnz     short loc_18000237E
0x18000233c  mov     rcx, [rbp+5Fh]; this
0x180002340  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\services"...
0x180002347  mov     edx, 2Ch ; ','; void *
0x18000234c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180002351  mov     edi, eax
0x180002353  jmp     short loc_1800023A2
0x180002355  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000235a  mov     edi, eax
0x18000235c  test    eax, eax
0x18000235e  jns     loc_1800022C7
  ... truncated ...
```
