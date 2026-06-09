# CCbsExecutionObject::InstallUninstallChainInternal(int,int &,int &,int &,int &,int &,int &,unsigned __int64 &,ulong &,_CBS_VERSION &,_CBS_VERSION &,CCbsOSVersionPublisher &,CCbsExecutionSpecialTransformers &,DoqExecuteImmediate &,CCbsInterfaceArray<CCbsExecutionUpdate *> &)

- ea: `0x1801829cc`
- end: `0x18018487e`
- name: `?InstallUninstallChainInternal@CCbsExecutionObject@@AEAAJHAEAH00000AEA_KAEAKAEAT_CBS_VERSION@@3AEAVCCbsOSVersionPublisher@@AEAVCCbsExecutionSpecialTransformers@@AEAVDoqExecuteImmediate@@AEAV?$CCbsInterfaceArray@PEAVCCbsExecutionUpdate@@@@@Z`
- size: `7858`
- prototype: `__int64 __usercall@<rax>(CCbsExecutionObject *this@<rcx>, __int64, __int64, __int64, __int64, __int64, __int64, union _CBS_VERSION *, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `69`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180182458`

## callees

- `0x180010cc0`
- `0x180012fe4`
- `0x180013250`
- `0x180016d40`
- `0x180028e24`
- `0x180042448`
- `0x180048c24`
- `0x18005620c`
- `0x18005b180`
- `0x180064934`
- `0x180065920`
- `0x180065f88`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a8058`
- `0x1800a8438`
- `0x1800a8678`
- `0x1800ad504`
- `0x1800ad8cc`
- `0x1800ae508`
- `0x1800b980c`
- `0x1800c82d8`
- `0x1800cf6f8`
- `0x1800d28bc`
- `0x1800e1850`
- `0x1800eb920`
- `0x1800ef360`
- `0x1800f60c4`
- `0x1800f618c`
- `0x1800f8500`
- `0x1800ff474`
- `0x1800ffd84`
- `0x180126a14`
- `0x18012a934`
- `0x18012ad40`
- `0x18012e0f8`
- `0x180145828`
- `0x180146ac0`
- `0x180146cb8`
- `0x1801474b0`
- `0x180148378`
- `0x180148cac`
- `0x180149be8`
- `0x18014b730`
- `0x18014cbf4`
- `0x18014d46c`
- `0x18014d6e8`
- `0x18014db70`

## string_xrefs

- `0x1801830db`: `Failed to process component watch list.`
- `0x18018309b`: `Plan: Start to process component watchlist`
- `0x1801832ed`: `Exec: package or update requires restart, delay the execution to shutdown.`
- `0x180183266`: `Exec: package or update requires restart but ignoring because it is being removed by deep clean, which means it was superseded`
- `0x18018320d`: `Failed to set cim payload source for CIM based update.`
- `0x180182cde`: `Failed to check whether package was already earlier pended.`
- `0x180182c2a`: `onecore\base\cbs\core\cbsexecutionobjectinstall.cpp`
- `0x180182e64`: `onecore\base\cbs\core\cbsexecutionobjectinstall.cpp`
- `0x180182f4e`: `onecore\base\cbs\core\cbsexecutionobjectinstall.cpp`
- `0x180183448`: `onecore\base\cbs\core\cbsexecutionobjectinstall.cpp`
- `0x180183651`: `onecore\base\cbs\core\cbsexecutionobjectinstall.cpp`
- `0x1801840b3`: `onecore\base\cbs\core\cbsexecutionobjectinstall.cpp`
- `0x180182f06`: `Failed to create CSI transaction for executing.`
- `0x180182e1c`: `Failed creating committer for Desktop update`
- `0x180182dab`: `Failed creating committer for CIM based update`
- `0x180182d2e`: `Exec: Task package already smart pended by earlier sessions, force package smart pend`
- `0x180183989`: `Doqe: Driver operations completed successfully.`
- `0x1801839a3`: `Doqe: Driver operations completed successfully.`
- `0x18018382b`: `Failed executing special install transformers`
- `0x180183a79`: `Failed executing special install transformers`
- `0x180183b83`: `Unable to configure poqexec pend location.`
- `0x1801843ae`: `Unable to configure poqexec pend location.`
- `0x180184413`: `Unable to configure poqexec pend location.`
- `0x180183ad5`: `Exec: Skipping transaction commit since nothing was changed.`
- `0x1801839bf`: `Doqe: interactive driver operations completed but required a reboot.`
- `0x1801839b3`: `Doqe: interactive driver operations completed.`
- `0x180183523`: `Analysis indicated that installation cannot succeed without pending.`
- `0x180183405`: `CBS already has pended content.`
- `0x180183305`: `Exec: The Package or one of its Updates required and client specified DelayExecutionIfPendRequired, Execution will be delayed to system shutdown time.`
- `0x180184235`: `Exec: The Package or one of its Updates required and client specified DelayExecutionIfPendRequired, Execution will be delayed to system shutdown time.`
- `0x1801846f4`: `Exec: Transaction failed, and an advanced installer required a reboot.`
- `0x1801847bd`: `Exec: Cancelled pending transactions after rollback.`
- `0x180184745`: `Exec: An error occurred while committing the transaction and the transaction rollback requires a reboot.`
- `0x180184729`: `Exec: Scheduled TrustedInstaller for auto-start because rollback was pended.`
- `0x180183d1c`: `Unable to finalize driver installs`
- `0x180183caf`: `Doqe: primitives did not complete, so rolling back interactive driver operations.`
- `0x180183e46`: `Exec: Failed to commit CSI transaction to execute changes.`
- `0x180183d7c`: `Exec: An error occurred while committing the transaction, the transaction has been rolled back.`
- `0x180184264`: `Exec: Failed to commit CSI transaction due to file in use or Component reboot required, package changes need to be pended.`
- `0x18018424b`: `Exec: Failed to commit CSI transaction due to file in use or Component reboot required and client specified DelayExecutionIfPendRequired, Execution will be delayed to system shutdown time.`
- `0x18018423e`: `Exec: The Package or one of its Updates required a reboot so transaction commit was skipped, Package's changes need to be pended.`
- `0x1801844ce`: `Exec: Pended transaction, changes will be applied during shutdown/startup processing.`
- `0x180184423`: `Exec: Restoring driver operations because of a CSI commit failure.`
- `0x180183f43`: `Unable to get offline boot directory`
- `0x180183f09`: `Exec: Although the offline commit completed immediately, CBS has to consider it pended due to a previous operation.`
- `0x180183eec`: `Exec: Offline commit completes with no pending online operations.`
- `0x180184800`: `Exec: An error occurred while committing the transaction, the transaction could not be rolled back.`
- `0x18018401d`: `Exec: Pended transaction, changes will be applied during startup processing. Scheduled TrustedInstaller for auto-start.`
- `0x180183fc3`: `Exec: Removed package list file from {}`
- `0x180183f9f`: `Unable to remove package list file: {}`
- `0x180183f64`: `Unable to allocate package list path`
- `0x18018413c`: `Exec: Advanced installer executed successfully but still required a reboot.`
- `0x18018451b`: `Exec: Skipping shutdown processing as it is using CIM based update flow.`
- `0x18018416f`: `Exec: Scheduled TrustedInstaller for auto-start because we pended the transaction.`
- `0x1801844fa`: `Exec: Scheduled TrustedInstaller for auto-start because we pended the transaction.`
- `0x1801845d3`: `Exec: Scavenge on completion requested by session.`
- `0x180184071`: `If a transaction was already pending, then we must have pended the transaction again.`
- `0x1801841cd`: `Exec: Scheduled TrustedInstaller for auto-start because interactive drivers required a reboot.`

## pseudocode

```c
__int64 __fastcall CCbsExecutionObject::InstallUninstallChainInternal(
        CCbsExecutionObject *this,
        __int64 a2,
        BOOL *a3,
        int *a4,
        int *a5,
        __int64 a6,
        _DWORD *a7,
        _DWORD *a8,
        __int64 *a9,
        WCHAR *a10,
        union _CBS_VERSION *a11,
        union _CBS_VERSION *a12,
        wchar_t *a13,
        CCbsExecutionSpecialTransformers *a14,
        struct HDRIVERUPDATECONTEXT__ **a15,
        __int64 a16)
{
  union _CBS_VERSION *v16; // r12
  __int64 v18; // rbx
  BOOL *v19; // r15
  unsigned int v20; // r8d
  CCbsSession **v21; // r14
  CCbsSession *v22; // rax
  int v23; // eax
  int v24; // edi
  __int64 v25; // rdx
  __int64 v26; // r8
  unsigned int ProgressCost; // eax
  __int64 v28; // r11
  int v29; // eax
  CCbsSession *v30; // rcx
  int IsTaskPackageAlreadySmartPended; // eax
  CCbsSession *v33; // rcx
  int v34; // eax
  int v35; // eax
  unsigned int v36; // ebx
  __int64 v37; // rdx
  int v38; // eax
  int v39; // eax
  __int64 v40; // rdx
  int v41; // eax
  int v42; // edx
  int v43; // eax
  int v44; // eax
  __int64 v45; // rax
  _QWORD *v46; // r15
  _QWORD *v47; // r12
  int v48; // ecx
  int v49; // eax
  int v50; // edi
  __int64 v51; // rax
  int v52; // edi
  int ShouldTheExecutionSmartPended; // eax
  const wchar_t *v54; // rdx
  const wchar_t *v55; // rdx
  int IsOffline; // eax
  unsigned __int8 v57; // r15
  unsigned int v58; // edi
  int v59; // eax
  unsigned int v60; // r15d
  __int64 v61; // rdx
  union _CBS_VERSION *v62; // rcx
  int v63; // eax
  CCbsExecutionSpecialTransformers *v64; // r15
  int TransformersFromAnalysis; // eax
  int v66; // eax
  int v67; // eax
  int v68; // eax
  int v69; // r12d
  int v70; // eax
  LPCWSTR v71; // rdx
  struct HDRIVERUPDATECONTEXT__ **v72; // rcx
  struct CCbsSession *v73; // rcx
  const char *v74; // r8
  const char *v75; // rdx
  int v76; // eax
  int v77; // eax
  unsigned int v78; // r15d
  int v79; // eax
  struct CCbsSession *v80; // rcx
  unsigned int v81; // edi
  unsigned int v82; // eax
  CCbsSession *v83; // rcx
  int v84; // eax
  struct CCbsSession *v85; // rcx
  unsigned int v86; // r8d
  unsigned int v87; // eax
  unsigned int v88; // eax
  unsigned int v89; // eax
  int v90; // r8d
  unsigned int v91; // ecx
  unsigned int v92; // eax
  unsigned int v93; // r8d
  CCbsSession *v94; // rcx
  int v95; // r8d
  __int64 v96; // rcx
  int v97; // r8d
  BOOL *v98; // r15
  int v99; // eax
  int OfflineWindowsDirectory; // eax
  const char *v101; // r8
  const WCHAR *v102; // rdi
  int v103; // eax
  BOOL v104; // eax
  unsigned int v105; // eax
  char v106; // r12
  unsigned int v107; // eax
  const char *v108; // r8
  int v109; // eax
  int v110; // edi
  const char *v111; // rdx
  int v112; // eax
  __int64 *v113; // r15
  int v114; // eax
  unsigned int v115; // eax
  CCbsSession *v116; // rcx
  unsigned int v117; // eax
  unsigned int v118; // eax
  __int64 v119; // rcx
  int v120; // eax
  bool v121; // zf
  unsigned int v122; // eax
  int v123; // eax
  char v124; // di
  const char *v125; // rdx
  const char *v126; // rdx
  unsigned int v127; // eax
  const char *v128; // rdx
  unsigned int v129; // eax
  __int64 v130; // rcx
  unsigned int v131; // eax
  unsigned int v132; // eax
  int v133; // [rsp+20h] [rbp-E0h]
  unsigned int *v134; // [rsp+20h] [rbp-E0h]
  struct ICSITransaction *v135; // [rsp+50h] [rbp-B0h] BYREF
  char v136; // [rsp+58h] [rbp-A8h]
  __int64 v137; // [rsp+60h] [rbp-A0h] BYREF
  bool v138; // [rsp+68h] [rbp-98h]
  int v139[4]; // [rsp+70h] [rbp-90h] BYREF
  int v140[2]; // [rsp+80h] [rbp-80h] BYREF
  BOOL *v141; // [rsp+88h] [rbp-78h]
  wchar_t *v142; // [rsp+90h] [rbp-70h] BYREF
  __int64 v143; // [rsp+98h] [rbp-68h]
  LPCWSTR lpExistingFileName; // [rsp+A0h] [rbp-60h] BYREF
  int *v145; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v146; // [rsp+B0h] [rbp-50h] BYREF
  union _CBS_VERSION *v147; // [rsp+B8h] [rbp-48h]
  __int64 *v148; // [rsp+C0h] [rbp-40h]
  struct HDRIVERUPDATECONTEXT__ **v149; // [rsp+C8h] [rbp-38h]
  int *v150; // [rsp+D0h] [rbp-30h] BYREF
  CCbsExecutionSpecialTransformers *v151; // [rsp+D8h] [rbp-28h]
  union _CBS_VERSION *v152; // [rsp+E0h] [rbp-20h]
  _DWORD *v153; // [rsp+E8h] [rbp-18h]
  _DWORD *v154; // [rsp+F0h] [rbp-10h]
  int *v155; // [rsp+F8h] [rbp-8h] BYREF
  int v156[2]; // [rsp+100h] [rbp+0h] BYREF
  int v157; // [rsp+108h] [rbp+8h] BYREF
  struct IUnknown *v158; // [rsp+110h] [rbp+10h] BYREF
  int v159; // [rsp+118h] [rbp+18h] BYREF
  unsigned int v160; // [rsp+11Ch] [rbp+1Ch] BYREF
  _BYTE v161[40]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v16 = a11;
  v151 = a14;
  v18 = 0;
  v19 = a3;
  v147 = a12;
  v150 = a5;
  *(_QWORD *)v140 = a6;
  v154 = a7;
  v153 = a8;
  v148 = a9;
  v142 = a13;
  v149 = a15;
  v143 = a16;
  v145 = a4;
  v141 = a3;
  v152 = a11;
  lpExistingFileName = a10;
  v146 = 0;
  LogAdapter::TraceAtLevel<>(1, "Perf: Execute chain started.");
  *(_OWORD *)v139 = CbsInstallUninstallStartEvent;
  CbsGenericEventReport(v139, L"Perf: Execute chain started.");
  v21 = (CCbsSession **)((char *)this + 64);
  v135 = 0;
  v137 = 0;
  v160 = 0;
  v159 = 0;
  v158 = 0;
  if ( *((_DWORD *)this + 10) || (v22 = *v21, v136 = 1, (*((_DWORD *)v22 + 173) & 0x4000) != 0) )
    v136 = 0;
  Windows::Rtl::StopWatch::StopWatch((Windows::Rtl::StopWatch *)v161, (CCbsSession *)((char *)*v21 + 304), v20);
  if ( !*((_DWORD *)this + 14) && !(unsigned int)CCbsSession::IsOffline(*v21) )
    *(_DWORD *)a10 = 7;
  v23 = CCbsExecutionObject::SetPendingStateforDelayedExecutedPackages(this, 15);
  v24 = v23;
  if ( v23 < 0 )
  {
    v157 = v23;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed setting pending state.");
      v155 = &v157;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v155);
    }
    v25 = 76;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectinstall.cpp",
      (const char *)(unsigned int)v24,
      v133);
LABEL_30:
    Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v161);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v158);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v137);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v135);
    return (unsigned int)v24;
  }
  SetRebootReason(*v21);
  if ( *((_QWORD *)this + 3) )
  {
    ProgressCost = CCbsExecutionObject::GetProgressCost(this);
    v29 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v28 + 32LL))(v28, 50, ProgressCost);
    v24 = v29;
    if ( v29 < 0 )
    {
      v159 = v29;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Exec: Client cancelled");
        *(_QWORD *)v156 = &v159;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v156);
      }
      v25 = 91;
      goto LABEL_16;
    }
  }
  if ( *((_DWORD *)this + 24) )
    SetRebootReason(*v21);
  if ( (*((_BYTE *)*v21 + 688) & 0x40) != 0 )
  {
    *(_QWORD *)v139 = *((_QWORD *)*v21 + 80);
    if ( LogAdapter::g_Logger )
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        1,
        1,
        (__int64)"Exec: Client forces reboot on session: {}",
        (__int64)v139);
    v30 = *v21;
    v159 = 1;
    SetRebootReason(v30);
  }
  if ( !*((_DWORD *)this + 126) )
  {
    v157 = 0;
    IsTaskPackageAlreadySmartPended = CCbsExecutionObject::IsTaskPackageAlreadySmartPended(this, &v157);
    v24 = IsTaskPackageAlreadySmartPended;
    if ( IsTaskPackageAlreadySmartPended < 0 )
    {
      v157 = IsTaskPackageAlreadySmartPended;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to check whether package was already earlier pended.");
        *(_QWORD *)v139 = &v157;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v139);
      }
      v25 = 125;
      goto LABEL_16;
    }
    if ( v157 )
    {
      LogAdapter::TraceAtLevel<>(
        1,
        "Exec: Task package already smart pended by earlier sessions, force package smart pend");
      *((_DWORD *)this + 13) = 1;
      v24 = 0;
      *v19 = 1;
      goto LABEL_30;
    }
  }
  v33 = *v21;
  v34 = *((_DWORD *)*v21 + 173);
  if ( (v34 & 0x80000) != 0 )
  {
    v35 = CCbsSession::CreateServicingCommitter(v33, 2, v26, &v146);
    v36 = v35;
    if ( v35 < 0 )
    {
      v157 = v35;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed creating committer for CIM based update");
        *(_QWORD *)v139 = &v157;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v139);
      }
      v37 = 146;
LABEL_42:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v37,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectinstall.cpp",
        (const char *)v36,
        v133);
      Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v161);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v158);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v137);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v135);
      if ( v146 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v146 + 16LL))(v146);
      return v36;
    }
  }
  else
  {
    if ( (v34 & 0x400) == 0 )
      goto LABEL_46;
    v38 = CCbsSession::CreateServicingCommitter(v33, 3, v26, &v146);
    v36 = v38;
    if ( v38 < 0 )
    {
      v157 = v38;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed creating committer for Desktop update");
        *(_QWORD *)v139 = &v157;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v139);
      }
      v37 = 155;
      goto LABEL_42;
    }
  }
  v18 = v146;
LABEL_46:
  Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v135);
  v134 = (unsigned int *)*((_QWORD *)this + 9);
  v39 = WcpCreateTransaction(&v137, *((_QWORD *)this + 11), 4, *v21);
  v24 = v39;
  if ( v39 < 0 )
  {
    v157 = v39;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create CSI transaction for executing.");
      *(_QWORD *)v139 = &v157;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v139);
    }
    v40 = 172;
LABEL_50:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v40,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectinstall.cpp",
      (const char *)(unsigned int)v24,
      (int)v134);
    goto LABEL_51;
  }
  v41 = DoqInitialize(*v21);
  v24 = v41;
  if ( v41 < 0 )
  {
    v157 = v41;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed initializing driver operation queue");
      *(_QWORD *)v139 = &v157;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v139);
    }
    v40 = 175;
    goto LABEL_50;
  }
  *(_QWORD *)v139 = DoqCountDriverOperations(0, 0);
  v43 = CCbsExecutionObject::PrepareExecution((_DWORD)this, v42, (_DWORD)v135, v143, (__int64)&v159, v18);
  v24 = v43;
  if ( v43 < 0 )
  {
    v157 = v43;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to prepare execution");
      *(_QWORD *)v139 = &v157;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v139);
    }
    v40 = 186;
    goto LABEL_50;
  }
  if ( !*((_DWORD *)*v21 + 363) )
  {
    LogAdapter::TraceAtLevel<>(1, "Plan: Start to process component watchlist");
    v44 = CCbsExecutionObject::ProcessComponentWatchList(this, v18);
    v24 = v44;
    if ( v44 < 0 )
    {
      v157 = v44;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to process component watch list.");
        *(_QWORD *)v139 = &v157;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v139);
      }
      v40 = 201;
      goto LABEL_50;
    }
  }
  if ( (*((_DWORD *)*v21 + 173) & 0x80000) != 0 )
  {
    v45 = *((_QWORD *)*v21 + 307);
    if ( v45 )
    {
      v46 = *(_QWORD **)(v45 + 88);
      v47 = &v46[*(_QWORD *)(v45 + 72)];
      while ( 1 )
      {
        if ( v46 == v47 )
        {
          v19 = v141;
          v16 = v152;
          goto LABEL_73;
        }
        v24 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v18 + 72LL))(v18, *v46);
        if ( v24 < 0 )
          break;
        ++v46;
      }
      v157 = v24;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set cim payload source for CIM based update.");
        *(_QWORD *)v139 = &v157;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v139);
      }
      v40 = 209;
      goto LABEL_50;
    }
  }
LABEL_73:
  v48 = *((_DWORD *)*v21 + 173);
  if ( (v48 & 0x400) != 0 || (v48 & 0x80000) != 0 )
  {
    v49 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 80LL))(v18);
    v24 = v49;
    if ( v49 < 0 )
    {
      v157 = v49;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"finalizing changes using turbostack failed");
        *(_QWORD *)v139 = &v157;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v139);
      }
      v40 = 216;
      goto LABEL_50;
    }
  }
  v50 = v159;
  if ( *((_DWORD *)this + 14) && (v159 & 1) != 0 )
  {
    LogAdapter::TraceAtLevel<>(
      1,
      "Exec: package or update requires restart but ignoring because it is being removed by deep clean, which means it was superseded");
    v50 &= ~1u;
    v159 = v50;
  }
  v51 = DoqCountDriverOperations(0, 0);
  *v148 = v51;
  if ( !*((_DWORD *)this + 14) && (v51 || (v50 & 1) != 0) )
    SetRebootReason(*v21);
  v52 = v50 & 1;
  v157 = v52;
  if ( v52 )
  {
    if ( !*((_DWORD *)this + 14) )
    {
      ShouldTheExecutionSmartPended = CCbsExecutionObject::ShouldTheExecutionSmartPended(this, 0);
      *((_DWORD *)this + 13) = ShouldTheExecutionSmartPended;
      if ( ShouldTheExecutionSmartPended || *((_BYTE *)*v21 + 2272) )
      {
        LogAdapter::TraceAtLevel<>(1, "Exec: package or update requires restart, delay the execution to shutdown.");
        *v19 = 1;
        RequireShutdownProcessing(1);
        LogAdapter::TraceAtLevel<>(
          1,
          "Exec: The Package or one of its Updates required and client specified DelayExecutionIfPendRequired, Execution "
          "will be delayed to system shutdown time.");
        SetServicingInProgress(*v21);
        PackageStoreCleanupCachedApplicabilityEvaluationPackage(*v21, v54);
LABEL_94:
        Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v161);
        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v158);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v137);
        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v135);
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        return 0;
      }
    }
  }
  if ( *(_QWORD *)(v143 + 24) )
  {
    PackageStoreWriteTimeStamp(*v21, L"LastModified_UTC");
    PackageStoreCleanupCachedApplicabilityEvaluationPackage(*v21, v55);
    PackageStoreMaintenanceActionSet(*v21, 2u, 0);
    PackageStoreMaintenanceActionSet(*v21, 0xFFFFu, 0);
  }
  v138 = (unsigned int)CCbsSession::IsOffline(*v21) || !*((_DWORD *)this + 24) && !v52;
  IsOffline = CCbsSession::IsOffline(*v21);
  v57 = v136;
  if ( IsOffline && v136 && *((_DWORD *)this + 24) )
  {
    v157 = -2146498554;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"CBS already has pended content.");
      *(_QWORD *)v139 = &v157;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v139);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14B,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectinstall.cpp",
      (const char *)0x800F0806LL,
      (int)v134);
    Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v161);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v158);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v137);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v135);
    if ( !v18 )
      return 2148468742LL;
    goto LABEL_349;
  }
  if ( !(unsigned int)CCbsSession::IsOffline(*v21) )
    goto LABEL_151;
  if ( *((_QWORD *)this + 76) )
  {
    v62 = v147;
    *(_QWORD *)v16 = *((_QWORD *)this + 75);
    *(_QWORD *)v62 = *((_QWORD *)this + 76);
    v63 = CCbsOSVersionPublisher::SetOsVersions((CCbsOSVersionPublisher *)v142, v16, v62, 0);
    v24 = v63;
    if ( v63 < 0 )
    {
      v157 = v63;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed setting new OS versions");
        *(_QWORD *)v139 = &v157;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v139);
      }
      v40 = 356;
      goto LABEL_50;
    }
  }
  else
  {
    CCbsOSVersionPublisher::GetOsVersions((CCbsOSVersionPublisher *)v142, v16, v147);
  }
  if ( !*((_DWORD *)this + 14) || v57 )
  {
    if ( v158 )
    {
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x18018487DLL);
    }
    v58 = 16 * v57;
    v59 = TransactionAnalyze(v135, v58, &GUID_7a8b78de_d107_46ca_812b_8e3f1c163270, &v158);
    v60 = v59;
    if ( v58 )
    {
      if ( v59 < 0 )
      {
        v157 = v59;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Analysis indicated that installation cannot succeed without pending.");
          *(_QWORD *)v139 = &v157;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v139);
        }
        v61 = 383;
LABEL_130:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v61,
          (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectinstall.cpp",
          (const char *)v60,
          (int)v134);
        Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v161);
        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v158);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v137);
        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v135);
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        return v60;
      }
    }
    else if ( v59 < 0 )
    {
      v157 = v59;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get analysis of transaction.");
        *(_QWORD *)v139 = &v157;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v139);
      }
      v61 = 387;
      goto LABEL_130;
    }
    v64 = v151;
    if ( !*((_DWORD *)this + 14) )
    {
      TransformersFromAnalysis = CCbsExecutionSpecialTransformers::GetTransformersFromAnalysis(
                                   v151,
                                   (struct ICSITransactionAnalysis *)v158);
      v24 = TransformersFromAnalysis;
      if ( TransformersFromAnalysis < 0 )
      {
        v157 = TransformersFromAnalysis;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting special transformers");
          *(_QWORD *)v139 = &v157;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v139);
        }
        v40 = 394;
        goto LABEL_50;
      }
      v66 = CCbsExecutionSpecialTransformers::Save(v64, v16, v147);
      v24 = v66;
      if ( v66 < 0 )
      {
        v157 = v66;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed saving special transformers");
          *(_QWORD *)v139 = &v157;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v139);
        }
        v40 = 398;
        goto LABEL_50;
      }
    }
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v158);
    if ( (unsigned int)CCbsExecutionSpecialTransformers::IsInstall(v64) )
    {
      v67 = CCbsOSVersionPublisher::SetOsVersions((CCbsOSVersionPublisher *)v142, 0, 0, v147);
      v24 = v67;
      if ( v67 < 0 )
      {
        v157 = v67;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed setting pnp target OS override");
          *(_QWORD *)v139 = &v157;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v139);
        }
        v40 = 421;
        goto LABEL_50;
      }
      v68 = CCbsExecutionSpecialTransformers::ExecutePhase(v64, 0, v145);
      v24 = v68;
      if ( v68 < 0 )
      {
        v157 = v68;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed executing special install transformers");
          v145 = &v157;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v145);
        }
        v40 = 430;
        goto LABEL_50;
      }
    }
  }
  else
  {
LABEL_151:
    v64 = v151;
  }
  v69 = 0;
  if ( *v148 && v138 )
  {
    if ( !(unsigned int)CCbsSession::IsOffline(*v21) )
      SetExecuteState(0x10000u);
    v70 = DoqSave(*v21);
    v24 = v70;
    if ( v70 < 0 )
    {
      v157 = v70;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed saving driver operation queue");
        v145 = &v157;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v145);
      }
      v40 = 448;
      goto LABEL_50;
    }
    if ( (*((_DWORD *)*v21 + 173) & 0x4000) != 0 && (unsigned int)CCbsSession::IsOffline(*v21) )
    {
      SetExecuteState(0);
    }
    else
    {
      v71 = lpExistingFileName;
      v72 = v149;
      *v153 = 1;
      v134 = 0;
      v24 = DoqExecuteImmediate::Execute(v72, *(unsigned int *)v71, *v21, 0);
      if ( v24 < 0 )
      {
        if ( (unsigned int)CCbsSession::IsOffline(*v21) )
          TryToMarkImageAsNotServiceable(v73);
        v74 = "Doqe: Failed while processing driver operations queue interactively.";
        goto LABEL_167;
      }
      LogAdapter::TraceAtLevel<>(1, "Doqe: Driver operations completed successfully.");
      if ( (unsigned int)CCbsSession::IsOffline(*v21) )
      {
        v75 = "Doqe: Driver operations completed successfully.";
      }
      else
      {
        v69 = dword_1803B40DC;
        v75 = "Doqe: interactive driver operations completed.";
        if ( dword_1803B40DC )
          v75 = "Doqe: interactive driver operations completed but required a reboot.";
      }
      LogAdapter::TraceAtLevel<>(1, v75);
    }
  }
  if ( *((_QWORD *)v64 + 3) && !(unsigned int)CCbsExecutionSpecialTransformers::IsInstall(v64) )
  {
    v76 = CCbsOSVersionPublisher::SetOsVersions((CCbsOSVersionPublisher *)v142, 0, 0, v147);
    v24 = v76;
    if ( v76 < 0 )
    {
      v157 = v76;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed setting pnp target OS override");
        v145 = &v157;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v145);
      }
      v40 = 513;
      goto LABEL_50;
    }
    v77 = CCbsExecutionSpecialTransformers::ExecutePhase(v64, 1u, v150);
    v24 = v77;
    if ( v77 < 0 )
    {
      v157 = v77;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed executing special install transformers");
        v150 = &v157;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v150);
      }
      v40 = 522;
      goto LABEL_50;
    }
  }
  v78 = 0;
  if ( v138 )
  {
    if ( !*(_QWORD *)(v143 + 24) )
    {
      LogAdapter::TraceAtLevel<>(1, "Exec: Skipping transaction commit since nothing was changed.");
LABEL_186:
      v79 = CCbsSession::SaveCurrentBuildNumbers(*v21);
      v24 = v79;
      if ( v79 < 0 )
      {
        v157 = v79;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed setting current build numbers");
          *(_QWORD *)v140 = &v157;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v140);
        }
        v40 = 731;
        goto LABEL_50;
      }
      if ( (int)CCbsSession::InvalidateWinnersPreload(*v21) < 0 )
        LogAdapter::TraceAtLevel<>(1, "Unable to invalidate for winners preload.");
      if ( (int)CCbsSession::InvalidateBaselinesPreload(*v21) < 0 )
        LogAdapter::TraceAtLevel<>(1, "Unable to invalidate for baselines preload.");
      goto LABEL_239;
    }
    if ( (unsigned int)CCbsSession::IsOffline(*v21) )
    {
      if ( v136 )
      {
        v81 = 1120;
      }
      else
      {
        v81 = 96;
        if ( (*((_DWORD *)v80 + 173) & 0x4000) != 0 )
          v81 = 97;
      }
      v82 = ConfigurePoqexecPendLocation(0, v80);
      LogAdapter::TraceAtLevelIfFailed<long,>(1, v82, "Unable to configure poqexec pend location.");
    }
    else
    {
      v81 = 102;
    }
    v83 = *v21;
    if ( (*((_DWORD *)*v21 + 173) & 0x80000) != 0 )
    {
      CCbsSession::CimSetupCleanup(v83);
      v84 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 88LL))(v18);
      v24 = v84;
      if ( v84 < 0 )
      {
        v157 = v84;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed finalizing pending changes");
          v150 = &v157;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v150);
        }
        v40 = 583;
        goto LABEL_50;
      }
      v160 = 1;
      goto LABEL_186;
    }
    v24 = TransactionCommit(v83, v135, v81, 1, &v160);
    v78 = v160 & 0xFFFF0000;
    v160 = (unsigned __int16)v160;
    if ( v24 >= 0 && *(_QWORD *)v147 && ((unsigned __int16)v160 == 1 || (unsigned __int16)v160 == 13) )
      **(_DWORD **)v140 = 1;
    if ( !(unsigned int)CCbsSession::IsOffline(*v21) && *v148 )
    {
      if ( v24 < 0 || v86 != 5 && v86 > 2 && v86 < 8 )
      {
        LogAdapter::TraceAtLevel<>(
          1,
          "Doqe: primitives did not complete, so rolling back interactive driver operations.");
        v134 = 0;
        v87 = DoqExecuteImmediate::Execute(v149, *(unsigned int *)lpExistingFileName, *v21, 1);
        LogAdapter::TraceAtLevelHr<long,>(3, v87, "Doqe: Failed undoing interactive driver operations.");
        *v153 = 0;
        v85 = *v21;
      }
      if ( (*(_BYTE *)lpExistingFileName & 2) != 0 )
      {
        v88 = DoqExecuteImmediate::Finalize((DoqExecuteImmediate *)v149, v85);
        LogAdapter::TraceAtLevelIfFailed<long,>(1, v88, "Unable to finalize driver installs");
        v85 = *v21;
      }
      if ( !v69 )
        v69 = dword_1803B40DC;
      v89 = DoqClear(v85, 0);
      LogAdapter::TraceAtLevelIfFailed<long,>(1, v89, "Unable to clear the live driver operations key");
    }
    if ( (unsigned int)CCbsSession::IsOffline(*v21) )
    {
      if ( v24 < 0 )
        goto LABEL_227;
      if ( v90 == 6 )
        goto LABEL_223;
      if ( v90 == 8 || v90 == 14 )
LABEL_227:
        TryToMarkImageAsNotServiceable(*v21);
      v91 = (*((_DWORD *)*v21 + 173) & 0x4000) == 0 ? 3 : 0;
    }
    else
    {
      v92 = ClearCurrentBuildNumbers(*v21);
      LogAdapter::TraceAtLevelIfFailed<long,>(3, v92, "Unable to clear current build numbers");
      v91 = -1;
    }
    SetExecuteState(v91);
    if ( v24 >= 0 )
      goto LABEL_186;
    if ( !(unsigned int)CCbsSession::IsOffline(*v21) && v24 == -2146885628 )
    {
      LogAdapter::TraceAtLevelIfFailed<long,>(1, 2148081668LL, "Mismatched catalog, mark store as corrupt.");
      CCbsSession::MarkPackageStoreCorrupt(*v21);
    }
    v74 = "Exec: Failed to commit CSI transaction to execute changes.";
LABEL_167:
    LogAdapter::TraceAtLevelHr<long,>(3, (unsigned int)v24, v74);
    goto LABEL_51;
  }
LABEL_239:
  v93 = v160;
  if ( v160 - 6 <= 2 )
  {
    if ( (v78 & 0x10000) != 0 )
    {
      v128 = "Exec: Transaction failed, and an advanced installer required a reboot.";
    }
    else
    {
      if ( !v69 )
        goto LABEL_356;
      v128 = "Exec: Transaction failed, and interactive drivers required a reboot.";
    }
    LogAdapter::TraceAtLevel<>(1, v128);
    RequireShutdownProcessing(1);
    v93 = v160;
LABEL_356:
    if ( v93 == 7 )
    {
      v129 = SetTrustedInstallerAutoStart(*v21);
      LogAdapter::TraceAtLevelHr<long,>(
        1,
        v129,
        "Exec: Scheduled TrustedInstaller for auto-start because rollback was pended.");
      RequireShutdownProcessing(1);
      v24 = -2147021879;
      LogAdapter::TraceAtLevelHr<long,>(
        3,
        2147945417LL,
        "Exec: An error occurred while committing the transaction and the transaction rollback requires a reboot.");
      Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v161);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v158);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v137);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v135);
      if ( !v18 )
        return (unsigned int)v24;
      goto LABEL_52;
    }
    v130 = *((_QWORD *)this + 11);
    LODWORD(v134) = 0;
    v157 = 0;
    v131 = PackageStoreCancelPendingTransaction(v130, v137, 0, &v157, v134, 0);
    LogAdapter::TraceAtLevelHr<long,>(1, v131, "Exec: Cancelled pending transactions after rollback.");
    DeletePoqexecFromCcpConfig(*v21);
    v132 = ConfigurePoqexecPendLocation(1, *v21);
    LogAdapter::TraceAtLevelIfFailed<long,>(1, v132, "Unable to set flag to pend PoqExec in SetupExecute.");
    if ( v160 != 6 )
    {
      LogAdapter::TraceAtLevelHr<long,>(
        3,
        2148469026LL,
        "Exec: An error occurred while committing the transaction, the transaction could not be rolled back.");
      Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v161);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v158);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v137);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v135);
      if ( v18 )
LABEL_361:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      return 2148469026LL;
    }
LABEL_223:
    LogAdapter::TraceAtLevelHr<long,>(
      3,
      2148469026LL,
      "Exec: An error occurred while committing the transaction, the transaction has been rolled back.");
    Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v161);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v158);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v137);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v135);
    if ( v18 )
      goto LABEL_361;
    return 2148469026LL;
  }
  if ( (unsigned int)CCbsSession::IsOffline(*v21) )
  {
    if ( CCbsSession::IsOfflineUnitTestMode(v94) && (*(_BYTE *)(v96 + 688) & 0x40) != 0
      || (*(_DWORD *)(v96 + 692) & 0x4000) != 0 )
    {
      v98 = v141;
      *v141 = 1;
      goto LABEL_264;
    }
    if ( v97 != 1 )
    {
      v104 = *((_DWORD *)this + 24) || *(_QWORD *)(v143 + 24);
      v98 = v141;
      *v141 = v104;
LABEL_264:
      if ( !*((_QWORD *)*v21 + 182) )
      {
        v105 = SetTrustedInstallerAutoStart(*v21);
        LogAdapter::TraceAtLevelHr<long,>(
          1,
          v105,
          "Exec: Pended transaction, changes will be applied during startup processing. Scheduled TrustedInstaller for auto-start.");
      }
      goto LABEL_266;
    }
    LogAdapter::TraceAtLevel<>(1, "Exec: Offline commit completes with no pending online operations.");
    *v154 = 1;
    if ( *((_DWORD *)this + 24) )
      LogAdapter::TraceAtLevel<>(
        1,
        "Exec: Although the offline commit completed immediately, CBS has to consider it pended due to a previous operation.");
    v99 = *((_DWORD *)this + 24);
    v98 = v141;
    v142 = 0;
    lpExistingFileName = 0;
    *v141 = v99;
    OfflineWindowsDirectory = CCbsSession::GetOfflineWindowsDirectory(*v21, &v142);
    if ( OfflineWindowsDirectory >= 0 )
    {
      OfflineWindowsDirectory = SczAllocConcat2Sz(&lpExistingFileName, v142, L"Servicing\\cbs_pbr_package_list.txt");
      if ( OfflineWindowsDirectory >= 0 )
      {
        v102 = lpExistingFileName;
        if ( (unsigned int)DoesFileExist(lpExistingFileName, 0) )
        {
          v103 = CbsSetAttrAndDeleteFile(v102);
          *(_QWORD *)v140 = v102;
          if ( v103 >= 0 )
          {
            if ( LogAdapter::g_Logger )
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                1,
                1,
                (__int64)"Exec: Removed package list file from {}",
                (__int64)v140);
          }
          else
          {
            LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
              1,
              (unsigned int)v103,
              "Unable to remove package list file: {}",
              v140);
          }
        }
        goto LABEL_258;
      }
      v101 = "Unable to allocate package list path";
    }
    else
    {
      v101 = "Unable to get offline boot directory";
    }
    LogAdapter::TraceAtLevelIfFailed<long,>(1, (unsigned int)OfflineWindowsDirectory, v101);
LABEL_258:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v142);
    goto LABEL_264;
  }
  if ( !*((_DWORD *)this + 24) && !v157 && (unsigned int)(v95 - 3) > 1 )
  {
    *v154 = 1;
    if ( (v78 & 0x10000) != 0 )
    {
      LogAdapter::TraceAtLevel<>(1, "Exec: Advanced installer executed successfully but still required a reboot.");
      v98 = v141;
      *v141 = 1;
      if ( !*((_DWORD *)*v21 + 317) )
        *((_DWORD *)*v21 + 317) = 9;
      v107 = SetTrustedInstallerAutoStart(*v21);
      v108 = "Exec: Scheduled TrustedInstaller for auto-start because we pended the transaction.";
    }
    else
    {
      if ( !v69 )
      {
        v98 = v141;
        goto LABEL_288;
      }
      LogAdapter::TraceAtLevel<>(1, "Exec: Interactive drivers executed successfully but still required a reboot.");
      v98 = v141;
      *v141 = 1;
      if ( !*((_DWORD *)*v21 + 317) )
        *((_DWORD *)*v21 + 317) = 11;
      SetRebootReason(*v21);
      v107 = SetTrustedInstallerAutoStart(*v21);
      v108 = "Exec: Scheduled TrustedInstaller for auto-start because interactive drivers required a reboot.";
    }
    LogAdapter::TraceAtLevelHr<long,>(1, v107, v108);
    RequireShutdownProcessing(1);
LABEL_288:
    if ( *v98 )
      SetServicingInProgress(*v21);
    v106 = v159;
    if ( (v159 & 2) != 0 && !*((_DWORD *)this + 14) )
      *((_DWORD *)this + 124) = 1;
    goto LABEL_267;
  }
  v109 = CCbsExecutionObject::ShouldTheExecutionSmartPended(this, 0);
  v110 = v109;
  if ( v157 )
  {
    if ( v109 )
    {
      RequireShutdownProcessing(1);
      v111 = "Exec: The Package or one of its Updates required and client specified DelayExecutionIfPendRequired, Executi"
             "on will be delayed to system shutdown time.";
    }
    else
    {
      v111 = "Exec: The Package or one of its Updates required a reboot so transaction commit was skipped, Package's chan"
             "ges need to be pended.";
    }
  }
  else
  {
    if ( v109 )
    {
      LogAdapter::TraceAtLevel<>(
        1,
        "Exec: Failed to commit CSI transaction due to file in use or Component reboot required and client specified Dela"
        "yExecutionIfPendRequired, Execution will be delayed to system shutdown time.");
      RequireShutdownProcessing(1);
      goto LABEL_301;
    }
    v111 = "Exec: Failed to commit CSI transaction due to file in use or Component reboot required, package changes need to be pended.";
  }
  LogAdapter::TraceAtLevel<>(1, v111);
LABEL_301:
  if ( !*((_DWORD *)this + 10) )
  {
    LogAdapter::TraceAtLevel<>(1, "Exec: Client did not specify to pend if necessary, no changes have been applied.");
    Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v161);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v158);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v137);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v135);
    if ( !v18 )
      return 2148468742LL;
LABEL_349:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    return 2148468742LL;
  }
  if ( !v110 )
  {
    v112 = DoqSave(*v21);
    v24 = v112;
    if ( v112 < 0 )
    {
      v157 = v112;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed saving driver operation queue");
        *(_QWORD *)v140 = &v157;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v140);
      }
      v40 = 1014;
      goto LABEL_50;
    }
    if ( !*(_QWORD *)(v143 + 24) )
    {
      LogAdapter::TraceAtLevel<>(1, "Exec: Skipping transaction pend since nothing was changed.");
      v113 = v148;
      goto LABEL_309;
    }
    SetExecuteState(0x14u);
    v113 = v148;
    v115 = ConfigurePoqexecPendLocation(*v148 == 0, *v21);
    LogAdapter::TraceAtLevelIfFailed<long,>(1, v115, "Unable to configure poqexec pend location.");
    v116 = *v21;
    if ( (*((_DWORD *)*v21 + 173) & 0x80000) != 0 )
    {
      CCbsSession::CimSetupCleanup(v116);
      goto LABEL_309;
    }
    v24 = TransactionCommit(v116, v135, 0x2Fu, 1, &v160);
    if ( v24 >= 0 )
    {
LABEL_309:
      if ( (*((_DWORD *)*v21 + 173) & 0x80000) != 0 )
      {
        v114 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 88LL))(v18);
        v24 = v114;
        if ( v114 < 0 )
        {
          v157 = v114;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed finalizing pending changes");
            *(_QWORD *)v140 = &v157;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v140);
          }
          v40 = 1084;
          goto LABEL_50;
        }
      }
      v120 = CCbsSession::SaveCurrentBuildNumbers(*v21);
      v24 = v120;
      if ( v120 < 0 )
      {
        v157 = v120;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed setting current build numbers");
          *(_QWORD *)v140 = &v157;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v140);
        }
        v40 = 1087;
        goto LABEL_50;
      }
      v121 = *v113 == 0;
      v98 = v141;
      *((_DWORD *)this + 26) = v121;
      *v98 = 1;
      LogAdapter::TraceAtLevel<>(
        1,
        "Exec: Pended transaction, changes will be applied during shutdown/startup processing.");
      v122 = SetTrustedInstallerAutoStart(*v21);
      LogAdapter::TraceAtLevelHr<long,>(
        1,
        v122,
        "Exec: Scheduled TrustedInstaller for auto-start because we pended the transaction.");
      if ( (*((_DWORD *)*v21 + 173) & 0x80000) != 0 )
        LogAdapter::TraceAtLevel<>(1, "Exec: Skipping shutdown processing as it is using CIM based update flow.");
      else
        RequireShutdownProcessing(1);
      goto LABEL_328;
    }
    if ( !*(_QWORD *)v139 )
    {
      v117 = ConfigurePoqexecPendLocation(1, *v21);
      LogAdapter::TraceAtLevelIfFailed<long,>(1, v117, "Unable to configure poqexec pend location.");
    }
    LogAdapter::TraceAtLevel<>(1, "Exec: Restoring driver operations because of a CSI commit failure.");
    v118 = DoqUndoSave(*v21);
    LogAdapter::TraceAtLevelIfFailed<long,>(1, v118, "Exec: Failed restoring driver operations queue");
    SetExecuteState(0xFFFFFFFF);
    LogAdapter::TraceAtLevelHr<long,unsigned long>(
      v119,
      (unsigned int)v24,
      "Exec: Failed to pend CSI transaction because transactions cannot be merged: {}.",
      &v160);
LABEL_51:
    Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v161);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v158);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v137);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v135);
    if ( !v18 )
      return (unsigned int)v24;
LABEL_52:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    return (unsigned int)v24;
  }
  v98 = v141;
  *((_DWORD *)this + 13) = 1;
  *v98 = 1;
LABEL_328:
  SetServicingInProgress(*v21);
LABEL_266:
  v106 = v159;
LABEL_267:
  if ( !*((_DWORD *)this + 24) )
    goto LABEL_367;
  if ( *v98 )
    goto LABEL_334;
  if ( !*(_QWORD *)(v143 + 24) )
  {
LABEL_367:
    if ( !*v98 )
    {
      v123 = DoqExecuteImmediate::NotifyVersionChange(v149, *v21);
      v24 = v123;
      if ( v123 < 0 )
      {
        v157 = v123;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to notify PNP of possible OS version change.");
          *(_QWORD *)v140 = &v157;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v140);
        }
        v40 = 1178;
        goto LABEL_50;
      }
    }
LABEL_334:
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v135);
    if ( *((_DWORD *)*v21 + 367) )
    {
      v124 = 1;
      v125 = "Exec: Scavenge on completion requested by session.";
    }
    else if ( (unsigned int)CCbsSession::IsOffline(*v21) && (v106 & 4) != 0 && !*((_DWORD *)this + 14) )
    {
      v124 = 1;
      v125 = "Exec: Scavenge for offline operation requiring cleanup requested.";
    }
    else
    {
      v124 = 0;
      v125 = "Exec: Scavenge not requested.";
    }
    LogAdapter::TraceAtLevel<>(1, v125);
    if ( !v124 )
      goto LABEL_94;
    if ( (*((_DWORD *)*v21 + 173) & 0x20000) != 0 )
    {
      v126 = "Exec: Scavenge not allowed by session request.";
    }
    else
    {
      if ( !*v98 )
      {
        DoqExecuteImmediate::Close((DoqExecuteImmediate *)v149);
        v127 = PackageStoreCsiScavenge(*v21, 0, 0, 0, 0, 0, 0, 0, 0);
        LogAdapter::TraceAtLevelIfFailed<long,>(2, v127, "Scavenge: Unable to scavenge offline store immediately");
        goto LABEL_94;
      }
      v126 = "Exec: Scavenge not allowed due to pended transaction.";
    }
    LogAdapter::TraceAtLevel<>(1, v126);
    goto LABEL_94;
  }
  v157 = -2146498560;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"If a transaction was already pending, then we must have pended t"
                                                        "he transaction again.");
    *(_QWORD *)v140 = &v157;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {}",
      (__int64)v140);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x496,
    (unsigned int)"onecore\\base\\cbs\\core\\cbsexecutionobjectinstall.cpp",
    (const char *)0x800F0800LL,
    (int)v134);
  Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v161);
  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v158);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v137);
  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v135);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  return 2148468736LL;
}

```

## disassembly

```asm
0x1801829cc  mov     [rsp-8+arg_8], rbx
0x1801829d1  push    rbp
0x1801829d2  push    rsi
0x1801829d3  push    rdi
0x1801829d4  push    r12
0x1801829d6  push    r13
0x1801829d8  push    r14
0x1801829da  push    r15
0x1801829dc  lea     rbp, [rsp-50h]
0x1801829e1  sub     rsp, 150h
0x1801829e8  mov     rax, cs:__security_cookie
0x1801829ef  xor     rax, rsp
0x1801829f2  mov     [rbp+80h+var_38], rax
0x1801829f6  mov     rax, [rbp+80h+arg_68]
0x1801829fd  lea     rdx, aPerfExecuteCha; "Perf: Execute chain started."
0x180182a04  mov     r12, [rbp+80h+arg_50]
0x180182a0b  xor     esi, esi
0x180182a0d  mov     rdi, [rbp+80h+arg_48]
0x180182a14  mov     r13, rcx
0x180182a17  mov     [rbp+80h+var_A8], rax
0x180182a1b  mov     ebx, esi
0x180182a1d  mov     rax, [rbp+80h+arg_58]
0x180182a24  mov     r15, r8
0x180182a27  mov     [rbp+80h+var_C8], rax
0x180182a2b  lea     ecx, [rsi+1]
0x180182a2e  mov     rax, [rbp+80h+arg_20]
0x180182a35  mov     [rbp+80h+var_B0], rax
0x180182a39  mov     rax, [rbp+80h+arg_28]
0x180182a40  mov     qword ptr [rbp+80h+var_100], rax
0x180182a44  mov     rax, [rbp+80h+arg_30]
0x180182a4b  mov     [rbp+80h+var_90], rax
0x180182a4f  mov     rax, [rbp+80h+arg_38]
0x180182a56  mov     [rbp+80h+var_98], rax
0x180182a5a  mov     rax, [rbp+80h+arg_40]
0x180182a61  mov     [rbp+80h+var_C0], rax
0x180182a65  mov     rax, [rbp+80h+arg_60]
0x180182a6c  mov     [rbp+80h+var_F0], rax
0x180182a70  mov     rax, [rbp+80h+arg_70]
0x180182a77  mov     [rbp+80h+var_B8], rax
0x180182a7b  mov     rax, [rbp+80h+arg_78]
0x180182a82  mov     [rbp+80h+var_E8], rax
0x180182a86  mov     [rbp+80h+var_D8], r9
0x180182a8a  mov     [rbp+80h+var_F8], r8
0x180182a8e  mov     [rbp+80h+var_A0], r12
0x180182a92  mov     [rbp+80h+lpExistingFileName], rdi
0x180182a96  mov     [rbp+80h+var_D0], rbx
0x180182a9a  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x180182a9f  movups  xmm0, cs:CbsInstallUninstallStartEvent
0x180182aa6  lea     rdx, aPerfExecuteCha_0; "Perf: Execute chain started."
0x180182aad  lea     rcx, [rsp+180h+var_110]
0x180182ab2  movdqu  xmmword ptr [rsp+180h+var_110], xmm0
0x180182ab8  call    CbsGenericEventReport
0x180182abd  lea     r14, [r13+40h]
0x180182ac1  mov     [rsp+180h+var_130], rsi
0x180182ac6  mov     [rsp+180h+var_120], rsi
0x180182acb  mov     [rbp+80h+var_64], esi
0x180182ace  mov     [rbp+80h+var_68], esi
0x180182ad1  mov     [rbp+80h+var_70], rsi
0x180182ad5  cmp     [r13+28h], esi
0x180182ad9  jnz     short loc_180182AEF
0x180182adb  mov     rax, [r14]
0x180182ade  mov     [rsp+180h+var_128], 1
0x180182ae3  test    dword ptr [rax+2B4h], 4000h
0x180182aed  jz      short loc_180182AF4
0x180182aef  mov     [rsp+180h+var_128], sil
0x180182af4  mov     rdx, [r14]
0x180182af7  lea     rcx, [rbp+80h+var_60]; this
0x180182afb  add     rdx, 130h; struct Windows::Rtl::StopWatch *
0x180182b02  call    ??0StopWatch@Rtl@Windows@@QEAA@PEAV012@K@Z; Windows::Rtl::StopWatch::StopWatch(Windows::Rtl::StopWatch *,ulong)
0x180182b07  cmp     [r13+38h], esi
0x180182b0b  jnz     short loc_180182B1F
0x180182b0d  mov     rcx, [r14]; this
0x180182b10  call    ?IsOffline@CCbsSession@@QEBAHXZ; CCbsSession::IsOffline(void)
0x180182b15  test    eax, eax
0x180182b17  jnz     short loc_180182B1F
0x180182b19  mov     dword ptr [rdi], 7
0x180182b1f  xor     r8d, r8d
0x180182b22  mov     rcx, r13
0x180182b25  lea     edx, [r8+0Fh]
0x180182b29  call    ?SetPendingStateforDelayedExecutedPackages@CCbsExecutionObject@@AEAAJW4CbsStoreObjectType@@H@Z; CCbsExecutionObject::SetPendingStateforDelayedExecutedPackages(CbsStoreObjectType,int)
0x180182b2e  mov     edi, eax
0x180182b30  test    eax, eax
0x180182b32  jns     short loc_180182B8C
0x180182b34  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182b3b  mov     [rbp+80h+var_78], eax
0x180182b3e  test    rcx, rcx
0x180182b41  jz      short loc_180182B82
0x180182b43  mov     esi, 3
0x180182b48  lea     r9, aFailedSettingP_3; "Failed setting pending state."
0x180182b4f  mov     r8d, esi
0x180182b52  xor     edx, edx
0x180182b54  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180182b59  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182b60  lea     rax, [rbp+80h+var_78]
0x180182b64  mov     [rbp+80h+var_88], rax
0x180182b68  lea     r9, asc_1802EE7AC; ": {}"
0x180182b6f  lea     rax, [rbp+80h+var_88]
0x180182b73  mov     r8d, esi
0x180182b76  mov     dl, 1
0x180182b78  mov     [rsp+180h+var_160], rax
0x180182b7d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180182b82  mov     edx, 4Ch ; 'L'
0x180182b87  jmp     loc_180182C23
0x180182b8c  mov     rcx, [r14]; this
0x180182b8f  xor     edx, edx
0x180182b91  call    SetRebootReason
0x180182b96  mov     r11, [r13+18h]
0x180182b9a  test    r11, r11
0x180182b9d  jz      loc_180182C3E
0x180182ba3  mov     rcx, r13; this
0x180182ba6  call    ?GetProgressCost@CCbsExecutionObject@@AEAAKXZ; CCbsExecutionObject::GetProgressCost(void)
0x180182bab  mov     rdx, [r11]
0x180182bae  mov     r9d, 1
0x180182bb4  mov     r8d, eax
0x180182bb7  mov     rcx, r11
0x180182bba  mov     r10, [rdx+20h]
0x180182bbe  lea     edx, [r9+31h]
0x180182bc2  mov     rax, r10
0x180182bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180182bca  mov     edi, eax
0x180182bcc  test    eax, eax
0x180182bce  jns     short loc_180182C3E
0x180182bd0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182bd7  mov     [rbp+80h+var_68], eax
0x180182bda  test    rcx, rcx
0x180182bdd  jz      short loc_180182C1E
0x180182bdf  mov     esi, 3
0x180182be4  lea     r9, aExecClientCanc; "Exec: Client cancelled"
0x180182beb  mov     r8d, esi
0x180182bee  xor     edx, edx
0x180182bf0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180182bf5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182bfc  lea     rax, [rbp+80h+var_68]
0x180182c00  mov     qword ptr [rbp+80h+var_80], rax
0x180182c04  lea     r9, asc_1802EE7AC; ": {}"
0x180182c0b  lea     rax, [rbp+80h+var_80]
0x180182c0f  mov     r8d, esi
0x180182c12  mov     dl, 1
0x180182c14  mov     [rsp+180h+var_160], rax; int
0x180182c19  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180182c1e  mov     edx, 5Bh ; '['; void *
0x180182c23  mov     rcx, [rbp+88h]; this
0x180182c2a  lea     r8, aOnecoreBaseCbs_38; "onecore\\base\\cbs\\core\\cbsexecutiono"...
0x180182c31  mov     r9d, edi; char *
0x180182c34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180182c39  jmp     loc_180182D45
0x180182c3e  cmp     [r13+60h], esi
0x180182c42  jz      short loc_180182C51
0x180182c44  mov     rcx, [r14]; this
0x180182c47  mov     edx, 9
0x180182c4c  call    SetRebootReason
0x180182c51  mov     rax, [r14]
0x180182c54  test    byte ptr [rax+2B0h], 40h
0x180182c5b  jz      short loc_180182CA8
0x180182c5d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182c64  mov     rax, [rax+280h]
0x180182c6b  mov     qword ptr [rsp+180h+var_110], rax
0x180182c70  test    rcx, rcx
0x180182c73  jz      short loc_180182C94
0x180182c75  mov     r8d, 1
0x180182c7b  lea     rax, [rsp+180h+var_110]
0x180182c80  mov     dl, r8b
0x180182c83  mov     [rsp+180h+var_160], rax
0x180182c88  lea     r9, aExecClientForc; "Exec: Client forces reboot on session: "...
0x180182c8f  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180182c94  mov     rcx, [r14]; this
0x180182c97  mov     edx, 5
0x180182c9c  mov     [rbp+80h+var_68], 1
0x180182ca3  call    SetRebootReason
0x180182ca8  cmp     [r13+1F8h], esi
0x180182caf  jnz     loc_180182D72
0x180182cb5  lea     rdx, [rbp+80h+var_78]; int *
0x180182cb9  mov     [rbp+80h+var_78], esi
0x180182cbc  mov     rcx, r13; this
0x180182cbf  call    ?IsTaskPackageAlreadySmartPended@CCbsExecutionObject@@QEAAJPEAH@Z; CCbsExecutionObject::IsTaskPackageAlreadySmartPended(int *)
0x180182cc4  mov     edi, eax
0x180182cc6  test    eax, eax
0x180182cc8  jns     short loc_180182D24
0x180182cca  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182cd1  mov     [rbp+80h+var_78], eax
0x180182cd4  test    rcx, rcx
0x180182cd7  jz      short loc_180182D1A
0x180182cd9  mov     esi, 3
0x180182cde  lea     r9, aFailedToCheckW_10; "Failed to check whether package was alr"...
0x180182ce5  mov     r8d, esi
0x180182ce8  xor     edx, edx
0x180182cea  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180182cef  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182cf6  lea     rax, [rbp+80h+var_78]
0x180182cfa  mov     qword ptr [rsp+180h+var_110], rax
0x180182cff  lea     r9, asc_1802EE7AC; ": {}"
0x180182d06  lea     rax, [rsp+180h+var_110]
0x180182d0b  mov     r8d, esi
0x180182d0e  mov     dl, 1
0x180182d10  mov     [rsp+180h+var_160], rax
0x180182d15  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180182d1a  mov     edx, 7Dh ; '}'
0x180182d1f  jmp     loc_180182C23
0x180182d24  cmp     [rbp+80h+var_78], esi
0x180182d27  jz      short loc_180182D72
0x180182d29  mov     ebx, 1
0x180182d2e  lea     rdx, aExecTaskPackag; "Exec: Task package already smart pended"...
0x180182d35  mov     ecx, ebx
0x180182d37  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x180182d3c  mov     [r13+34h], ebx
0x180182d40  mov     edi, esi
0x180182d42  mov     [r15], ebx
0x180182d45  lea     rcx, [rbp+80h+var_60]; this
0x180182d49  call    ??1StopWatch@Rtl@Windows@@QEAA@XZ; Windows::Rtl::StopWatch::~StopWatch(void)
0x180182d4e  lea     rcx, [rbp+80h+var_70]
0x180182d52  call    ?Close@?$AutoComPtr@UIEnumCSI_PENDING_TRANSACTION@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(void)
0x180182d57  lea     rcx, [rsp+180h+var_120]
0x180182d5c  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x180182d61  lea     rcx, [rsp+180h+var_130]
0x180182d66  call    ?Close@?$AutoComPtr@UIEnumCSI_PENDING_TRANSACTION@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(void)
0x180182d6b  mov     eax, edi
0x180182d6d  jmp     loc_18018484B
0x180182d72  mov     rcx, [r14]
0x180182d75  mov     esi, 3
0x180182d7a  mov     eax, [rcx+2B4h]
0x180182d80  bt      eax, 13h
0x180182d84  jnb     short loc_180182DEE
0x180182d86  lea     r9, [rbp+80h+var_D0]
0x180182d8a  lea     edx, [rsi-1]
0x180182d8d  call    ?CreateServicingCommitter@CCbsSession@@QEAAJW4InitializeScenario@IServicingCommitter@@PEAUICSIStore@@PEAV?$AutoComPtr@VIServicingCommitter@@@Windows@@@Z; CCbsSession::CreateServicingCommitter(IServicingCommitter::InitializeScenario,ICSIStore *,Windows::AutoComPtr<IServicingCommitter> *)
0x180182d92  mov     ebx, eax
0x180182d94  test    eax, eax
0x180182d96  jns     loc_180182EB5
0x180182d9c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182da3  mov     [rbp+80h+var_78], eax
0x180182da6  test    rcx, rcx
0x180182da9  jz      short loc_180182DE7
0x180182dab  lea     r9, aFailedCreating_6; "Failed creating committer for CIM based"...
0x180182db2  mov     r8d, esi
0x180182db5  xor     edx, edx
0x180182db7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180182dbc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182dc3  lea     rax, [rbp+80h+var_78]
0x180182dc7  mov     qword ptr [rsp+180h+var_110], rax
0x180182dcc  lea     r9, asc_1802EE7AC; ": {}"
0x180182dd3  lea     rax, [rsp+180h+var_110]
0x180182dd8  mov     r8d, esi
0x180182ddb  mov     dl, 1
0x180182ddd  mov     [rsp+180h+var_160], rax
0x180182de2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180182de7  mov     edx, 92h
0x180182dec  jmp     short loc_180182E5D
0x180182dee  bt      eax, 0Ah
0x180182df2  jnb     loc_180182EB9
0x180182df8  lea     r9, [rbp+80h+var_D0]
0x180182dfc  mov     edx, esi
0x180182dfe  call    ?CreateServicingCommitter@CCbsSession@@QEAAJW4InitializeScenario@IServicingCommitter@@PEAUICSIStore@@PEAV?$AutoComPtr@VIServicingCommitter@@@Windows@@@Z; CCbsSession::CreateServicingCommitter(IServicingCommitter::InitializeScenario,ICSIStore *,Windows::AutoComPtr<IServicingCommitter> *)
0x180182e03  mov     ebx, eax
0x180182e05  test    eax, eax
0x180182e07  jns     loc_180182EB5
0x180182e0d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182e14  mov     [rbp+80h+var_78], eax
0x180182e17  test    rcx, rcx
0x180182e1a  jz      short loc_180182E58
0x180182e1c  lea     r9, aFailedCreating_2; "Failed creating committer for Desktop u"...
0x180182e23  mov     r8d, esi
0x180182e26  xor     edx, edx
0x180182e28  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180182e2d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182e34  lea     rax, [rbp+80h+var_78]
0x180182e38  mov     qword ptr [rsp+180h+var_110], rax
0x180182e3d  lea     r9, asc_1802EE7AC; ": {}"
0x180182e44  lea     rax, [rsp+180h+var_110]
0x180182e49  mov     r8d, esi
0x180182e4c  mov     dl, 1
0x180182e4e  mov     [rsp+180h+var_160], rax; int
0x180182e53  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180182e58  mov     edx, 9Bh; void *
0x180182e5d  mov     rcx, [rbp+88h]; this
0x180182e64  lea     r8, aOnecoreBaseCbs_38; "onecore\\base\\cbs\\core\\cbsexecutiono"...
0x180182e6b  mov     r9d, ebx; char *
0x180182e6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180182e73  lea     rcx, [rbp+80h+var_60]; this
0x180182e77  call    ??1StopWatch@Rtl@Windows@@QEAA@XZ; Windows::Rtl::StopWatch::~StopWatch(void)
0x180182e7c  lea     rcx, [rbp+80h+var_70]
0x180182e80  call    ?Close@?$AutoComPtr@UIEnumCSI_PENDING_TRANSACTION@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(void)
0x180182e85  lea     rcx, [rsp+180h+var_120]
0x180182e8a  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x180182e8f  lea     rcx, [rsp+180h+var_130]
0x180182e94  call    ?Close@?$AutoComPtr@UIEnumCSI_PENDING_TRANSACTION@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(void)
0x180182e99  mov     rcx, [rbp+80h+var_D0]
0x180182e9d  test    rcx, rcx
0x180182ea0  jz      short loc_180182EAE
0x180182ea2  mov     rax, [rcx]
0x180182ea5  mov     rax, [rax+10h]
0x180182ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180182eae  mov     eax, ebx
0x180182eb0  jmp     loc_18018484B
0x180182eb5  mov     rbx, [rbp+80h+var_D0]
0x180182eb9  lea     rcx, [rsp+180h+var_130]
0x180182ebe  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x180182ec3  mov     r9, [r14]
0x180182ec6  lea     rcx, [rsp+180h+var_120]
0x180182ecb  mov     rdx, [r13+58h]
0x180182ecf  mov     r8d, 4
  ... truncated ...
```
