# ScanForUpdatesWorker::DoWork(void)

- ea: `0x180016044`
- end: `0x180016645`
- name: `?DoWork@ScanForUpdatesWorker@@QEAAJXZ`
- size: `1537`
- prototype: `__int64 __fastcall(ScanForUpdatesWorker *__hidden this)`
- caller_count: `1`
- callee_count: `36`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800107d0`

## callees

- `0x180003450`
- `0x180003948`
- `0x180005c74`
- `0x18000760c`
- `0x18000ca1c`
- `0x18000d544`
- `0x18000da00`
- `0x18000e958`
- `0x180010150`
- `0x1800109dc`
- `0x180012118`
- `0x180012f10`
- `0x180013eb4`
- `0x180013f58`
- `0x180014244`
- `0x180014300`
- `0x180014428`
- `0x1800150ac`
- `0x180015338`
- `0x180015818`
- `0x180015f10`
- `0x180015fd4`
- `0x180016044`
- `0x180017b80`
- `0x180018574`
- `0x180018630`
- `0x180018928`
- `0x180018a10`
- `0x180019794`
- `0x18001c58c`
- `0x180020990`
- `0x180020a1c`
- `0x1800211d8`
- `0x180033824`
- `0x180034640`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016438`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016438`

## string_xrefs

- `0x180016107`: `onecoreuap\enduser\winstore\installservice\lib\scanforupdatesworker.cpp`
- `0x180016189`: `onecoreuap\enduser\winstore\installservice\lib\scanforupdatesworker.cpp`
- `0x1800160e6`: `Scan for Updates not enabled on the system. Disabling task and exiting`
- `0x1800160fa`: `ScanForUpdatesWorker::DoWork`
- `0x180016179`: `ScanForUpdatesWorker::DoWork`
- `0x18001630e`: `Auto update is enabled - %u updates to be scheduled with UO`
- `0x1800163c0`: `ScanForUpdatesWorker`
- `0x180016481`: `PauseStoreUpdates`
- `0x18001648d`: `StartStoreUpdates`
- `0x180016494`: `%systemroot%\System32\usoclient.exe`
- `0x1800164c5`: `Scheduled work with UO from scheduled task`
- `0x1800162a3`: `Autoupdate disabled - will not schedule work with UO`
- `0x180016164`: `USO store provider is not enabled. Using ScheduleWorkWithUO for background update scan.`
- `0x180016091`: `AutoUpdateTasksEnabled`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ScanForUpdatesWorker::DoWork(ScanForUpdatesWorker *this)
{
  __int64 v2; // rcx
  bool IsCurrentThreadLocalSystem; // bl
  int v4; // esi
  ScheduledTask **v5; // rax
  const char *v6; // r9
  __int64 result; // rax
  __int64 v8; // rbx
  int v9; // eax
  CorrelationVector *v10; // rax
  int v11; // r8d
  int AutoUpdateState; // eax
  int v13; // eax
  DownloadAndInstallPendingUpdatesWorker **v14; // rax
  DownloadAndInstallPendingUpdatesWorker *v15; // rbx
  __int64 v16; // rbx
  __int64 (__fastcall *v17)(__int64, __int64, HSTRING); // r12
  CorrelationVector *v18; // rax
  HSTRING v19; // r15
  int v20; // eax
  HRESULT v21; // eax
  int v22; // eax
  int v23; // eax
  CorrelationVector *v24; // rax
  WindowsUpdate::CommonTelemetry *v25; // rcx
  const char *v26; // r8
  DownloadAndInstallPendingUpdatesWorker *v27; // rax
  __int64 v28; // rdx
  int ppv; // [rsp+20h] [rbp-188h]
  int ppva; // [rsp+20h] [rbp-188h]
  int ppvb; // [rsp+20h] [rbp-188h]
  int ppvc; // [rsp+20h] [rbp-188h]
  bool v33; // [rsp+50h] [rbp-158h] BYREF
  int v34[2]; // [rsp+58h] [rbp-150h] BYREF
  LPVOID v35; // [rsp+60h] [rbp-148h] BYREF
  __int64 v36; // [rsp+68h] [rbp-140h] BYREF
  __int64 v37; // [rsp+70h] [rbp-138h] BYREF
  ScanForUpdatesWorker *v38; // [rsp+78h] [rbp-130h] BYREF
  __int64 v39; // [rsp+80h] [rbp-128h] BYREF
  DownloadAndInstallPendingUpdatesWorker *v40; // [rsp+88h] [rbp-120h] BYREF
  std::_Ref_count_base *v41; // [rsp+90h] [rbp-118h]
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-110h] BYREF
  __int64 v43; // [rsp+B0h] [rbp-F8h]
  _BYTE v44[160]; // [rsp+C0h] [rbp-E8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  try
  {
    v38 = this;
    IsCurrentThreadLocalSystem = TokenHelpers::IsCurrentThreadLocalSystem(this);
    v33 = IsCurrentThreadLocalSystem;
    if ( IsCurrentThreadLocalSystem )
    {
      v34[0] = 1;
      v4 = Registry::GetValue<unsigned long>(
             v2,
             "S\x00O\x00F\x00T\x00W\x00A\x00R\x00E\x00\\\x00M\x00i\x00c\x00r\x00o\x00s\x00o\x00f\x00t\x00\\\x00W\x00i\x00n\x00d\x00o\x00w\x00s\x00\\\x00C\x00u\x00r\x00r\x00e\x00n\x00t\x00V\x00e\x00r\x00s\x00i\x00o\x00n\x00\\\x00I\x00n\x00s\x00t\x00a\x00l\x00l\x00S\x00e\x00r\x00v\x00i\x00c\x00e\x00\\\x00C\x00o\x00n\x00f\x00i\x00g\x00u\x00r\x00a\x00t\x00i\x00o\x00n",
             L"AutoUpdateTasksEnabled",
             v34);
      v5 = (ScheduledTask **)InstallServiceTasks::ScanForUpdates(&v40);
      ScheduledTask::SetEnabled(*v5, v4 != 0);
      if ( v41 )
        std::_Ref_count_base::_Decref(v41);
      if ( !v4 )
      {
        LogSimpleMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
          0x229u,
          "ScanForUpdatesWorker::DoWork",
          -1,
          L"Scan for Updates not enabled on the system. Disabling task and exiting",
          0,
          0);
        return 0;
      }
      DisableServerRetryTrigger();
      ConfigureWakeUpTasks();
    }
    if ( !CanUseUsoStoreProvider(*(HSTRING *)this)
      && (ShouldExecuteSearchForAllUpdatesForDevice() || ShouldExecuteSearchForAllUpdatesForLoggedOnUsers()) )
    {
      LogSimpleMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
        0x285u,
        "ScanForUpdatesWorker::DoWork",
        -1,
        L"USO store provider is not enabled. Using ScheduleWorkWithUO for background update scan.",
        0,
        0);
      if ( IsCurrentThreadLocalSystem )
      {
        AppReadinessAwaiter::AppReadinessAwaiter((AppReadinessAwaiter *)&v37, *((void **)this + 2));
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v37);
      }
      Microsoft::WRL::Details::Make<Windows::ApplicationModel::Store::Preview::InstallControl::AppUpdateOptions,>(&v37);
      v8 = v37;
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(v37 + 16) + 56LL))(v37 + 16, 0);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x28D,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
          (const char *)(unsigned int)v9,
          ppv);
      wil::ActivateInstance<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppInstallManagerInternal7>(&v38);
      v36 = v8;
      v35 = *(LPVOID *)this;
      v10 = CorrelationVector::CorrelationVector((CorrelationVector *)v44);
      *(_QWORD *)v34 = CorrelationVector::hstring(v10);
      v33 = 0;
      ___CallAndWaitForCompletion_UIAppInstallManagerInternal7_Internal_InstallControl_Preview_Store_ApplicationModel_Windows__EPEAUHSTRING____PEAU8_PEAUIAppUpdateOptions_34567_PEAPEAU__IAsyncOperation_PEAU__IVectorView_PEAVAppInstallItem_InstallControl_Preview_Store_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_7___Z_NPEAU8_PEAU8_PEAVAppUpdateOptions_34567__wil__YA_A_PPEAUIAppInstallManagerInternal7_Internal_InstallControl_Preview_Store_ApplicationModel_Windows__P81234567_EAAJEPEAUHSTRING____1PEAUIAppUpdateOptions_34567_PEAPEAU__IAsyncOperation_PEAU__IVectorView_PEAVAppInstallItem_InstallControl_Preview_Store_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_7__Z__QEA_N__QEAPEAU8_6__QEAPEAVAppUpdateOptions_34567__Z(
        (unsigned int)&v39,
        (_DWORD)v38,
        v11,
        (unsigned int)&v33,
        (__int64)v34,
        (__int64)&v35,
        (__int64)&v36);
      CorrelationVector::~CorrelationVector((CorrelationVector *)v44);
      RecordSuccessUpdateSearch();
      v34[0] = 1;
      AutoUpdateState = GetAutoUpdateState((enum WindowsUpdate::Internal::AutoUpdateState *)v34);
      if ( AutoUpdateState < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x29B,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
          (const char *)(unsigned int)AutoUpdateState,
          ppva);
      if ( ((v34[0] - 1) & 0xFFFFFFFD) != 0 )
      {
        LogSimpleMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
          0x2C3u,
          "ScanForUpdatesWorker::DoWork",
          -1,
          L"Autoupdate disabled - will not schedule work with UO",
          0,
          0);
      }
      else
      {
        v34[0] = 0;
        v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v39 + 56LL))(v39, v34);
        if ( v13 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x29F,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
            (const char *)(unsigned int)v13,
            ppva);
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
          0x2A0u,
          "ScanForUpdatesWorker::DoWork",
          -1,
          L"Auto update is enabled - %u updates to be scheduled with UO",
          0,
          0);
        if ( v34[0] )
        {
          v14 = (DownloadAndInstallPendingUpdatesWorker **)wil::ActivateInstance<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>(&v35);
          v15 = *v14;
          *v14 = 0;
          v40 = v15;
          wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(&v35);
          v36 = 0;
          if ( (**(int (__fastcall ***)(DownloadAndInstallPendingUpdatesWorker *, GUID *, __int64 *))v15)(
                 v15,
                 &GUID_908ab59e_1819_438d_877e_8eaaa74e06a2,
                 &v36) < 0 )
          {
            v35 = 0;
            v21 = CoCreateInstance(
                    &GUID_9c695035_48d2_4229_8b73_4c70e756e519,
                    0,
                    4u,
                    &GUID_c53f3549_0dbf_429a_8297_c812ba00742d,
                    &v35);
            if ( v21 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x2B0,
                (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
                (const char *)(unsigned int)v21,
                ppvc);
            v22 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD))(*(_QWORD *)v35 + 40LL))(v35, L"IA", 0);
            if ( v22 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x2B3,
                (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
                (const char *)(unsigned int)v22,
                ppvc);
            v23 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v35 + 32LL))(
                    v35,
                    L"IA",
                    L"%systemroot%\\System32\\usoclient.exe",
                    L"StartStoreUpdates");
            if ( v23 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x2BA,
                (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
                (const char *)(unsigned int)v23,
                (int)L"PauseStoreUpdates");
            LogSimpleMessage(
              3u,
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
              0x2BBu,
              "ScanForUpdatesWorker::DoWork",
              -1,
              L"Scheduled work with UO from scheduled task",
              0,
              0);
            v24 = CorrelationVector::CorrelationVector((CorrelationVector *)v44);
            WindowsUpdate::CommonTelemetry::ScheduleWorkWithUO(v25, (const unsigned __int16 *)v24 + 4, v26);
            CorrelationVector::~CorrelationVector((CorrelationVector *)v44);
            wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(&v35);
          }
          else
          {
            v16 = v36;
            v17 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING))(*(_QWORD *)v36 + 48LL);
            v18 = CorrelationVector::CorrelationVector((CorrelationVector *)v44);
            v19 = CorrelationVector::hstring(v18);
            v43 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(
              &hstringHeader,
              L"ScanForUpdatesWorker",
              0x15u,
              0x14u);
            v20 = v17(v16, v43, v19);
            if ( v20 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x2AA,
                (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
                (const char *)(unsigned int)v20,
                ppvb);
            v43 = 0;
            CorrelationVector::~CorrelationVector((CorrelationVector *)v44);
          }
          wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(&v36);
          wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(&v40);
          v8 = v37;
        }
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
      wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(&v38);
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    if ( AllowWakeUpOnACScheduledTasks() )
    {
      v40 = (DownloadAndInstallPendingUpdatesWorker *)operator new(0x10u);
      v27 = DownloadAndInstallPendingUpdatesWorker::DownloadAndInstallPendingUpdatesWorker(v40);
      v28 = *((_QWORD *)this + 1);
      *((_QWORD *)this + 1) = v27;
      if ( v28 )
        std::default_delete<DownloadAndInstallPendingUpdatesWorker>::operator()();
      DownloadAndInstallPendingUpdatesWorker::DoWork(*((DownloadAndInstallPendingUpdatesWorker **)this + 1));
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2D0,
                           (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x180016044  push    rbx
0x180016046  push    rsi
0x180016047  push    rdi
0x180016048  push    r12
0x18001604a  push    r14
0x18001604c  push    r15
0x18001604e  sub     rsp, 178h
0x180016055  mov     rax, cs:__security_cookie
0x18001605c  xor     rax, rsp
0x18001605f  mov     [rsp+1A8h+var_48], rax
0x180016067  mov     r14, rcx
0x18001606a  mov     [rsp+1A8h+var_130], rcx
0x18001606f  call    ?IsCurrentThreadLocalSystem@TokenHelpers@@YA_NXZ; TokenHelpers::IsCurrentThreadLocalSystem(void)
0x180016074  mov     bl, al
0x180016076  mov     [rsp+1A8h+var_158], al
0x18001607a  xor     edi, edi
0x18001607c  test    al, al
0x18001607e  jz      loc_180016134
0x180016084  mov     [rsp+1A8h+var_150], 1
0x18001608c  lea     r9, [rsp+1A8h+var_150]
0x180016091  lea     r8, aAutoupdatetask; "AutoUpdateTasksEnabled"
0x180016098  lea     rdx, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; "S\x00O\x00F\x00T\x00W\x00A\x00R\x00E"...
0x18001609f  call    ??$GetValue@K@Registry@@YAKPEAUHKEY__@@PEBG1$$QEAK@Z; Registry::GetValue<ulong>(HKEY__ *,ushort const *,ushort const *,ulong &&)
0x1800160a4  mov     esi, eax
0x1800160a6  test    eax, eax
0x1800160a8  setnz   r15b
0x1800160ac  lea     rcx, [rsp+1A8h+var_120]
0x1800160b4  call    ?ScanForUpdates@InstallServiceTasks@@YA?AV?$shared_ptr@VScheduledTask@@@std@@XZ; InstallServiceTasks::ScanForUpdates(void)
0x1800160b9  nop
0x1800160ba  mov     dl, r15b; bool
0x1800160bd  mov     rcx, [rax]; this
0x1800160c0  call    ?SetEnabled@ScheduledTask@@QEAAX_N@Z; ScheduledTask::SetEnabled(bool)
0x1800160c5  nop
0x1800160c6  mov     rcx, [rsp+1A8h+var_118]; this
0x1800160ce  test    rcx, rcx
0x1800160d1  jz      short loc_1800160D8
0x1800160d3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800160d8  test    esi, esi
0x1800160da  jnz     short loc_18001611D
0x1800160dc  mov     [rsp+1A8h+var_170], rdi; unsigned __int16 *
0x1800160e1  mov     [rsp+1A8h+var_178], rdi; char *
0x1800160e6  lea     rax, aScanForUpdates; "Scan for Updates not enabled on the sys"...
0x1800160ed  mov     [rsp+1A8h+var_180], rax; unsigned __int16 *
0x1800160f2  mov     dword ptr [rsp+1A8h+ppv], 0FFFFFFFFh; int
0x1800160fa  lea     r9, aScanforupdates_0; "ScanForUpdatesWorker::DoWork"
0x180016101  mov     r8d, 229h; unsigned int
0x180016107  lea     rdx, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\installs"...
0x18001610e  lea     ecx, [rsi+3]; unsigned int
0x180016111  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180016116  xor     eax, eax
0x180016118  jmp     loc_1800165AF
0x18001611d  jmp     short loc_18001612A
0x18001611f  xor     edi, edi
0x180016121  mov     bl, [rsp+1A8h+var_158]
0x180016125  mov     r14, [rsp+1A8h+var_130]
0x18001612a  call    ?DisableServerRetryTrigger@@YAXXZ; DisableServerRetryTrigger(void)
0x18001612f  call    ?ConfigureWakeUpTasks@@YAXXZ; ConfigureWakeUpTasks(void)
0x180016134  mov     rcx, [r14]; HSTRING
0x180016137  call    ?CanUseUsoStoreProvider@@YA_NPEAUHSTRING__@@@Z; CanUseUsoStoreProvider(HSTRING__ *)
0x18001613c  test    al, al
0x18001613e  jnz     loc_180016568
0x180016144  call    ?ShouldExecuteSearchForAllUpdatesForDevice@@YA_NXZ; ShouldExecuteSearchForAllUpdatesForDevice(void)
0x180016149  test    al, al
0x18001614b  jnz     short loc_18001615A
0x18001614d  call    ?ShouldExecuteSearchForAllUpdatesForLoggedOnUsers@@YA_NXZ; ShouldExecuteSearchForAllUpdatesForLoggedOnUsers(void)
0x180016152  test    al, al
0x180016154  jz      loc_180016568
0x18001615a  mov     [rsp+1A8h+var_170], rdi; unsigned __int16 *
0x18001615f  mov     [rsp+1A8h+var_178], rdi; char *
0x180016164  lea     rax, aUsoStoreProvid; "USO store provider is not enabled. Usin"...
0x18001616b  mov     [rsp+1A8h+var_180], rax; unsigned __int16 *
0x180016170  or      r15d, 0FFFFFFFFh
0x180016174  mov     dword ptr [rsp+1A8h+ppv], r15d; int
0x180016179  lea     r12, aScanforupdates_0; "ScanForUpdatesWorker::DoWork"
0x180016180  mov     r9, r12; char *
0x180016183  mov     r8d, 285h; unsigned int
0x180016189  lea     rsi, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\installs"...
0x180016190  mov     rdx, rsi; char *
0x180016193  lea     ecx, [r15+4]; unsigned int
0x180016197  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x18001619c  test    bl, bl
0x18001619e  jz      short loc_1800161B8
0x1800161a0  mov     rdx, [r14+10h]; void *
0x1800161a4  lea     rcx, [rsp+1A8h+var_138]; this
0x1800161a9  call    ??0AppReadinessAwaiter@@QEAA@PEAX@Z; AppReadinessAwaiter::AppReadinessAwaiter(void *)
0x1800161ae  lea     rcx, [rsp+1A8h+var_138]
0x1800161b3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800161b8  lea     rcx, [rsp+1A8h+var_138]
0x1800161bd  call    ??$Make@VAppUpdateOptions@InstallControl@Preview@Store@ApplicationModel@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VAppUpdateOptions@InstallControl@Preview@Store@ApplicationModel@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::ApplicationModel::Store::Preview::InstallControl::AppUpdateOptions,>(void)
0x1800161c2  nop
0x1800161c3  mov     rbx, [rsp+1A8h+var_138]
0x1800161c8  lea     rcx, [rbx+10h]
0x1800161cc  mov     rax, [rcx]
0x1800161cf  xor     edx, edx
0x1800161d1  mov     rax, [rax+38h]
0x1800161d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161da  mov     rcx, [rsp+1A8h]; this
0x1800161e2  test    eax, eax
0x1800161e4  js      loc_1800165D0
0x1800161ea  lea     rcx, [rsp+1A8h+var_130]
0x1800161ef  call    ??$ActivateInstance@UIAppInstallManagerInternal7@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@wil@@YA?AV?$com_ptr_t@UIAppInstallManagerInternal7@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppInstallManagerInternal7>(ushort const *)
0x1800161f4  nop
0x1800161f5  mov     [rsp+1A8h+var_140], rbx
0x1800161fa  mov     rax, [r14]
0x1800161fd  mov     [rsp+1A8h+var_148], rax
0x180016202  lea     rcx, [rsp+1A8h+var_E8]; this
0x18001620a  call    ??0CorrelationVector@@QEAA@XZ; CorrelationVector::CorrelationVector(void)
0x18001620f  nop
0x180016210  mov     rcx, rax; this
0x180016213  call    ?hstring@CorrelationVector@@QEAAPEAUHSTRING__@@XZ; CorrelationVector::hstring(void)
0x180016218  mov     qword ptr [rsp+1A8h+var_150], rax
0x18001621d  mov     [rsp+1A8h+var_158], dil
0x180016222  lea     rax, [rsp+1A8h+var_140]
0x180016227  mov     [rsp+1A8h+var_178], rax
0x18001622c  lea     rax, [rsp+1A8h+var_148]
0x180016231  mov     [rsp+1A8h+var_180], rax
0x180016236  lea     rax, [rsp+1A8h+var_150]
0x18001623b  mov     [rsp+1A8h+ppv], rax; int
0x180016240  lea     r9, [rsp+1A8h+var_158]
0x180016245  mov     rdx, [rsp+1A8h+var_130]
0x18001624a  lea     rcx, [rsp+1A8h+var_128]
0x180016252  call    ??$CallAndWaitForCompletion@UIAppInstallManagerInternal7@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@EPEAUHSTRING__@@PEAU8@PEAUIAppUpdateOptions@34567@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@7@$$Z_NPEAU8@PEAU8@PEAVAppUpdateOptions@34567@@wil@@YA?A_PPEAUIAppInstallManagerInternal7@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@P81234567@EAAJEPEAUHSTRING__@@1PEAUIAppUpdateOptions@34567@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@7@@Z$$QEA_N$$QEAPEAU8@6$$QEAPEAVAppUpdateOptions@34567@@Z
0x180016257  nop
0x180016258  lea     rcx, [rsp+1A8h+var_E8]; this
0x180016260  call    ??1CorrelationVector@@QEAA@XZ; CorrelationVector::~CorrelationVector(void)
0x180016265  call    ?RecordSuccessUpdateSearch@@YAXXZ; RecordSuccessUpdateSearch(void)
0x18001626a  mov     [rsp+1A8h+var_150], 1
0x180016272  lea     rcx, [rsp+1A8h+var_150]; enum WindowsUpdate::Internal::AutoUpdateState *
0x180016277  call    ?GetAutoUpdateState@@YAJPEAW4AutoUpdateState@Internal@WindowsUpdate@@@Z; GetAutoUpdateState(WindowsUpdate::Internal::AutoUpdateState *)
0x18001627c  mov     rcx, [rsp+1A8h]; this
0x180016284  test    eax, eax
0x180016286  js      loc_1800165E1
0x18001628c  mov     eax, [rsp+1A8h+var_150]
0x180016290  dec     eax
0x180016292  test    eax, 0FFFFFFFDh
0x180016297  jz      short loc_1800162CF
0x180016299  mov     [rsp+1A8h+var_170], rdi; unsigned __int16 *
0x18001629e  mov     [rsp+1A8h+var_178], rdi; char *
0x1800162a3  lea     rax, aAutoupdateDisa; "Autoupdate disabled - will not schedule"...
0x1800162aa  mov     [rsp+1A8h+var_180], rax; unsigned __int16 *
0x1800162af  mov     dword ptr [rsp+1A8h+ppv], r15d; int
0x1800162b4  mov     r9, r12; char *
0x1800162b7  mov     r8d, 2C3h; unsigned int
0x1800162bd  mov     rdx, rsi; char *
0x1800162c0  mov     ecx, 3; unsigned int
0x1800162c5  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x1800162ca  jmp     loc_18001653A
0x1800162cf  mov     [rsp+1A8h+var_150], edi
0x1800162d3  mov     rcx, [rsp+1A8h+var_128]
0x1800162db  mov     rax, [rcx]
0x1800162de  lea     rdx, [rsp+1A8h+var_150]
0x1800162e3  mov     rax, [rax+38h]
0x1800162e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162ec  mov     rcx, [rsp+1A8h]; this
0x1800162f4  test    eax, eax
0x1800162f6  js      loc_1800165F1
0x1800162fc  mov     eax, [rsp+1A8h+var_150]
0x180016300  mov     [rsp+1A8h+var_168], eax
0x180016304  mov     [rsp+1A8h+var_170], rdi; unsigned __int16 *
0x180016309  mov     [rsp+1A8h+var_178], rdi; char *
0x18001630e  lea     rax, aAutoUpdateIsEn; "Auto update is enabled - %u updates to "...
0x180016315  mov     [rsp+1A8h+var_180], rax; unsigned __int16 *
0x18001631a  mov     dword ptr [rsp+1A8h+ppv], r15d; int
0x18001631f  mov     r9, r12; char *
0x180016322  mov     r8d, 2A0h; unsigned int
0x180016328  mov     rdx, rsi; char *
0x18001632b  mov     ecx, 3; unsigned int
0x180016330  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180016335  cmp     [rsp+1A8h+var_150], edi
0x180016339  jbe     loc_18001653A
0x18001633f  lea     rcx, [rsp+1A8h+var_148]
0x180016344  call    ??$ActivateInstance@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@wil@@YA?AV?$com_ptr_t@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>(ushort const *)
0x180016349  mov     rbx, [rax]
0x18001634c  mov     [rax], rdi
0x18001634f  mov     [rsp+1A8h+var_120], rbx
0x180016357  lea     rcx, [rsp+1A8h+var_148]
0x18001635c  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x180016361  nop
0x180016362  mov     [rsp+1A8h+var_140], rdi
0x180016367  mov     rax, [rbx]
0x18001636a  lea     r8, [rsp+1A8h+var_140]
0x18001636f  lea     rdx, _GUID_908ab59e_1819_438d_877e_8eaaa74e06a2
0x180016376  mov     rcx, rbx
0x180016379  mov     rax, [rax]
0x18001637c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016381  test    eax, eax
0x180016383  js      loc_180016415
0x180016389  mov     rbx, [rsp+1A8h+var_140]
0x18001638e  mov     rax, [rbx]
0x180016391  mov     r12, [rax+30h]
0x180016395  lea     rcx, [rsp+1A8h+var_E8]; this
0x18001639d  call    ??0CorrelationVector@@QEAA@XZ; CorrelationVector::CorrelationVector(void)
0x1800163a2  nop
0x1800163a3  mov     rcx, rax; this
0x1800163a6  call    ?hstring@CorrelationVector@@QEAAPEAUHSTRING__@@XZ; CorrelationVector::hstring(void)
0x1800163ab  mov     r15, rax
0x1800163ae  mov     [rsp+1A8h+var_F8], rdi
0x1800163b6  mov     r9d, 14h; unsigned int
0x1800163bc  lea     r8d, [r9+1]; unsigned int
0x1800163c0  lea     rdx, aScanforupdates_1; "ScanForUpdatesWorker"
0x1800163c7  lea     rcx, [rsp+1A8h+hstringHeader]; hstringHeader
0x1800163cf  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800163d4  nop
0x1800163d5  mov     r8, r15
0x1800163d8  mov     rdx, [rsp+1A8h+var_F8]
0x1800163e0  mov     rcx, rbx
0x1800163e3  mov     rax, r12
0x1800163e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163eb  mov     rcx, [rsp+1A8h]; this
0x1800163f3  test    eax, eax
0x1800163f5  js      loc_180016602
0x1800163fb  mov     [rsp+1A8h+var_F8], rdi
0x180016403  lea     rcx, [rsp+1A8h+var_E8]; this
0x18001640b  call    ??1CorrelationVector@@QEAA@XZ; CorrelationVector::~CorrelationVector(void)
0x180016410  jmp     loc_18001651D
0x180016415  mov     [rsp+1A8h+var_148], rdi
0x18001641a  lea     rax, [rsp+1A8h+var_148]
0x18001641f  mov     [rsp+1A8h+ppv], rax; int
0x180016424  lea     r9, _GUID_c53f3549_0dbf_429a_8297_c812ba00742d; riid
0x18001642b  xor     edx, edx; pUnkOuter
0x18001642d  lea     r8d, [rdx+4]; dwClsContext
0x180016431  lea     rcx, _GUID_9c695035_48d2_4229_8b73_4c70e756e519; rclsid
0x180016438  call    cs:__imp_CoCreateInstance
0x18001643e  mov     rcx, [rsp+1A8h]; this
0x180016446  test    eax, eax
0x180016448  js      loc_180016613
0x18001644e  mov     rcx, [rsp+1A8h+var_148]
0x180016453  mov     rax, [rcx]
0x180016456  xor     r8d, r8d
0x180016459  lea     rdx, aIa; "IA"
0x180016460  mov     rax, [rax+28h]
0x180016464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016469  mov     rcx, [rsp+1A8h]; this
0x180016471  test    eax, eax
0x180016473  js      loc_180016623
0x180016479  mov     rcx, [rsp+1A8h+var_148]
0x18001647e  mov     rax, [rcx]
0x180016481  lea     r8, aPausestoreupda; "PauseStoreUpdates"
0x180016488  mov     [rsp+1A8h+ppv], r8; int
0x18001648d  lea     r9, aStartstoreupda; "StartStoreUpdates"
0x180016494  lea     r8, aSystemrootSyst; "%systemroot%\\System32\\usoclient.exe"
0x18001649b  lea     rdx, aIa; "IA"
0x1800164a2  mov     rax, [rax+20h]
0x1800164a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164ab  mov     rcx, [rsp+1A8h]; this
0x1800164b3  test    eax, eax
0x1800164b5  js      loc_180016633
0x1800164bb  mov     [rsp+1A8h+var_170], rdi; unsigned __int16 *
0x1800164c0  mov     [rsp+1A8h+var_178], rdi; char *
0x1800164c5  lea     rax, aScheduledWorkW; "Scheduled work with UO from scheduled t"...
0x1800164cc  mov     [rsp+1A8h+var_180], rax; unsigned __int16 *
0x1800164d1  mov     dword ptr [rsp+1A8h+ppv], r15d; int
0x1800164d6  mov     r9, r12; char *
0x1800164d9  mov     r8d, 2BBh; unsigned int
0x1800164df  mov     rdx, rsi; char *
0x1800164e2  mov     ecx, 3; unsigned int
0x1800164e7  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x1800164ec  lea     rcx, [rsp+1A8h+var_E8]; this
0x1800164f4  call    ??0CorrelationVector@@QEAA@XZ; CorrelationVector::CorrelationVector(void)
0x1800164f9  nop
0x1800164fa  lea     rdx, [rax+8]; unsigned __int16 *
0x1800164fe  call    ?ScheduleWorkWithUO@CommonTelemetry@WindowsUpdate@@YAXPEBGPEBD@Z; WindowsUpdate::CommonTelemetry::ScheduleWorkWithUO(ushort const *,char const *)
0x180016503  nop
0x180016504  lea     rcx, [rsp+1A8h+var_E8]; this
0x18001650c  call    ??1CorrelationVector@@QEAA@XZ; CorrelationVector::~CorrelationVector(void)
0x180016511  nop
0x180016512  lea     rcx, [rsp+1A8h+var_148]
0x180016517  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x18001651c  nop
0x18001651d  lea     rcx, [rsp+1A8h+var_140]
0x180016522  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x180016527  nop
0x180016528  lea     rcx, [rsp+1A8h+var_120]
0x180016530  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x180016535  mov     rbx, [rsp+1A8h+var_138]
0x18001653a  lea     rcx, [rsp+1A8h+var_128]
0x180016542  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016547  nop
0x180016548  lea     rcx, [rsp+1A8h+var_130]
0x18001654d  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x180016552  nop
0x180016553  test    rbx, rbx
0x180016556  jz      short loc_180016568
0x180016558  mov     rax, [rbx]
0x18001655b  mov     rcx, rbx
0x18001655e  mov     rax, [rax+10h]
0x180016562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016567  nop
0x180016568  call    ?AllowWakeUpOnACScheduledTasks@@YA_NXZ; AllowWakeUpOnACScheduledTasks(void)
0x18001656d  test    al, al
0x18001656f  jz      short loc_1800165A7
0x180016571  mov     ecx, 10h; Size
0x180016576  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001657b  mov     [rsp+1A8h+var_120], rax
0x180016583  mov     rcx, rax; this
0x180016586  call    ??0DownloadAndInstallPendingUpdatesWorker@@QEAA@XZ; DownloadAndInstallPendingUpdatesWorker::DownloadAndInstallPendingUpdatesWorker(void)
0x18001658b  nop
0x18001658c  mov     rdx, [r14+8]
0x180016590  mov     [r14+8], rax
0x180016594  test    rdx, rdx
  ... truncated ...
```
