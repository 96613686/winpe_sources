# CCbsExecutionObject::ExecuteInternal(long &,AutoScz &,int &,__int64 &,int &,int &,int &,CbsPackageFailureSource &,int &,ulong &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x18016f73c`
- end: `0x1801707f2`
- name: `?ExecuteInternal@CCbsExecutionObject@@AEAAJAEAJAEAVAutoScz@@AEAHAEA_J222AEAW4CbsPackageFailureSource@@2AEAKAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `4278`
- prototype: `__int64 __usercall@<rax>(struct CCbsExecutionObject *@<rcx>, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `53`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18016ee90`

## callees

- `0x180001808`
- `0x180003e44`
- `0x18000d910`
- `0x180023750`
- `0x180028e24`
- `0x180042130`
- `0x18004be14`
- `0x180051dd4`
- `0x18005b180`
- `0x180065f88`
- `0x180069d10`
- `0x180093a70`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a2404`
- `0x1800a8678`
- `0x1800ad504`
- `0x1800ae508`
- `0x1800b8e68`
- `0x1800b980c`
- `0x1800be684`
- `0x1800c23c0`
- `0x1800e4788`
- `0x1800eb920`
- `0x1800f1eb4`
- `0x1800f60c4`
- `0x1800f618c`
- `0x1800f8580`
- `0x1800fdf20`
- `0x180107778`
- `0x18010f324`
- `0x18012231c`
- `0x18012b7e8`
- `0x18012d1d4`
- `0x180143f5c`
- `0x18015918c`
- `0x18015e85c`
- `0x18016e1f0`
- `0x18016f73c`
- `0x180170d38`
- `0x180171fb0`
- `0x180172330`
- `0x1801733f4`
- `0x180174530`
- `0x18017ff2c`
- `0x180180368`
- `0x1801d2788`
- `0x1801d74e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18016f8a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18016f8f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18016f8a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18016f8f5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18016f8bb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18016f8bb`
- `ntdll!NtSetInformationThread` at `0x18016f912`
- `ntdll!NtSetInformationThread` at `0x18016f912`

## string_xrefs

- `0x18016fa14`: `Unserviceable`
- `0x18016f8e4`: `Exec: Build Update detected, lowering IO priority.`
- `0x18016f898`: `Exec: Build Update detected, lowering thread priority.`
- `0x18016f8c7`: `Unable to set thread priority to low`
- `0x180170767`: `Failed to commit package states.`
- `0x18016ff0d`: `Failed to convert client tasks to execution tasks`
- `0x180170232`: `Failed to load execution tasks.`
- `0x180170309`: `Failed to persist execution tasks.`
- `0x1801704d7`: `Exec: Scheduled TrustedInstaller for auto-start because session was delayed.`

## pseudocode

```c
__int64 __fastcall CCbsExecutionObject::ExecuteInternal(
        struct CCbsExecutionObject *a1,
        int *a2,
        wchar_t **a3,
        int *a4,
        __int64 *a5,
        __int64 a6,
        struct PerSessionPackageState **a7,
        _DWORD *a8,
        enum CbsPackageFailureSource *a9,
        int *a10,
        _DWORD *a11,
        __int64 a12)
{
  __int64 v15; // rax
  __int64 v16; // rcx
  wchar_t **v17; // r14
  struct CCbsPackage *v18; // rdx
  CCbsSession *v19; // rcx
  int SessionPackageState; // eax
  const wchar_t *v21; // rdx
  __int64 v22; // rcx
  struct CCbsSession *v23; // rcx
  int Property; // eax
  char v25; // bl
  HANDLE CurrentThread; // rax
  unsigned int v27; // eax
  HANDLE v28; // rax
  unsigned int v29; // eax
  int v30; // eax
  int v31; // edx
  unsigned int v32; // ebx
  __int64 v33; // rdx
  __int64 v35; // rax
  unsigned int v36; // eax
  struct CCbsSession *v37; // rcx
  __int64 v38; // rcx
  int v39; // r8d
  __int64 v40; // rdx
  const wchar_t *v41; // rcx
  const wchar_t *v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rax
  const wchar_t *v46; // rcx
  bool v47; // zf
  int NextCounter; // eax
  struct CCbsSession *v49; // rcx
  int SessionGlobalExclusivity; // eax
  int v51; // r8d
  int v52; // r9d
  __int64 v53; // rcx
  int IsPendingRequired; // eax
  CCbsSession *v55; // rcx
  int v56; // edx
  unsigned int v57; // eax
  __int64 v58; // rcx
  enum CbsPackageFailureSource *v59; // r15
  _DWORD *v60; // rbx
  int v61; // r14d
  int v62; // eax
  struct CCbsSession *v63; // rcx
  int v64; // eax
  int v65; // eax
  unsigned __int64 *v66; // rsi
  int v67; // eax
  wchar_t **v68; // r15
  int v69; // ebx
  struct CCbsSession *v70; // rdx
  CCbsPackage *v71; // rcx
  int TargetState; // eax
  __int64 v73; // rcx
  signed int v74; // ebx
  wchar_t **v75; // rax
  __int64 v76; // rcx
  int v77; // edx
  __int64 v78; // rax
  int SessionAttributeValue; // eax
  __int64 v80; // r8
  int ExecutionTasks; // eax
  unsigned int v82; // esi
  __int64 v83; // rdx
  __int64 v84; // rdx
  unsigned __int64 v85; // r8
  int v86; // eax
  int v87; // eax
  int v88; // eax
  int v89; // eax
  unsigned int v90; // eax
  __int64 v91; // rcx
  int v92; // eax
  int v93; // eax
  int v94; // eax
  int v95; // eax
  int v96; // eax
  unsigned int v97; // eax
  int v98; // [rsp+20h] [rbp-A1h]
  int v99[2]; // [rsp+40h] [rbp-81h] BYREF
  unsigned int v100[2]; // [rsp+48h] [rbp-79h] BYREF
  struct PerSessionPackageState **v101; // [rsp+50h] [rbp-71h] BYREF
  enum CbsPackageFailureSource *p_ThreadInformation; // [rsp+58h] [rbp-69h] BYREF
  wchar_t **v103; // [rsp+60h] [rbp-61h] BYREF
  __int64 v104; // [rsp+68h] [rbp-59h] BYREF
  _QWORD v105[2]; // [rsp+70h] [rbp-51h] BYREF
  __int128 v106; // [rsp+80h] [rbp-41h] BYREF
  _DWORD *v107; // [rsp+90h] [rbp-31h] BYREF
  const wchar_t *v108; // [rsp+98h] [rbp-29h] BYREF
  __int64 *v109; // [rsp+A0h] [rbp-21h]
  struct PerSessionPackageState *ThreadInformation; // [rsp+A8h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+47h]

  v109 = a5;
  *(_QWORD *)v99 = a6;
  v101 = a7;
  v107 = a8;
  p_ThreadInformation = a9;
  v15 = *((_QWORD *)a1 + 8);
  v103 = a3;
  *(_DWORD *)(v15 + 760) = 1;
  v17 = (wchar_t **)&qword_1802EB518;
  if ( !(unsigned int)CCbsSession::IsOffline(*((CCbsSession **)a1 + 8))
    && (unsigned __int8)StringsAreEqual(*(_QWORD *)(v16 + 648), L"Setup Platform", 0) )
  {
    v18 = (struct CCbsPackage *)*((_QWORD *)a1 + 9);
    v19 = (CCbsSession *)*((_QWORD *)a1 + 8);
    ThreadInformation = 0;
    SessionPackageState = CCbsSession::GetSessionPackageState(v19, v18, &ThreadInformation, 0);
    *a2 = SessionPackageState;
    v21 = &qword_1802EB518;
    v22 = *((_QWORD *)a1 + 9);
    if ( *(_QWORD *)(v22 + 120) )
      v21 = *(const wchar_t **)(v22 + 120);
    *(_QWORD *)v100 = v21;
    if ( SessionPackageState < 0 )
      LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
        1,
        (unsigned int)SessionPackageState,
        "Unable to get session package state for package: {}",
        v100);
    if ( !*a2 && !*((_DWORD *)ThreadInformation + 2) )
    {
      v23 = (struct CCbsSession *)*((_QWORD *)a1 + 8);
      LODWORD(ThreadInformation) = 1;
      v100[0] = 0;
      Property = ConfigGetProperty(v23, L"UseLowPriority", v100);
      *a2 = Property;
      v25 = v100[0];
      if ( Property < 0 )
        v25 = 3;
      if ( (v25 & 2) != 0 )
      {
        LogAdapter::TraceAtLevel<>(1, "Exec: Build Update detected, lowering thread priority.");
        CurrentThread = GetCurrentThread();
        v27 = SetThreadPriority(CurrentThread, -1);
        LogAdapter::TraceAtLevelIfWin32BoolFalse<>(3, v27, "Unable to set thread priority to low");
      }
      if ( (v25 & 1) != 0 )
      {
        LogAdapter::TraceAtLevel<>(1, "Exec: Build Update detected, lowering IO priority.");
        v28 = GetCurrentThread();
        v29 = NtSetInformationThread(v28, ThreadIoPriority, &ThreadInformation, 4u);
        LogAdapter::TraceAtLevelIfNtStatusFailed<long,>(3, v29, "Unable to set IO priority to low");
      }
    }
  }
  v30 = CCbsExecutionObject::DetermineComponentWatchlistPolicy(a1);
  v32 = v30;
  if ( v30 < 0 )
  {
    LODWORD(ThreadInformation) = v30;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        v31,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to determine watchlist policy.");
      p_ThreadInformation = (enum CbsPackageFailureSource *)&ThreadInformation;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&p_ThreadInformation);
    }
    v33 = 332;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v33,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectexecution.cpp",
      (const char *)v32,
      v98);
    return v32;
  }
  if ( !(unsigned int)CCbsSession::IsClientWindowsUpdate(*((CCbsSession **)a1 + 8))
    && (*(_DWORD *)(*((_QWORD *)a1 + 8) + 692LL) & 0x100000) == 0 )
  {
    v35 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(a12);
    v36 = PreventSystemSleepMode(L"Execution", v35);
    LogAdapter::TraceAtLevelIfFailed<long,>(1, v36, "Unable to block system sleep");
  }
  *a11 = CCbsSessionManager::RegisterActiveSession(
           (CCbsSessionManager *)qword_1803B11E8,
           *((struct CCbsSession **)a1 + 8),
           a1);
  v37 = (struct CCbsSession *)*((_QWORD *)a1 + 8);
  v100[0] = 0;
  if ( !(unsigned int)PackageStoreGetProperty(v37, L"Unserviceable", v100) && v100[0] )
  {
    LODWORD(ThreadInformation) = -2146498512;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"The image has been damaged by an offline servicing failure and"
                                                          " no further servicing is allowed.");
      p_ThreadInformation = (enum CbsPackageFailureSource *)&ThreadInformation;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&p_ThreadInformation);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15D,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectexecution.cpp",
      (const char *)0x800F0830LL,
      v98);
    return 2148468784LL;
  }
  if ( (unsigned int)CCbsSession::IsOffline(*((CCbsSession **)a1 + 8))
    && (unsigned __int8)StringsAreEqual(*(_QWORD *)(v38 + 648), L"Setup Platform", 0) )
  {
    LogAdapter::TraceAtLevel<>(1, "Exec: Setup Platform offline operation, skip exclusivity check.");
  }
  else
  {
    v49 = (struct CCbsSession *)*((_QWORD *)a1 + 8);
    v100[0] = 0;
    SessionGlobalExclusivity = PackageStoreGetSessionGlobalExclusivity(v49, (enum EXCLUSIVITY_TYPE::EXCLUSIVITY *)v100);
    v32 = SessionGlobalExclusivity;
    if ( SessionGlobalExclusivity < 0 )
    {
      LODWORD(ThreadInformation) = SessionGlobalExclusivity;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get session exclusivity");
        *(_QWORD *)v100 = &ThreadInformation;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v100);
      }
      v33 = 371;
      goto LABEL_19;
    }
    if ( (int)v100[0] >= 3 )
    {
      v32 = -2146498513;
      LogAdapter::TraceAtLevelHr<long,>(
        3,
        2148468783LL,
        "Exec: Cannot finalize session because an exclusive session is pending.");
      return v32;
    }
  }
  v40 = *((_QWORD *)a1 + 9);
  v41 = &qword_1802EB518;
  if ( *(_QWORD *)(v40 + 168) )
    v41 = *(const wchar_t **)(v40 + 168);
  v42 = &qword_1802EB518;
  v108 = v41;
  v43 = *((_QWORD *)a1 + 8);
  if ( *(_QWORD *)(v40 + 120) )
    v42 = *(const wchar_t **)(v40 + 120);
  v104 = (__int64)v42;
  v105[0] = *(_QWORD *)(v43 + 640);
  *(_QWORD *)&v106 = *(_QWORD *)(v43 + 648);
  if ( LogAdapter::g_Logger )
    LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t const *,wchar_t const *>(
      (_DWORD)LogAdapter::g_Logger,
      v40,
      v39,
      (unsigned int)"Exec: Processing started.  Client: {}, Session: {}, Package: {}, Identifier: {}",
      (__int64)&v106,
      (__int64)v105,
      (__int64)&v104,
      (__int64)&v108);
  v44 = *((_QWORD *)a1 + 8);
  if ( *(_QWORD *)(v44 + 648) && *(_QWORD *)(v44 + 640) )
  {
    v45 = *((_QWORD *)a1 + 9);
    v46 = &qword_1802EB518;
    v47 = *(_QWORD *)(v45 + 120) == 0;
    v106 = CbsExecuteStartEvent;
    if ( !v47 )
      v46 = *(const wchar_t **)(v45 + 120);
    v98 = (int)v46;
    CbsGenericEventReport(&v106, L"Exec: Processing started.  Client: %ls, Session: %ls, Package: %ls");
  }
  NextCounter = PackageStoreGetNextCounter(
                  *((struct CCbsSession **)a1 + 8),
                  L"NextExecutionSequence",
                  (unsigned int *)a1 + 119,
                  1);
  v32 = NextCounter;
  if ( NextCounter < 0 )
  {
    LODWORD(ThreadInformation) = NextCounter;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get next execution sequence.");
      *(_QWORD *)&v106 = &ThreadInformation;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v106);
    }
    v33 = 405;
    goto LABEL_19;
  }
  LogAdapter::TraceAtLevel<unsigned long>(1, "Exec: Using execution sequence: {}", (char *)a1 + 476);
  if ( (unsigned int)dword_1803AEEF8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1803AEEF8, 0x400000000000LL) )
  {
    *(_QWORD *)&v106 = (char *)a1 + 480;
    v53 = *(_QWORD *)(*((_QWORD *)a1 + 8) + 640LL);
    v104 = 0x80000000LL;
    v105[0] = v53;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>>(
      v53,
      (unsigned int)byte_180398E45,
      v51,
      v52,
      (__int64)&v104,
      (__int64)v105,
      (__int64)&v106);
  }
  *v107 = 1;
  IsPendingRequired = PackageStoreIsPendingRequired(*((struct CCbsSession **)a1 + 8), 0, 0);
  v55 = (CCbsSession *)*((_QWORD *)a1 + 8);
  *((_DWORD *)a1 + 24) = IsPendingRequired;
  if ( !(unsigned int)CCbsSession::IsOffline(v55) && !LODWORD(qword_1803B11E8[8].SpinCount) )
  {
    RequireShutdownProcessing(2);
    *(_DWORD *)v101 = 1;
    v57 = RegisterWinlogonNotification(*((struct CCbsSession **)a1 + 8));
    LogAdapter::TraceAtLevelIfFailed<long,>(
      1,
      v57,
      "Unable to register for Winlogon Notifications for the duration of the transaction");
  }
  if ( *((_DWORD *)a1 + 126)
    || (v58 = *((_QWORD *)a1 + 8), *(_DWORD *)(v58 + 1020) < *(_DWORD *)(v58 + 1028))
    || !*(_QWORD *)(v58 + 1112) )
  {
    v63 = (struct CCbsSession *)*((_QWORD *)a1 + 8);
    if ( *((_DWORD *)v63 + 270) )
    {
      v64 = CCbsSession::ChangeState(v63, 48, 0);
      v32 = v64;
      if ( v64 < 0 )
      {
        LODWORD(ThreadInformation) = v64;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Session start notification failed");
          v101 = &ThreadInformation;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v101);
        }
        v33 = 461;
        goto LABEL_19;
      }
      v65 = CCbsExecutionObject::ConvertClientTasksToExecutionTasks(a1, (char *)a1 + 400);
      v32 = v65;
      if ( v65 < 0 )
      {
        LODWORD(ThreadInformation) = v65;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to convert client tasks to execution tasks");
          v101 = &ThreadInformation;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v101);
        }
        v33 = 468;
        goto LABEL_19;
      }
      v66 = (unsigned __int64 *)((char *)a1 + 424);
      v67 = CCbsSession::SetTotalExecutionPhases(*((CCbsSession **)a1 + 8), *((_DWORD *)a1 + 106));
      v32 = v67;
      if ( v67 < 0 )
      {
        LODWORD(ThreadInformation) = v67;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set total execution phase");
          v101 = &ThreadInformation;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v101);
        }
        v33 = 472;
        goto LABEL_19;
      }
      if ( !*((_DWORD *)a1 + 11)
        && !(unsigned int)CCbsSession::IsOffline(*((CCbsSession **)a1 + 8))
        && !*((_DWORD *)a1 + 24) )
      {
        v68 = v103;
        v69 = LocalizedString(0x12Cu, *((void **)a1 + 58), v103);
        LogAdapter::TraceAtLevelIfFailed<long,>(
          1,
          (unsigned int)v69,
          "Exec: Failed getting localized display name string");
        if ( v69 >= 0 )
        {
          v70 = (struct CCbsSession *)*((_QWORD *)a1 + 8);
          v71 = (CCbsPackage *)*((_QWORD *)a1 + 9);
          v100[0] = 4096;
          TargetState = CCbsPackage::GetTargetState(v71, v70, 0, (enum CbsState *)v100);
          v32 = TargetState;
          if ( TargetState < 0 )
          {
            LODWORD(ThreadInformation) = TargetState;
            if ( LogAdapter::g_Logger )
            {
              v73 = *((_QWORD *)a1 + 9);
              if ( *(_QWORD *)(v73 + 120) )
                v17 = *(wchar_t ***)(v73 + 120);
              v103 = v17;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to get intended state for package:{}",
                (__int64)&v103);
              v101 = &ThreadInformation;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)&v101);
            }
            v33 = 499;
            goto LABEL_19;
          }
          v74 = v100[0];
          v75 = (wchar_t **)CbsStateToString(v100[0]);
          v76 = *((_QWORD *)a1 + 9);
          v103 = v75;
          v101 = (struct PerSessionPackageState **)CbsStateToString(*(unsigned int *)(v76 + 704));
          v78 = *((_QWORD *)a1 + 9);
          if ( *(_QWORD *)(v78 + 120) )
            v17 = *(wchar_t ***)(v78 + 120);
          v107 = v17;
          if ( LogAdapter::g_Logger )
          {
            LOBYTE(v77) = 1;
            LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
              (_DWORD)LogAdapter::g_Logger,
              v77,
              1,
              (unsigned int)"Exec: Creating restore point: Package: {}, current: {}, targeted: {}",
              (__int64)&v107,
              (__int64)&v101,
              (__int64)&v103);
          }
          if ( (int)SrBeginRestorePoint(*v68, v74 >= *(_DWORD *)(*((_QWORD *)a1 + 9) + 704LL), v109) >= 0 )
            **(_DWORD **)v99 = 1;
        }
      }
      v60 = (_DWORD *)((char *)a1 + 500);
    }
    else
    {
      v100[0] = 0;
      SessionAttributeValue = PackageStoreGetSessionAttributeValue(v63, v56, L"SessionGuide", v100);
      v32 = SessionAttributeValue;
      if ( SessionAttributeValue < 0 )
      {
        LODWORD(ThreadInformation) = SessionAttributeValue;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get session attribute on whether execution is se"
                                                              "ssion guide based.");
          *(_QWORD *)v99 = &ThreadInformation;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v99);
        }
        v33 = 527;
        goto LABEL_19;
      }
      v60 = (_DWORD *)((char *)a1 + 500);
      v66 = (unsigned __int64 *)((char *)a1 + 424);
      *((_DWORD *)a1 + 125) = v100[0] != 0;
    }
    v61 = 0;
    if ( *v60 )
    {
      v80 = *((_QWORD *)a1 + 8);
      if ( *(_DWORD *)(v80 + 1080) )
      {
        if ( !*v66 )
          __fastfail(8u);
        v84 = *((_QWORD *)a1 + 55);
        if ( *(_DWORD *)(*(_QWORD *)v84 + 168LL) )
        {
          *(_DWORD *)(v80 + 1096) = 1;
          v84 = *((_QWORD *)a1 + 55);
        }
        v85 = *v66 - 1;
        if ( v85 >= *v66 )
          __fastfail(8u);
        if ( *(_DWORD *)(*(_QWORD *)(v84 + 8 * v85) + 168LL) )
          *(_DWORD *)(*((_QWORD *)a1 + 8) + 1100LL) = 1;
        v86 = CCbsExecutionObject::PersistExecutionTasks(a1);
        v82 = v86;
        if ( v86 < 0 )
        {
          LODWORD(ThreadInformation) = v86;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to persist execution tasks.");
            *(_QWORD *)v99 = &ThreadInformation;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v99);
          }
          v83 = 562;
          goto LABEL_109;
        }
        v87 = PackageStoreSetSessionAttributeValue(*((struct CCbsSession **)a1 + 8), L"SessionGuide", 1u);
        v82 = v87;
        if ( v87 < 0 )
        {
          LODWORD(ThreadInformation) = v87;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set session attribute.");
            *(_QWORD *)v99 = &ThreadInformation;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v99);
          }
          v83 = 574;
          goto LABEL_109;
        }
      }
      else
      {
        ExecutionTasks = CCbsExecutionObject::LoadExecutionTasks(a1);
        v82 = ExecutionTasks;
        if ( ExecutionTasks < 0 )
        {
          LODWORD(ThreadInformation) = ExecutionTasks;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to load execution tasks.");
            *(_QWORD *)v99 = &ThreadInformation;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v99);
          }
          v83 = 545;
          goto LABEL_109;
        }
      }
      v59 = p_ThreadInformation;
      v88 = CCbsExecutionObject::ProcesssMultiPhaseExecution(a1, p_ThreadInformation, a4, a10);
      v82 = v88;
      if ( v88 >= 0 )
        goto LABEL_63;
      LODWORD(ThreadInformation) = v88;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to process Multi-phase execution.");
        *(_QWORD *)v99 = &ThreadInformation;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v99);
      }
      v83 = 582;
    }
    else
    {
      v59 = p_ThreadInformation;
      v89 = CCbsExecutionObject::ProcessSinglePhaseExecution(a1, (__int64)a4, (__int64)a10);
      v82 = v89;
      if ( v89 >= 0 )
        goto LABEL_63;
      LODWORD(ThreadInformation) = v89;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to process single phase execution.");
        *(_QWORD *)v99 = &ThreadInformation;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v99);
      }
      v83 = 593;
    }
LABEL_109:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v83,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectexecution.cpp",
      (const char *)v82,
      v98);
    return v82;
  }
  v59 = p_ThreadInformation;
  v60 = (_DWORD *)((char *)a1 + 500);
  v61 = 1;
  *a10 = 1;
LABEL_63:
  if ( *((_DWORD *)a1 + 13) )
  {
    v62 = CCbsExecutionObject::SetPendingStateforDelayedExecutedPackages(a1, 14);
    v32 = v62;
    if ( v62 < 0 )
    {
      LODWORD(ThreadInformation) = v62;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed setting pending state.");
        *(_QWORD *)v99 = &ThreadInformation;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v99);
      }
      v33 = 603;
      goto LABEL_19;
    }
    CCbsExecutionObject::PersistRebootReasonForDelayedPackages(a1);
    v90 = SetTrustedInstallerAutoStart(*((struct CCbsSession **)a1 + 8));
    LogAdapter::TraceAtLevelHr<long,>(
      1,
      v90,
      "Exec: Scheduled TrustedInstaller for auto-start because session was delayed.");
    RequireShutdownProcessing(1);
    LogAdapter::TraceAtLevel<>(1, "Exec: Execution Skipped for now.");
    *a10 = 1;
  }
  else if ( *a4 )
  {
    if ( *a10 )
    {
      if ( !*v60 )
      {
        v93 = CCbsExecutionObject::SetPendingStateforDelayedExecutedPackages(a1, 15);
        v32 = v93;
        if ( v93 < 0 )
        {
          LODWORD(ThreadInformation) = v93;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed setting pending state.");
            *(_QWORD *)v99 = &ThreadInformation;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v99);
          }
          v33 = 630;
          goto LABEL_19;
        }
      }
    }
  }
  v91 = *((_QWORD *)a1 + 8);
  if ( *(_QWORD *)(v91 + 1112) && !*((_DWORD *)a1 + 124) )
  {
    if ( *a4 || *((_DWORD *)a1 + 24) )
    {
      if ( !v61 )
      {
        v94 = CCbsSession::SetTotalExecutionPhases((CCbsSession *)v91, *(_DWORD *)(v91 + 1028) + 1);
        v32 = v94;
        if ( v94 < 0 )
        {
          LODWORD(ThreadInformation) = v94;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set total execution phase");
            *(_QWORD *)v99 = &ThreadInformation;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v99);
          }
          v33 = 653;
          goto LABEL_19;
        }
      }
      v95 = CCbsSession::PersistPostTransactionAction(*((CCbsSession **)a1 + 8));
      v32 = v95;
      if ( v95 < 0 )
      {
        LODWORD(ThreadInformation) = v95;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to persist post transaction action");
          *(_QWORD *)v99 = &ThreadInformation;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v99);
        }
        v33 = 656;
        goto LABEL_19;
      }
      *a4 = 1;
    }
    else
    {
      v92 = CCbsExecutionObject::ExecutePostTransactionAction(a1);
      v32 = v92;
      if ( v92 < 0 )
      {
        LODWORD(ThreadInformation) = v92;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to execute post transaction action.");
          *(_QWORD *)v99 = &ThreadInformation;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v99);
        }
        v33 = 642;
        goto LABEL_19;
      }
    }
  }
  if ( (!*a10 || *((_BYTE *)a1 + 60)) && !*((_BYTE *)a1 + 891) )
  {
    v96 = CCbsExecutionObject::FinalCommitPackagesState((_DWORD)a1, (int)a1 + 112, 0, *a4, *(_DWORD *)v59);
    *((_BYTE *)a1 + 891) = 1;
    v32 = v96;
    if ( v96 < 0 )
    {
      LODWORD(ThreadInformation) = v96;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to commit package states.");
        *(_QWORD *)v99 = &ThreadInformation;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v99);
      }
      v33 = 678;
      goto LABEL_19;
    }
  }
  LODWORD(ThreadInformation) = 0;
  v97 = CCbsExecutionObject::PostExecute(a1, (int *)&ThreadInformation);
  LogAdapter::TraceAtLevelIfFailed<long,>(1, v97, "Post execution not successful.");
  return 0;
}

```

## disassembly

```asm
0x18016f73c  push    rbp
0x18016f73e  push    rbx
0x18016f73f  push    rsi
0x18016f740  push    rdi
0x18016f741  push    r12
0x18016f743  push    r13
0x18016f745  push    r14
0x18016f747  push    r15
0x18016f749  lea     rbp, [rsp-7]
0x18016f74e  sub     rsp, 0C8h
0x18016f755  mov     rax, cs:__security_cookie
0x18016f75c  xor     rax, rsp
0x18016f75f  mov     [rbp+3Fh+var_50], rax
0x18016f763  mov     rax, [rbp+3Fh+arg_20]
0x18016f767  mov     rdi, rcx
0x18016f76a  mov     r13, [rbp+3Fh+arg_48]
0x18016f771  mov     r12, r9
0x18016f774  mov     r15, [rbp+3Fh+arg_50]
0x18016f77b  mov     rbx, rdx
0x18016f77e  mov     rsi, [rbp+3Fh+arg_58]
0x18016f785  mov     [rbp+3Fh+var_60], rax
0x18016f789  mov     rax, [rbp+3Fh+arg_28]
0x18016f78d  mov     qword ptr [rsp+100h+var_C0], rax
0x18016f792  mov     rax, [rbp+3Fh+arg_30]
0x18016f796  mov     [rbp+3Fh+var_B0], rax
0x18016f79a  mov     rax, [rbp+3Fh+arg_38]
0x18016f7a1  mov     [rbp+3Fh+var_70], rax
0x18016f7a5  mov     rax, [rbp+3Fh+arg_40]
0x18016f7ac  mov     [rbp+3Fh+var_A8], rax
0x18016f7b0  mov     rax, [rcx+40h]
0x18016f7b4  mov     [rbp+3Fh+var_A0], r8
0x18016f7b8  mov     dword ptr [rax+2F8h], 1
0x18016f7c2  mov     rcx, [rcx+40h]; this
0x18016f7c6  call    ?IsOffline@CCbsSession@@QEBAHXZ; CCbsSession::IsOffline(void)
0x18016f7cb  lea     r14, qword_1802EB518
0x18016f7d2  mov     edx, 3
0x18016f7d7  test    eax, eax
0x18016f7d9  jnz     loc_18016F936
0x18016f7df  mov     rcx, [rcx+288h]
0x18016f7e6  lea     rdx, aSetupPlatform; "Setup Platform"
0x18016f7ed  xor     r8d, r8d
0x18016f7f0  call    StringsAreEqual
0x18016f7f5  test    al, al
0x18016f7f7  jz      loc_18016F931
0x18016f7fd  mov     rdx, [rdi+48h]; struct CCbsPackage *
0x18016f801  lea     r8, [rbp+3Fh+ThreadInformation]; struct PerSessionPackageState **
0x18016f805  mov     rcx, [rdi+40h]; this
0x18016f809  xor     r9d, r9d; unsigned __int64 *
0x18016f80c  mov     [rbp+3Fh+ThreadInformation], 0
0x18016f814  call    ?GetSessionPackageState@CCbsSession@@QEAAJPEAVCCbsPackage@@PEAPEAUPerSessionPackageState@@PEA_K@Z; CCbsSession::GetSessionPackageState(CCbsPackage *,PerSessionPackageState * *,unsigned __int64 *)
0x18016f819  mov     [rbx], eax
0x18016f81b  mov     rdx, r14
0x18016f81e  mov     rcx, [rdi+48h]
0x18016f822  cmp     qword ptr [rcx+78h], 0
0x18016f827  cmovnz  rdx, [rcx+78h]
0x18016f82c  mov     qword ptr [rbp+3Fh+var_B8], rdx
0x18016f830  test    eax, eax
0x18016f832  jns     short loc_18016F84B
0x18016f834  lea     r9, [rbp+3Fh+var_B8]
0x18016f838  mov     edx, eax
0x18016f83a  lea     r8, aUnableToGetSes; "Unable to get session package state for"...
0x18016f841  mov     ecx, 1
0x18016f846  call    ??$TraceAtLevelHr@JPEB_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelHr<long,wchar_t const *>(LogAdapter::LogLevel,long,char const * const,wchar_t const * const &)
0x18016f84b  cmp     dword ptr [rbx], 0
0x18016f84e  jnz     loc_18016F931
0x18016f854  mov     rax, [rbp+3Fh+ThreadInformation]
0x18016f858  cmp     dword ptr [rax+8], 0
0x18016f85c  jnz     loc_18016F931
0x18016f862  mov     rcx, [rdi+40h]; struct CCbsSession *
0x18016f866  lea     r8, [rbp+3Fh+var_B8]; unsigned int *
0x18016f86a  lea     rdx, aUselowpriority; "UseLowPriority"
0x18016f871  mov     dword ptr [rbp+3Fh+ThreadInformation], 1
0x18016f878  mov     [rbp+3Fh+var_B8], 0
0x18016f87f  call    ?ConfigGetProperty@@YAJPEAVCCbsSession@@PEB_WPEAK@Z; ConfigGetProperty(CCbsSession *,wchar_t const *,ulong *)
0x18016f884  mov     [rbx], eax
0x18016f886  test    eax, eax
0x18016f888  mov     ebx, [rbp+3Fh+var_B8]
0x18016f88b  mov     edx, 3
0x18016f890  cmovs   ebx, edx
0x18016f893  test    bl, 2
0x18016f896  jz      short loc_18016F8DF
0x18016f898  lea     rdx, aExecBuildUpdat; "Exec: Build Update detected, lowering t"...
0x18016f89f  mov     ecx, 1
0x18016f8a4  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x18016f8a9  call    cs:__imp_GetCurrentThread
0x18016f8b0  nop     dword ptr [rax+rax+00h]
0x18016f8b5  mov     rcx, rax; hThread
0x18016f8b8  or      edx, 0FFFFFFFFh; nPriority
0x18016f8bb  call    cs:__imp_SetThreadPriority
0x18016f8c2  nop     dword ptr [rax+rax+00h]
0x18016f8c7  lea     r8, aUnableToSetThr; "Unable to set thread priority to low"
0x18016f8ce  mov     ecx, 3
0x18016f8d3  mov     edx, eax
0x18016f8d5  call    ??$TraceAtLevelIfWin32BoolFalse@$$V@LogAdapter@@YAXW4LogLevel@0@HQEBD@Z; LogAdapter::TraceAtLevelIfWin32BoolFalse<>(LogAdapter::LogLevel,int,char const * const)
0x18016f8da  mov     edx, 3
0x18016f8df  test    bl, 1
0x18016f8e2  jz      short loc_18016F936
0x18016f8e4  lea     rdx, aExecBuildUpdat_0; "Exec: Build Update detected, lowering I"...
0x18016f8eb  mov     ecx, 1
0x18016f8f0  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x18016f8f5  call    cs:__imp_GetCurrentThread
0x18016f8fc  nop     dword ptr [rax+rax+00h]
0x18016f901  mov     r9d, 4; ThreadInformationLength
0x18016f907  lea     r8, [rbp+3Fh+ThreadInformation]; ThreadInformation
0x18016f90b  mov     rcx, rax; ThreadHandle
0x18016f90e  lea     edx, [r9+12h]; ThreadInformationClass
0x18016f912  call    cs:__imp_NtSetInformationThread
0x18016f919  nop     dword ptr [rax+rax+00h]
0x18016f91e  lea     r8, aUnableToSetIoP; "Unable to set IO priority to low"
0x18016f925  mov     ecx, 3
0x18016f92a  mov     edx, eax
0x18016f92c  call    ??$TraceAtLevelIfNtStatusFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfNtStatusFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x18016f931  mov     edx, 3
0x18016f936  mov     rcx, rdi; this
0x18016f939  call    ?DetermineComponentWatchlistPolicy@CCbsExecutionObject@@AEAAJXZ; CCbsExecutionObject::DetermineComponentWatchlistPolicy(void)
0x18016f93e  mov     ebx, eax
0x18016f940  test    eax, eax
0x18016f942  jns     short loc_18016F9AF
0x18016f944  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18016f94b  mov     dword ptr [rbp+3Fh+ThreadInformation], eax
0x18016f94e  test    rcx, rcx
0x18016f951  jz      short loc_18016F990
0x18016f953  mov     r8d, edx
0x18016f956  lea     r9, aFailedToDeterm_13; "Failed to determine watchlist policy."
0x18016f95d  xor     edx, edx
0x18016f95f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18016f964  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18016f96b  lea     rax, [rbp+3Fh+ThreadInformation]
0x18016f96f  mov     [rbp+3Fh+var_A8], rax
0x18016f973  lea     r9, asc_1802EE7AC; ": {}"
0x18016f97a  lea     rax, [rbp+3Fh+var_A8]
0x18016f97e  mov     r8d, 3
0x18016f984  mov     dl, 1
0x18016f986  mov     [rsp+100h+var_E0], rax; int
0x18016f98b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18016f990  mov     edx, 14Ch; void *
0x18016f995  mov     rcx, [rbp+47h]; this
0x18016f999  lea     r8, aOnecoreBaseCbs_116; "onecore\\base\\cbs\\core\\cbsexecutiono"...
0x18016f9a0  mov     r9d, ebx; char *
0x18016f9a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016f9a8  mov     eax, ebx
0x18016f9aa  jmp     loc_1801707D1
0x18016f9af  mov     rcx, [rdi+40h]; this
0x18016f9b3  call    ?IsClientWindowsUpdate@CCbsSession@@QEBAHXZ; CCbsSession::IsClientWindowsUpdate(void)
0x18016f9b8  test    eax, eax
0x18016f9ba  jnz     short loc_18016F9F6
0x18016f9bc  mov     rax, [rdi+40h]
0x18016f9c0  test    dword ptr [rax+2B4h], 100000h
0x18016f9ca  jnz     short loc_18016F9F6
0x18016f9cc  mov     rcx, rsi
0x18016f9cf  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18016f9d4  mov     rdx, rax
0x18016f9d7  lea     rcx, aExecution; "Execution"
0x18016f9de  call    PreventSystemSleepMode
0x18016f9e3  lea     r8, aUnableToBlockS; "Unable to block system sleep"
0x18016f9ea  mov     edx, eax
0x18016f9ec  mov     ecx, 1
0x18016f9f1  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x18016f9f6  mov     rdx, [rdi+40h]; struct CCbsSession *
0x18016f9fa  mov     r8, rdi; struct CCbsExecutionObject *
0x18016f9fd  mov     rcx, cs:qword_1803B11E8; this
0x18016fa04  call    ?RegisterActiveSession@CCbsSessionManager@@QEAAKPEAVCCbsSession@@PEAVCCbsExecutionObject@@@Z; CCbsSessionManager::RegisterActiveSession(CCbsSession *,CCbsExecutionObject *)
0x18016fa09  mov     [r15], eax
0x18016fa0c  lea     r8, [rbp+3Fh+var_B8]; unsigned int *
0x18016fa10  mov     rcx, [rdi+40h]; struct CCbsSession *
0x18016fa14  lea     rdx, aUnserviceable; "Unserviceable"
0x18016fa1b  xor     r15d, r15d
0x18016fa1e  mov     [rbp+3Fh+var_B8], r15d
0x18016fa22  call    ?PackageStoreGetProperty@@YAJPEAVCCbsSession@@PEB_WPEAK@Z; PackageStoreGetProperty(CCbsSession *,wchar_t const *,ulong *)
0x18016fa27  test    eax, eax
0x18016fa29  jnz     short loc_18016FAA1
0x18016fa2b  cmp     [rbp+3Fh+var_B8], r15d
0x18016fa2f  jz      short loc_18016FAA1
0x18016fa31  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18016fa38  mov     edi, 800F0830h
0x18016fa3d  mov     dword ptr [rbp+3Fh+ThreadInformation], edi
0x18016fa40  test    rcx, rcx
0x18016fa43  jz      short loc_18016FA82
0x18016fa45  lea     ebx, [rax+3]
0x18016fa48  xor     edx, edx
0x18016fa4a  mov     r8d, ebx
0x18016fa4d  lea     r9, aTheImageHasBee; "The image has been damaged by an offlin"...
0x18016fa54  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18016fa59  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18016fa60  lea     rax, [rbp+3Fh+ThreadInformation]
0x18016fa64  mov     [rbp+3Fh+var_A8], rax
0x18016fa68  lea     r9, asc_1802EE7AC; ": {}"
0x18016fa6f  lea     rax, [rbp+3Fh+var_A8]
0x18016fa73  mov     r8d, ebx
0x18016fa76  mov     dl, 1
0x18016fa78  mov     [rsp+100h+var_E0], rax; int
0x18016fa7d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18016fa82  mov     rcx, [rbp+47h]; this
0x18016fa86  lea     r8, aOnecoreBaseCbs_116; "onecore\\base\\cbs\\core\\cbsexecutiono"...
0x18016fa8d  mov     r9d, edi; char *
0x18016fa90  mov     edx, 15Dh; void *
0x18016fa95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016fa9a  mov     eax, edi
0x18016fa9c  jmp     loc_1801707D1
0x18016faa1  mov     rcx, [rdi+40h]; this
0x18016faa5  call    ?IsOffline@CCbsSession@@QEBAHXZ; CCbsSession::IsOffline(void)
0x18016faaa  test    eax, eax
0x18016faac  jz      loc_18016FC2F
0x18016fab2  mov     rcx, [rcx+288h]
0x18016fab9  lea     rdx, aSetupPlatform; "Setup Platform"
0x18016fac0  xor     r8d, r8d
0x18016fac3  call    StringsAreEqual
0x18016fac8  test    al, al
0x18016faca  jz      loc_18016FC2F
0x18016fad0  lea     rdx, aExecSetupPlatf; "Exec: Setup Platform offline operation,"...
0x18016fad7  mov     ecx, 1
0x18016fadc  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x18016fae1  mov     rdx, [rdi+48h]
0x18016fae5  mov     rcx, r14
0x18016fae8  mov     rax, [rdx+0A8h]
0x18016faef  test    rax, rax
0x18016faf2  cmovnz  rcx, rax
0x18016faf6  mov     rax, r14
0x18016faf9  mov     [rbp+3Fh+var_68], rcx
0x18016fafd  cmp     [rdx+78h], r15
0x18016fb01  mov     rcx, [rdi+40h]
0x18016fb05  cmovnz  rax, [rdx+78h]
0x18016fb0a  mov     [rbp+3Fh+var_98], rax
0x18016fb0e  mov     rax, [rcx+280h]
0x18016fb15  mov     [rbp+3Fh+var_90], rax
0x18016fb19  mov     rax, [rcx+288h]
0x18016fb20  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18016fb27  mov     qword ptr [rbp+3Fh+var_80], rax
0x18016fb2b  test    rcx, rcx
0x18016fb2e  jz      short loc_18016FB60
0x18016fb30  lea     rax, [rbp+3Fh+var_68]
0x18016fb34  mov     [rsp+100h+var_C8], rax
0x18016fb39  lea     r9, aExecProcessing_5; "Exec: Processing started.  Client: {}, "...
0x18016fb40  lea     rax, [rbp+3Fh+var_98]
0x18016fb44  mov     [rsp+100h+var_D0], rax
0x18016fb49  lea     rax, [rbp+3Fh+var_90]
0x18016fb4d  mov     [rsp+100h+var_D8], rax
0x18016fb52  lea     rax, [rbp+3Fh+var_80]
0x18016fb56  mov     [rsp+100h+var_E0], rax
0x18016fb5b  call    ??$LogNumObjects@PEA_WPEA_WPEB_WPEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEA_W3AEBQEB_W4@Z; LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t const *,wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t * const &,wchar_t * const &,wchar_t const * const &,wchar_t const * const &)
0x18016fb60  mov     rax, [rdi+40h]
0x18016fb64  mov     r8, [rax+288h]
0x18016fb6b  test    r8, r8
0x18016fb6e  jz      short loc_18016FBAD
0x18016fb70  mov     r9, [rax+280h]
0x18016fb77  test    r9, r9
0x18016fb7a  jz      short loc_18016FBAD
0x18016fb7c  mov     rax, [rdi+48h]
0x18016fb80  lea     rdx, aExecProcessing_4; "Exec: Processing started.  Client: %ls,"...
0x18016fb87  movups  xmm0, cs:CbsExecuteStartEvent
0x18016fb8e  mov     rcx, r14
0x18016fb91  cmp     [rax+78h], r15
0x18016fb95  movdqu  [rbp+3Fh+var_80], xmm0
0x18016fb9a  cmovnz  rcx, [rax+78h]
0x18016fb9f  mov     [rsp+100h+var_E0], rcx
0x18016fba4  lea     rcx, [rbp+3Fh+var_80]
0x18016fba8  call    CbsGenericEventReport
0x18016fbad  mov     rcx, [rdi+40h]; struct CCbsSession *
0x18016fbb1  lea     rsi, [rdi+1DCh]
0x18016fbb8  mov     r8, rsi; unsigned int *
0x18016fbbb  lea     rdx, aNextexecutions; "NextExecutionSequence"
0x18016fbc2  mov     r9d, 1; int
0x18016fbc8  call    ?PackageStoreGetNextCounter@@YAJPEAVCCbsSession@@PEB_WPEAKH@Z; PackageStoreGetNextCounter(CCbsSession *,wchar_t const *,ulong *,int)
0x18016fbcd  mov     ebx, eax
0x18016fbcf  test    eax, eax
0x18016fbd1  jns     loc_18016FCC5
0x18016fbd7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18016fbde  mov     dword ptr [rbp+3Fh+ThreadInformation], eax
0x18016fbe1  test    rcx, rcx
0x18016fbe4  jz      short loc_18016FC25
0x18016fbe6  mov     edi, 3
0x18016fbeb  lea     r9, aFailedToGetNex_16; "Failed to get next execution sequence."
0x18016fbf2  mov     r8d, edi
0x18016fbf5  xor     edx, edx
0x18016fbf7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18016fbfc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18016fc03  lea     rax, [rbp+3Fh+ThreadInformation]
0x18016fc07  mov     qword ptr [rbp+3Fh+var_80], rax
0x18016fc0b  lea     r9, asc_1802EE7AC; ": {}"
0x18016fc12  lea     rax, [rbp+3Fh+var_80]
0x18016fc16  mov     r8d, edi
0x18016fc19  mov     dl, 1
0x18016fc1b  mov     [rsp+100h+var_E0], rax
0x18016fc20  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18016fc25  mov     edx, 195h
0x18016fc2a  jmp     loc_18016F995
0x18016fc2f  mov     rcx, [rdi+40h]; struct CCbsSession *
0x18016fc33  lea     rdx, [rbp+3Fh+var_B8]; enum EXCLUSIVITY_TYPE::EXCLUSIVITY *
0x18016fc37  mov     [rbp+3Fh+var_B8], r15d
0x18016fc3b  call    ?PackageStoreGetSessionGlobalExclusivity@@YAJPEAVCCbsSession@@PEAW4EXCLUSIVITY@EXCLUSIVITY_TYPE@@@Z; PackageStoreGetSessionGlobalExclusivity(CCbsSession *,EXCLUSIVITY_TYPE::EXCLUSIVITY *)
0x18016fc40  mov     ebx, eax
0x18016fc42  test    eax, eax
0x18016fc44  jns     short loc_18016FC9E
0x18016fc46  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18016fc4d  mov     dword ptr [rbp+3Fh+ThreadInformation], eax
0x18016fc50  test    rcx, rcx
0x18016fc53  jz      short loc_18016FC94
0x18016fc55  mov     edi, 3
0x18016fc5a  lea     r9, aFailedToGetSes_1; "Failed to get session exclusivity"
0x18016fc61  mov     r8d, edi
  ... truncated ...
```
