# WorkerTaskMigrationSource::DoStateTransferSteps(__int64 &)

- ea: `0x1400ce948`
- end: `0x1400cf604`
- name: `?DoStateTransferSteps@WorkerTaskMigrationSource@@AEAAJAEA_J@Z`
- size: `3260`
- prototype: `__int64 __fastcall(WorkerTaskMigrationSource *__hidden this, __int64 *)`
- caller_count: `1`
- callee_count: `51`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400ae810`

## callees

- `0x14002ecd0`
- `0x140031c88`
- `0x140042240`
- `0x140054508`
- `0x140054630`
- `0x1400549dc`
- `0x140062e00`
- `0x14006af38`
- `0x140078c98`
- `0x14007a72c`
- `0x140096ab4`
- `0x1400a0074`
- `0x1400a009c`
- `0x1400a0154`
- `0x1400a05e8`
- `0x1400b04e0`
- `0x1400b4c40`
- `0x1400b7ae8`
- `0x1400cce00`
- `0x1400ce0c0`
- `0x1400ce7c4`
- `0x1400ce884`
- `0x1400ce948`
- `0x1400cf8a0`
- `0x1400cf9c0`
- `0x1400eb528`
- `0x1400ed0f8`
- `0x1400f1978`
- `0x140119298`
- `0x14011d7f4`
- `0x14011d820`
- `0x14012bea0`
- `0x14012f68c`
- `0x140132940`
- `0x1401335fc`
- `0x14014c9c8`
- `0x14014eaec`
- `0x14015ec8c`
- `0x140170910`
- `0x14017295c`
- `0x1401731dc`
- `0x1401e1864`
- `0x140218028`
- `0x1402180e8`
- `0x140218140`
- `0x140218608`
- `0x140219804`
- `0x14021ae90`
- `0x14022138c`
- `0x14022148c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1400cea65`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1400cf565`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1400cea65`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1400cf565`
- `vid!VidTdxExportPause` at `0x1400cedb9`
- `vid!VidTdxExportPause` at `0x1400cedb9`

## string_xrefs

- `0x1400cecf4`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x1400cedf5`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x1400ceed8`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x1400cef20`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x1400cef56`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x1400cef8c`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x1400cefb4`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x1400cf175`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x1400cf33b`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x1400cf3c1`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x1400cf477`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x1400cf49c`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x1400cf4da`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x1400cf4ff`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`

## pseudocode

```c
__int64 __fastcall WorkerTaskMigrationSource::DoStateTransferSteps(WorkerTaskMigrationSource *this, __int64 *a2)
{
  WorkerTaskMigrationSource *v3; // rsi
  const struct _GUID *v4; // rbx
  _QWORD *v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 future; // r14
  __int64 v9; // rax
  __int64 v10; // rax
  _BYTE *v11; // r14
  __int64 v12; // rcx
  __int64 v13; // rax
  void *v14; // rdx
  wil::details ***v15; // rcx
  wil::details *v16; // rcx
  _DWORD *v17; // r13
  __int64 v18; // rcx
  int v19; // eax
  SavedStateRepository **v20; // r15
  int v21; // eax
  int v22; // eax
  int v23; // eax
  const char *v24; // r9
  WorkerTaskMigrationSource *v25; // r15
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // r15
  __int64 v31; // rcx
  __int64 v32; // rbx
  __int64 v33; // rcx
  unsigned int v34; // edx
  int v35; // eax
  const char *v36; // r9
  int v37; // r15d
  __int64 *v38; // r12
  int v39; // eax
  int v40; // ebx
  int v41; // eax
  int v42; // ebx
  __int64 v44; // rax
  __int64 v45; // rax
  int v46; // [rsp+20h] [rbp-348h]
  int v47; // [rsp+30h] [rbp-338h] BYREF
  int v48; // [rsp+34h] [rbp-334h] BYREF
  __int64 VmName; // [rsp+38h] [rbp-330h] BYREF
  __int64 v50; // [rsp+40h] [rbp-328h] BYREF
  __int64 v51[2]; // [rsp+48h] [rbp-320h] BYREF
  char *v52[2]; // [rsp+58h] [rbp-310h] BYREF
  WorkerTaskMigrationSource *v53; // [rsp+68h] [rbp-300h]
  WorkerTaskMigrationSource *v54; // [rsp+70h] [rbp-2F8h]
  _QWORD *v55; // [rsp+78h] [rbp-2F0h] BYREF
  __int64 v56; // [rsp+80h] [rbp-2E8h] BYREF
  __int64 (__fastcall *v57)(WorkerTaskMigrationSource *); // [rsp+88h] [rbp-2E0h] BYREF
  __int64 v58; // [rsp+90h] [rbp-2D8h]
  char v59[16]; // [rsp+98h] [rbp-2D0h] BYREF
  __int64 *v60; // [rsp+A8h] [rbp-2C0h]
  __int64 *v61; // [rsp+B0h] [rbp-2B8h]
  ULONGLONG TickCount64; // [rsp+B8h] [rbp-2B0h]
  __m128i si128; // [rsp+C0h] [rbp-2A8h] BYREF
  _OWORD v64[3]; // [rsp+D0h] [rbp-298h] BYREF
  __int64 v65; // [rsp+100h] [rbp-268h]
  int v66; // [rsp+108h] [rbp-260h]
  struct _GUID v67; // [rsp+110h] [rbp-258h] BYREF
  _BYTE v68[24]; // [rsp+120h] [rbp-248h] BYREF
  char v69; // [rsp+138h] [rbp-230h]
  _BYTE v70[24]; // [rsp+140h] [rbp-228h] BYREF
  char v71; // [rsp+158h] [rbp-210h]
  __int128 v72; // [rsp+160h] [rbp-208h] BYREF
  __int64 v73; // [rsp+170h] [rbp-1F8h]
  _BYTE v74[12]; // [rsp+180h] [rbp-1E8h] BYREF
  int v75; // [rsp+18Ch] [rbp-1DCh]
  __int64 v76; // [rsp+198h] [rbp-1D0h]
  __int64 v77; // [rsp+1A0h] [rbp-1C8h]
  char v78[72]; // [rsp+1A8h] [rbp-1C0h] BYREF
  _BYTE v79[24]; // [rsp+1F0h] [rbp-178h] BYREF
  __int64 v80; // [rsp+208h] [rbp-160h]
  __int64 v81; // [rsp+210h] [rbp-158h]
  char v82[72]; // [rsp+218h] [rbp-150h] BYREF
  _BYTE v83[96]; // [rsp+260h] [rbp-108h] BYREF
  char v84[40]; // [rsp+2C0h] [rbp-A8h] BYREF
  char v85[72]; // [rsp+2E8h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+0h]

  v60 = a2;
  v3 = this;
  v54 = this;
  v53 = this;
  v61 = a2;
  v48 = 0;
  v67 = 0;
  v4 = (const struct _GUID *)((char *)this + 412);
  Vml::VmPerfTraceOperation::VmPerfTraceOperation(
    (Vml::VmPerfTraceOperation *)v79,
    (struct Vml::VmPerfTraceComponent *)&g_MigrationPerfTrace,
    (const struct _GUID *)((char *)this + 412),
    &v67);
  v67 = 0;
  Vml::VmPerfTraceOperation::VmPerfTraceOperation(
    (Vml::VmPerfTraceOperation *)v74,
    (struct Vml::VmPerfTraceComponent *)&g_MigrationPerfTrace,
    v4,
    &v67);
  v67 = 0;
  Vml::VmPerfTraceOperation::VmPerfTraceOperation(
    (Vml::VmPerfTraceOperation *)v84,
    (struct Vml::VmPerfTraceComponent *)&g_MigrationPerfTrace,
    v4,
    &v67);
  v80 = *a2;
  v56 = (__int64)v3 + 16;
  v5 = (_QWORD *)((char *)v3 + 16);
  v55 = (_QWORD *)((char *)v3 + 16);
  VirtualMachine::GetVmName((VirtualMachine *)(*((_QWORD *)v3 + 2) + 16LL));
  Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
    (Vml::VmPerfTraceOperation *)v79,
    &VMWP_PERF_MIGRATION_SOURCE_MOVE_START);
  TickCount64 = GetTickCount64();
  *(_QWORD *)&v67.Data1 = 0;
  *(_QWORD *)v67.Data4 = 0;
  std::promise<long>::promise<long>(v68);
  v69 = 1;
  std::promise<long>::promise<long>(v70);
  v71 = 1;
  v72 = 0;
  v73 = 0;
  VmName = (__int64)v3;
  v57 = WorkerTaskMigrationSource::SendVmState;
  v58 = 0;
  std::tuple<WorkerTaskMigrationSource *,std::_Ph<1>,std::_Ph<2>>::tuple<WorkerTaskMigrationSource *,std::_Ph<1>,std::_Ph<2>>(
    v59,
    &VmName);
  try
  {
    ____0V___Binder_U_Unforced_std__P8WorkerTaskMigrationSource__EAAJV__future_J_2_0__EPEAV3_AEBU___Ph__00_2_AEBU___Ph__01_2__std___0A____packaged_task___A6AJV__future_J_std__0_Z_std__QEAA___QEAV___Binder_U_Unforced_std__P8WorkerTaskMigrationSource__EAAJV__future_J_2_0__EPEAV3_AEBU___Ph__00_2_AEBU___Ph__01_2__1__Z(
      &v72,
      &v57);
    v6 = *(_QWORD *)std::_Promise<long>::_Get_state_for_future(&v72);
    LOBYTE(v58) = 1;
    if ( v6 )
      _InterlockedAdd((volatile signed __int32 *)(v6 + 8), 1u);
    v57 = 0;
    *(_QWORD *)&v67.Data1 = v6;
    v67.Data4[0] = 1;
    std::_State_manager<int>::~_State_manager<int>(&v57);
    v7 = std::optional<EndpointTransferRuntimeStats::RuntimeStatistics>::value(v70);
    future = std::packaged_task<long (void)>::get_future(v7, v52);
    v9 = std::optional<EndpointTransferRuntimeStats::RuntimeStatistics>::value(v68);
    v10 = std::packaged_task<long (void)>::get_future(v9, v51);
    std::thread::_Start<std::packaged_task<long (std::future<long>,std::future<long>)>,std::future<long>,std::future<long>>(
      &v57,
      &v72,
      v10,
      future);
    std::thread::detach((std::thread *)&v57);
    std::thread::~thread((std::thread *)&v57);
    std::_State_manager<int>::~_State_manager<int>(v51);
    std::_State_manager<int>::~_State_manager<int>(v52);
    VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(*v5 + 16LL));
    Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v74,
      &VMWP_PERF_MIGRATION_SOURCE_PAUSE_VM_START);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    si128.m128i_i32[2] = 0;
    si128.m128i_i8[12] = 0;
    memset_0(v64, 0, 0x40u);
    memset(v64, 0, sizeof(v64));
    v65 = 0;
    v66 = 0;
    std::variant<std::monostate,Compute::Responses::System::WorkerCoreNotification,Schema::Responses::System::OperationSystemMigrationNotificationInfo>::variant<std::monostate,Compute::Responses::System::WorkerCoreNotification,Schema::Responses::System::OperationSystemMigrationNotificationInfo>(
      v83,
      &si128);
    v57 = (__int64 (__fastcall *)(WorkerTaskMigrationSource *))((char *)v3 + 576);
    (*(void (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)v3 + 72) + 128LL))(*((_QWORD *)v3 + 72), v83);
    if ( !(unsigned int)VirtualMachine::SetState(*v5, 9, 26) )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
        VmlDebugTraceEx(16866, &off_1402DB060);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x570,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)0x8000FFFFLL,
        v46);
    }
    if ( *((_DWORD *)v3 + 138) == 2 )
    {
      v12 = *v5;
      VmName = *v5 + 1152LL;
      v50 = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(v12 + 16));
      VmEventWrite<unsigned short const *,unsigned short const *>(
        &MSVM_WORKER_MIGRATION_ENTER_BLACKOUT,
        1u,
        (__int64)&VmName);
      *((struct _FILETIME *)v3 + 101) = CurrentFileTime();
      v11 = (char *)v3 + 588;
      VirtualMachine::StopVm(*v5, *((_DWORD *)v3 + 147) & 0x20 | 0x11u, 18);
      if ( *((_BYTE *)v3 + 409) )
      {
        v13 = (**(__int64 (__fastcall ***)(__int64))(*(_QWORD *)(*v5 + 1024LL) + 24LL))(*(_QWORD *)(*v5 + 1024LL) + 24LL);
        if ( !(unsigned int)VidTdxExportPause(v13) )
        {
          if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
            VmlDebugTraceEx(16866, &off_1402DADF8);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x58D,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
            (const char *)0x8000FFFFLL,
            v46);
        }
      }
      if ( (unsigned __int8)_is_valid___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEBA_NXZ((char *)v3 + 1224) )
      {
        if ( *v15 )
          v16 = **v15;
        else
          v16 = 0;
        wil::details::SetEvent(v16, v14);
      }
    }
    else
    {
      v11 = (char *)v3 + 588;
    }
    VmName = (__int64)v11;
    v17 = (_DWORD *)((char *)v3 + 556);
    v51[0] = (__int64)v3 + 556;
    *((_DWORD *)v3 + 139) = 5;
    *(_BYTE *)(*((_QWORD *)v3 + 58) + 848LL) = 1;
    v50 = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(*v5 + 16LL));
    Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v74,
      &VMWP_PERF_MIGRATION_SOURCE_PAUSE_VM_STOP,
      (__int64)&v50);
    if ( (*v11 & 0x20) != 0 )
    {
      v18 = *v5;
      v50 = *v5 + 1152LL;
      v52[0] = (char *)VirtualMachine::GetVmName((VirtualMachine *)(v18 + 16));
      VmEventWrite<unsigned short const *,unsigned short const *>(
        &MSVM_WORKER_MIGRATION_SOURCE_PAUSE_VM_STOP,
        1u,
        (__int64)&v50);
    }
    v19 = WorkerTaskMigrationSource::CheckCancel((WorkerTaskMigrationSource *)((char *)v3 + 400));
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5B3,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)(unsigned int)v19,
        v46);
    *(_OWORD *)v52 = 0;
    v20 = (SavedStateRepository **)((char *)v3 + 448);
    v50 = (__int64)v3 + 448;
    VmRepositoryAutoLock::VmRepositoryAutoLock(v52, *((_QWORD *)v3 + 56), 1);
    if ( SLODWORD(v52[1]) < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5BB,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)LODWORD(v52[1]),
        v46);
    v21 = SavedStateRepository::WriteInteger(*v20, L"/migration/blackout_start_timestamp", *((_QWORD *)v3 + 101));
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5BF,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)(unsigned int)v21,
        v46);
    v22 = SavedStateRepository::WriteInteger(*v20, L"/migration/clock_drift", *((_QWORD *)v3 + 102));
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5C3,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)(unsigned int)v22,
        v46);
    v23 = SavedStateRepository::Commit(*v20);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5C5,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)(unsigned int)v23,
        v46);
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v52);
    v76 = 0;
    v77 = 0;
    v75 = 1;
    v52[0] = (char *)VirtualMachine::GetVmName((VirtualMachine *)(*v5 + 16LL));
    Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v74,
      &VMWP_PERF_MIGRATION_SOURCE_SAVE_VSM_START);
    (*(void (__fastcall **)(_QWORD, SavedStateRepository *))(**(_QWORD **)(*v5 + 1024LL) + 256LL))(
      *(_QWORD *)(*v5 + 1024LL),
      *v20);
    try
    {
      (*(void (__fastcall **)(_QWORD, SavedStateRepository *))(**(_QWORD **)(*v5 + 992LL) + 416LL))(
        *(_QWORD *)(*v5 + 992LL),
        *v20);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x5D7,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        v24);
      v48 = 0;
      v5 = v55;
      v3 = v54;
      v11 = (_BYTE *)VmName;
      v60 = v61;
      v17 = (_DWORD *)v51[0];
      v20 = (SavedStateRepository **)v50;
    }
    (*(void (__fastcall **)(_QWORD, SavedStateRepository *))(**(_QWORD **)(*v5 + 992LL) + 400LL))(
      *(_QWORD *)(*v5 + 992LL),
      *v20);
    v25 = v53;
    if ( (*v11 & 1) != 0 && (*v11 & 0x10) == 0 && *((_BYTE *)v53 + 529) )
      WorkerTaskMigrationSource::SetupSkippedForProtectionBitmapsForChecksum(v3);
    v51[0] = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(*v5 + 16LL));
    Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v74,
      &VMWP_PERF_MIGRATION_SOURCE_SAVE_VSM_STOP,
      (__int64)v51);
    if ( !*((_BYTE *)v25 + 530) )
    {
      v26 = std::optional<EndpointTransferRuntimeStats::RuntimeStatistics>::value(v68);
      v47 = 0;
      std::promise<long>::set_value(v26, &v47);
      std::_Optional_destruct_base<std::promise<long>,0>::reset(v68);
    }
    v76 = 0;
    v77 = 0;
    v75 = 1;
    v51[0] = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(*v5 + 16LL));
    Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v74,
      &VMWP_PERF_MIGRATION_SOURCE_MOVE_SAVE_STATE_START);
    v27 = WorkerTaskMigrationSource::SaveVmState(v3);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5F5,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)(unsigned int)v27,
        v46);
    v51[0] = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(*v5 + 16LL));
    Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v74,
      &VMWP_PERF_MIGRATION_SOURCE_MOVE_SAVE_STATE_STOP,
      (__int64)v51);
    v28 = std::optional<EndpointTransferRuntimeStats::RuntimeStatistics>::value(v70);
    v47 = 0;
    std::promise<long>::set_value(v28, &v47);
    std::_Optional_destruct_base<std::promise<long>,0>::reset(v70);
    v76 = 0;
    v77 = 0;
    v75 = 1;
    v51[0] = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(*v5 + 16LL));
    Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v74,
      &VMWP_PERF_MIGRATION_SOURCE_MOVE_POWER_OFF_START);
    VirtualMotherboard::PowerOff(*(_QWORD *)(*v5 + 984LL), (*(_DWORD *)v11 & 0x20 | 0x10u) >> 4);
    *v17 = 7;
    v47 = 0;
    WorkerAsyncTaskBase::UpdateStatusProgress(v3, 0x5Du, &v47);
    v51[0] = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(*v5 + 16LL));
    Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v74,
      &VMWP_PERF_MIGRATION_SOURCE_MOVE_POWER_OFF_STOP,
      (__int64)v51);
    if ( *((_BYTE *)v25 + 530) )
    {
      v29 = std::optional<EndpointTransferRuntimeStats::RuntimeStatistics>::value(v68);
      v47 = 0;
      std::promise<long>::set_value(v29, &v47);
      std::_Optional_destruct_base<std::promise<long>,0>::reset(v68);
    }
    v30 = *v5;
    v31 = *(_QWORD *)(*v5 + 1424LL);
    if ( v31 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v31 + 256LL))(v31, 0);
    HyperVRepository::Disconnect(*(HyperVRepository **)(*(_QWORD *)(v30 + 1416) + 88LL), 0);
    *v17 = 9;
    if ( (*v11 & 0x20) != 0 )
    {
      if ( !(unsigned int)VirtualMachine::SetState(*v5, 7, 24) )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
          VmlDebugTraceEx(16866, &off_1402DB030);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x624,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
          (const char *)0x8000FFFFLL,
          v46);
      }
      v32 = *v5;
      v51[0] = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(v32 + 16));
      v55 = (_QWORD *)(v32 + 1152);
      Vml::VmPerfTraceComponent::LogEvent<unsigned short const *,unsigned short const *>(
        v33,
        VMWP_PERF_MIGRATION_SOURCE_MIGRATING_SUSPENDED,
        &v55,
        v51);
    }
    (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v57 + 24LL))(*(_QWORD *)v57, 0);
    *v17 = 10;
    if ( (*v11 & 0x20) != 0 )
    {
      v35 = MigrationManager::WaitForInMigratingSuspendedState(*((MigrationManager **)v3 + 54), v34);
      if ( v35 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x635,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
          (const char *)(unsigned int)v35,
          v46);
      v47 = 0;
      WorkerAsyncTaskBase::UpdateStatusProgress(v3, 0x64u, &v47);
    }
    *v17 = 11;
    std::_Variant_destroy_layer_<std::monostate,Compute::Responses::System::WorkerCoreNotification,Schema::Responses::System::OperationSystemMigrationNotificationInfo>::~_Variant_destroy_layer_<std::monostate,Compute::Responses::System::WorkerCoreNotification,Schema::Responses::System::OperationSystemMigrationNotificationInfo>(v83);
    Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::~DelayedBase<void,Marshal::Details::DelayedJsonTraits>(v64);
    std::packaged_task<long (std::future<long>,std::future<long>)>::~packaged_task<long (std::future<long>,std::future<long>)>(&v72);
    v37 = v48;
    v38 = v60;
  }
  catch ( ... )
  {
    v47 = wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x642,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
            v36);
    if ( v69 )
    {
      v44 = std::optional<EndpointTransferRuntimeStats::RuntimeStatistics>::value(v68);
      v48 = -2147467260;
      std::promise<long>::set_value(v44, &v48);
      std::_Optional_destruct_base<std::promise<long>,0>::reset(v68);
    }
    if ( v71 )
    {
      v45 = std::optional<EndpointTransferRuntimeStats::RuntimeStatistics>::value(v70);
      v48 = -2147467260;
      std::promise<long>::set_value(v45, &v48);
      std::_Optional_destruct_base<std::promise<long>,0>::reset(v70);
    }
    VmMigrationConnection::Cancel(*((VmMigrationConnection **)v54 + 55), 1);
    v3 = v54;
    v11 = (char *)v54 + 588;
    v37 = v47;
    v38 = v61;
  }
  if ( (unsigned __int8)std::_State_manager<long>::valid(&v67) )
  {
    v39 = std::future<long>::get(&v67);
    v40 = v39;
    if ( v39 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x65B,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)(unsigned int)v39,
        v46);
    if ( v37 >= 0 && v40 < 0 )
      v37 = wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)0x65F,
              (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
              (const char *)(unsigned int)v40,
              v46);
    if ( (*v11 & 0x20) != 0 )
    {
      v41 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 72) + 40LL))(*((_QWORD *)v3 + 72));
      v42 = v41;
      if ( v41 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x664,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
          (const char *)(unsigned int)v41,
          v46);
      if ( v37 >= 0 && v42 < 0 )
        v37 = wil::details::in1diag3::Log_Hr(
                retaddr,
                (void *)0x668,
                (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
                (const char *)(unsigned int)v42,
                v46);
    }
  }
  *(_BYTE *)(*((_QWORD *)v3 + 58) + 848LL) = 0;
  v56 = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(*(_QWORD *)v56 + 16LL));
  Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
    (Vml::VmPerfTraceOperation *)v79,
    &VMWP_PERF_MIGRATION_SOURCE_MOVE_STOP,
    (__int64)&v56);
  *v38 = v81;
  *((_QWORD *)v3 + 78) = GetTickCount64() - TickCount64;
  std::_Optional_destruct_base<std::promise<long>,0>::~_Optional_destruct_base<std::promise<long>,0>(v70);
  std::_Optional_destruct_base<std::promise<long>,0>::~_Optional_destruct_base<std::promise<long>,0>(v68);
  std::_State_manager<int>::~_State_manager<int>(&v67);
  std::wstring::_Tidy_deallocate(v85);
  std::wstring::_Tidy_deallocate(v78);
  std::wstring::_Tidy_deallocate(v82);
  return (unsigned int)v37;
}

```

## disassembly

```asm
0x1400ce948  mov     r11, rsp
0x1400ce94b  mov     [r11+18h], rbx
0x1400ce94f  mov     [r11+20h], rsi
0x1400ce953  push    rdi
0x1400ce954  push    r12
0x1400ce956  push    r13
0x1400ce958  push    r14
0x1400ce95a  push    r15
0x1400ce95c  sub     rsp, 340h
0x1400ce963  mov     rax, cs:__security_cookie
0x1400ce96a  xor     rax, rsp
0x1400ce96d  mov     [rsp+368h+var_38], rax
0x1400ce975  mov     r14, rdx
0x1400ce978  mov     [rsp+368h+var_2C0], rdx
0x1400ce980  mov     rsi, rcx
0x1400ce983  mov     [rsp+368h+var_2F8], rcx
0x1400ce988  mov     [rsp+368h+var_300], rcx
0x1400ce98d  mov     [rsp+368h+var_2B8], rdx
0x1400ce995  xor     edi, edi
0x1400ce997  mov     [rsp+368h+var_334], edi
0x1400ce99b  xorps   xmm0, xmm0
0x1400ce99e  movups  xmmword ptr [rsp+368h+var_258.Data1], xmm0
0x1400ce9a6  lea     rbx, [rcx+19Ch]
0x1400ce9ad  lea     r9, [r11-258h]; struct _GUID *
0x1400ce9b4  mov     r8, rbx; struct _GUID *
0x1400ce9b7  lea     r15, ?g_MigrationPerfTrace@@3VVmPerfTraceComponent@Vml@@A; Vml::VmPerfTraceComponent g_MigrationPerfTrace
0x1400ce9be  mov     rdx, r15; struct Vml::VmPerfTraceComponent *
0x1400ce9c1  lea     rcx, [r11-178h]; this
0x1400ce9c8  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x1400ce9cd  nop
0x1400ce9ce  xorps   xmm0, xmm0
0x1400ce9d1  movups  xmmword ptr [rsp+368h+var_258.Data1], xmm0
0x1400ce9d9  lea     r9, [rsp+368h+var_258]; struct _GUID *
0x1400ce9e1  mov     r8, rbx; struct _GUID *
0x1400ce9e4  mov     rdx, r15; struct Vml::VmPerfTraceComponent *
0x1400ce9e7  lea     rcx, [rsp+368h+var_1E8]; this
0x1400ce9ef  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x1400ce9f4  nop
0x1400ce9f5  xorps   xmm0, xmm0
0x1400ce9f8  movups  xmmword ptr [rsp+368h+var_258.Data1], xmm0
0x1400cea00  lea     r9, [rsp+368h+var_258]; struct _GUID *
0x1400cea08  mov     r8, rbx; struct _GUID *
0x1400cea0b  mov     rdx, r15; struct Vml::VmPerfTraceComponent *
0x1400cea0e  lea     rcx, [rsp+368h+var_A8]; this
0x1400cea16  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x1400cea1b  nop
0x1400cea1c  mov     rax, [r14]
0x1400cea1f  mov     [rsp+368h+var_160], rax
0x1400cea27  lea     rax, [rsi+10h]
0x1400cea2b  mov     [rsp+368h+var_2E8], rax
0x1400cea33  mov     rbx, rax
0x1400cea36  mov     [rsp+368h+var_2F0], rax
0x1400cea3b  mov     rcx, [rax]
0x1400cea3e  add     rcx, 10h; this
0x1400cea42  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400cea47  mov     [rsp+368h+var_330], rax
0x1400cea4c  lea     r8, [rsp+368h+var_330]
0x1400cea51  lea     rdx, VMWP_PERF_MIGRATION_SOURCE_MOVE_START; EventDescriptor
0x1400cea58  lea     rcx, [rsp+368h+var_178]; this
0x1400cea60  call    ??$BeginOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::BeginOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x1400cea65  call    cs:__imp_GetTickCount64
0x1400cea6c  nop     dword ptr [rax+rax+00h]
0x1400cea71  mov     [rsp+368h+var_2B0], rax
0x1400cea79  xorps   xmm0, xmm0
0x1400cea7c  movups  xmmword ptr [rsp+368h+var_258.Data1], xmm0
0x1400cea84  mov     qword ptr [rsp+368h+var_258.Data1], rdi
0x1400cea8c  mov     [rsp+368h+var_258.Data4], dil
0x1400cea94  lea     rcx, [rsp+368h+var_248]
0x1400cea9c  call    ??0?$promise@J@std@@QEAA@XZ; std::promise<long>::promise<long>(void)
0x1400ceaa1  lea     r12d, [rdi+1]
0x1400ceaa5  mov     [rsp+368h+var_230], r12b
0x1400ceaad  lea     rcx, [rsp+368h+var_228]
0x1400ceab5  call    ??0?$promise@J@std@@QEAA@XZ; std::promise<long>::promise<long>(void)
0x1400ceaba  mov     [rsp+368h+var_210], r12b
0x1400ceac2  xorps   xmm0, xmm0
0x1400ceac5  xor     eax, eax
0x1400ceac7  movups  [rsp+368h+var_208], xmm0
0x1400ceacf  mov     [rsp+368h+var_1F8], rax
0x1400cead7  mov     [rsp+368h+var_330], rsi
0x1400ceadc  lea     rax, ?SendVmState@WorkerTaskMigrationSource@@AEAAJV?$future@J@std@@0@Z; WorkerTaskMigrationSource::SendVmState(std::future<long>,std::future<long>)
0x1400ceae3  mov     [rsp+368h+var_2E0], rax
0x1400ceaeb  mov     [rsp+368h+var_2D8], rdi
0x1400ceaf3  lea     rdx, [rsp+368h+var_330]
0x1400ceaf8  lea     rcx, [rsp+368h+var_2D0]
0x1400ceb00  call    ??$?0PEAVWorkerTaskMigrationSource@@AEBU?$_Ph@$00@std@@AEBU?$_Ph@$01@2@$0A@@?$tuple@PEAVWorkerTaskMigrationSource@@U?$_Ph@$00@std@@U?$_Ph@$01@3@@std@@QEAA@$$QEAPEAVWorkerTaskMigrationSource@@AEBU?$_Ph@$00@1@AEBU?$_Ph@$01@1@@Z; std::tuple<WorkerTaskMigrationSource *,std::_Ph<1>,std::_Ph<2>>::tuple<WorkerTaskMigrationSource *,std::_Ph<1>,std::_Ph<2>>(WorkerTaskMigrationSource * &&,std::_Ph<1> const &,std::_Ph<2> const &)
0x1400ceb05  lea     rdx, [rsp+368h+var_2E0]
0x1400ceb0d  lea     rcx, [rsp+368h+var_208]
0x1400ceb15  call    ??$?0V?$_Binder@U_Unforced@std@@P8WorkerTaskMigrationSource@@EAAJV?$future@J@2@0@_EPEAV3@AEBU?$_Ph@$00@2@AEBU?$_Ph@$01@2@@std@@$0A@@?$packaged_task@$$A6AJV?$future@J@std@@0@Z@std@@QEAA@$$QEAV?$_Binder@U_Unforced@std@@P8WorkerTaskMigrationSource@@EAAJV?$future@J@2@0@_EPEAV3@AEBU?$_Ph@$00@2@AEBU?$_Ph@$01@2@@1@@Z
0x1400ceb1a  nop
0x1400ceb1b  lea     rcx, [rsp+368h+var_208]
0x1400ceb23  call    ?_Get_state_for_future@?$_Promise@J@std@@QEAAAEAV?$_State_manager@J@2@XZ; std::_Promise<long>::_Get_state_for_future(void)
0x1400ceb28  mov     rax, [rax]
0x1400ceb2b  mov     byte ptr [rsp+368h+var_2D8], r12b
0x1400ceb33  test    rax, rax
0x1400ceb36  jz      short loc_1400CEB3D
0x1400ceb38  lock add [rax+8], r12d
0x1400ceb3d  mov     [rsp+368h+var_2E0], rdi
0x1400ceb45  mov     qword ptr [rsp+368h+var_258.Data1], rax
0x1400ceb4d  mov     [rsp+368h+var_258.Data4], r12b
0x1400ceb55  lea     rcx, [rsp+368h+var_2E0]
0x1400ceb5d  call    ??1?$_State_manager@H@std@@QEAA@XZ; std::_State_manager<int>::~_State_manager<int>(void)
0x1400ceb62  lea     rcx, [rsp+368h+var_228]
0x1400ceb6a  call    ?value@?$optional@URuntimeStatistics@EndpointTransferRuntimeStats@@@std@@QEGAAAEAURuntimeStatistics@EndpointTransferRuntimeStats@@XZ; std::optional<EndpointTransferRuntimeStats::RuntimeStatistics>::value(void)
0x1400ceb6f  lea     rdx, [rsp+368h+var_310]
0x1400ceb74  mov     rcx, rax
0x1400ceb77  call    ?get_future@?$packaged_task@$$A6AJXZ@std@@QEAA?AV?$future@J@2@XZ; std::packaged_task<long (void)>::get_future(void)
0x1400ceb7c  mov     r14, rax
0x1400ceb7f  lea     rcx, [rsp+368h+var_248]
0x1400ceb87  call    ?value@?$optional@URuntimeStatistics@EndpointTransferRuntimeStats@@@std@@QEGAAAEAURuntimeStatistics@EndpointTransferRuntimeStats@@XZ; std::optional<EndpointTransferRuntimeStats::RuntimeStatistics>::value(void)
0x1400ceb8c  lea     rdx, [rsp+368h+var_320]
0x1400ceb91  mov     rcx, rax
0x1400ceb94  call    ?get_future@?$packaged_task@$$A6AJXZ@std@@QEAA?AV?$future@J@2@XZ; std::packaged_task<long (void)>::get_future(void)
0x1400ceb99  nop
0x1400ceb9a  mov     r9, r14
0x1400ceb9d  mov     r8, rax
0x1400ceba0  lea     rdx, [rsp+368h+var_208]
0x1400ceba8  lea     rcx, [rsp+368h+var_2E0]
0x1400cebb0  call    ??$_Start@V?$packaged_task@$$A6AJV?$future@J@std@@0@Z@std@@V?$future@J@2@V32@@thread@std@@AEAAX$$QEAV?$packaged_task@$$A6AJV?$future@J@std@@0@Z@1@$$QEAV?$future@J@1@1@Z; std::thread::_Start<std::packaged_task<long (std::future<long>,std::future<long>)>,std::future<long>,std::future<long>>(std::packaged_task<long (std::future<long>,std::future<long>)> &&,std::future<long> &&,std::future<long> &&)
0x1400cebb5  nop
0x1400cebb6  lea     rcx, [rsp+368h+var_2E0]; this
0x1400cebbe  call    ?detach@thread@std@@QEAAXXZ; std::thread::detach(void)
0x1400cebc3  nop
0x1400cebc4  lea     rcx, [rsp+368h+var_2E0]; this
0x1400cebcc  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x1400cebd1  nop
0x1400cebd2  lea     rcx, [rsp+368h+var_320]
0x1400cebd7  call    ??1?$_State_manager@H@std@@QEAA@XZ; std::_State_manager<int>::~_State_manager<int>(void)
0x1400cebdc  nop
0x1400cebdd  lea     rcx, [rsp+368h+var_310]
0x1400cebe2  call    ??1?$_State_manager@H@std@@QEAA@XZ; std::_State_manager<int>::~_State_manager<int>(void)
0x1400cebe7  mov     rcx, [rbx]
0x1400cebea  add     rcx, 10h; this
0x1400cebee  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400cebf3  mov     [rsp+368h+var_330], rax
0x1400cebf8  lea     r8, [rsp+368h+var_330]
0x1400cebfd  lea     rdx, VMWP_PERF_MIGRATION_SOURCE_PAUSE_VM_START; EventDescriptor
0x1400cec04  lea     rcx, [rsp+368h+var_1E8]; this
0x1400cec0c  call    ??$BeginOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::BeginOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x1400cec11  movdqa  xmm0, cs:__xmm@00000000000000000000000200000000
0x1400cec19  movdqa  [rsp+368h+var_2A8], xmm0
0x1400cec22  mov     dword ptr [rsp+368h+var_2A8+8], edi
0x1400cec29  mov     byte ptr [rsp+368h+var_2A8+0Ch], dil
0x1400cec31  xor     edx, edx; Val
0x1400cec33  lea     r8d, [rdx+40h]; Size
0x1400cec37  lea     rcx, [rsp+368h+var_298]; void *
0x1400cec3f  call    memset_0
0x1400cec44  xorps   xmm0, xmm0
0x1400cec47  movdqa  [rsp+368h+var_298], xmm0
0x1400cec50  xorps   xmm1, xmm1
0x1400cec53  movdqa  [rsp+368h+var_288], xmm1
0x1400cec5c  movdqa  [rsp+368h+var_278], xmm0
0x1400cec65  mov     [rsp+368h+var_268], rdi
0x1400cec6d  mov     [rsp+368h+var_260], edi
0x1400cec74  lea     rdx, [rsp+368h+var_2A8]
0x1400cec7c  lea     rcx, [rsp+368h+var_108]
0x1400cec84  call    ??$?0UOperationSystemMigrationNotificationInfo@System@Responses@Schema@@$0A@$0A@@?$variant@Umonostate@std@@UWorkerCoreNotification@System@Responses@Compute@@UOperationSystemMigrationNotificationInfo@45Schema@@@std@@QEAA@$$QEAUOperationSystemMigrationNotificationInfo@System@Responses@Schema@@@Z; std::variant<std::monostate,Compute::Responses::System::WorkerCoreNotification,Schema::Responses::System::OperationSystemMigrationNotificationInfo>::variant<std::monostate,Compute::Responses::System::WorkerCoreNotification,Schema::Responses::System::OperationSystemMigrationNotificationInfo>(Schema::Responses::System::OperationSystemMigrationNotificationInfo &&)
0x1400cec89  nop
0x1400cec8a  lea     rax, [rsi+240h]
0x1400cec91  mov     [rsp+368h+var_2E0], rax
0x1400cec99  mov     rcx, [rax]
0x1400cec9c  mov     rax, [rcx]
0x1400cec9f  lea     rdx, [rsp+368h+var_108]
0x1400ceca7  mov     rax, [rax+80h]
0x1400cecae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cecb3  mov     edx, 9
0x1400cecb8  lea     r8d, [rdx+11h]
0x1400cecbc  mov     rcx, [rbx]
0x1400cecbf  call    ?SetState@VirtualMachine@@QEAAHW4_VM_STATE@@W4_VM_STATE_REASON_CODE@@@Z; VirtualMachine::SetState(_VM_STATE,_VM_STATE_REASON_CODE)
0x1400cecc4  test    eax, eax
0x1400cecc6  jnz     short loc_1400CED05
0x1400cecc8  mov     ebx, 41E2h
0x1400ceccd  mov     ecx, ebx
0x1400ceccf  call    VmlIsDebugTraceEnabled
0x1400cecd4  test    eax, eax
0x1400cecd6  jz      short loc_1400CECE6
0x1400cecd8  lea     rdx, off_1402DB060; "Failed to set state of VM to stopping."
0x1400cecdf  mov     ecx, ebx
0x1400cece1  call    VmlDebugTraceEx
0x1400cece6  mov     rcx, [rsp+368h]; this
0x1400cecee  mov     r9d, 8000FFFFh; char *
0x1400cecf4  lea     r8, aOnecoreVmWorke_0; "onecore\\vm\\worker\\migration\\workert"...
0x1400cecfb  mov     edx, 570h; void *
0x1400ced00  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400ced05  cmp     dword ptr [rsi+228h], 2
0x1400ced0c  jz      short loc_1400CED1A
0x1400ced0e  lea     r14, [rsi+24Ch]
0x1400ced15  jmp     loc_1400CEE2B
0x1400ced1a  mov     rcx, [rbx]
0x1400ced1d  lea     rax, [rcx+480h]
0x1400ced24  mov     [rsp+368h+var_330], rax
0x1400ced29  add     rcx, 10h; this
0x1400ced2d  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400ced32  mov     [rsp+368h+var_328], rax
0x1400ced37  lea     rax, [rsp+368h+var_330]
0x1400ced3c  mov     qword ptr [rsp+368h+var_348], rax; int
0x1400ced41  lea     r9, [rsp+368h+var_328]
0x1400ced46  mov     edx, r12d; unsigned int
0x1400ced49  lea     rcx, MSVM_WORKER_MIGRATION_ENTER_BLACKOUT; EventDescriptor
0x1400ced50  call    ??$VmEventWrite@PEBGPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@$$QEAPEBG2@Z; VmEventWrite<ushort const *,ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const * &&,ushort const * &&)
0x1400ced55  call    ?CurrentFileTime@@YA?AU_FILETIME@@XZ; CurrentFileTime(void)
0x1400ced5a  mov     rdx, rax
0x1400ced5d  mov     rcx, 0FFFFFFFF00000000h
0x1400ced67  and     rdx, rcx
0x1400ced6a  mov     ecx, eax
0x1400ced6c  add     rdx, rcx
0x1400ced6f  mov     [rsi+328h], rdx
0x1400ced76  lea     r14, [rsi+24Ch]
0x1400ced7d  mov     edx, [r14]
0x1400ced80  and     edx, 20h
0x1400ced83  or      edx, 11h
0x1400ced86  mov     r8d, 12h
0x1400ced8c  mov     rcx, [rbx]
0x1400ced8f  call    ?StopVm@VirtualMachine@@QEAAXIW4__MIDL___MIDL_itf_vmbservices_0000_0011_0003@@@Z; VirtualMachine::StopVm(uint,__MIDL___MIDL_itf_vmbservices_0000_0011_0003)
0x1400ced94  cmp     [rsi+199h], dil
0x1400ced9b  jz      short loc_1400CEE06
0x1400ced9d  mov     rax, [rbx]
0x1400ceda0  mov     rcx, [rax+400h]
0x1400ceda7  add     rcx, 18h
0x1400cedab  mov     rax, [rcx]
0x1400cedae  mov     rax, [rax]
0x1400cedb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cedb6  mov     rcx, rax
0x1400cedb9  call    cs:__imp_VidTdxExportPause
0x1400cedc0  nop     dword ptr [rax+rax+00h]
0x1400cedc5  test    eax, eax
0x1400cedc7  jnz     short loc_1400CEE06
0x1400cedc9  mov     ebx, 41E2h
0x1400cedce  mov     ecx, ebx
0x1400cedd0  call    VmlIsDebugTraceEnabled
0x1400cedd5  test    eax, eax
0x1400cedd7  jz      short loc_1400CEDE7
0x1400cedd9  lea     rdx, off_1402DADF8; "Failed to set export pause for TD."
0x1400cede0  mov     ecx, ebx
0x1400cede2  call    VmlDebugTraceEx
0x1400cede7  mov     rcx, [rsp+368h]; this
0x1400cedef  mov     r9d, 8000FFFFh; char *
0x1400cedf5  lea     r8, aOnecoreVmWorke_0; "onecore\\vm\\worker\\migration\\workert"...
0x1400cedfc  mov     edx, 58Dh; void *
0x1400cee01  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cee06  lea     rcx, [rsi+4C8h]
0x1400cee0d  call    ?is_valid@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEBA_NXZ
0x1400cee12  test    al, al
0x1400cee14  jz      short loc_1400CEE2B
0x1400cee16  mov     rax, [rcx]
0x1400cee19  test    rax, rax
0x1400cee1c  jz      short loc_1400CEE23
0x1400cee1e  mov     rcx, [rax]
0x1400cee21  jmp     short loc_1400CEE26
0x1400cee23  mov     rcx, rdi; this
0x1400cee26  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x1400cee2b  mov     [rsp+368h+var_330], r14
0x1400cee30  lea     r13, [rsi+22Ch]
0x1400cee37  mov     [rsp+368h+var_320], r13
0x1400cee3c  mov     dword ptr [r13+0], 5
0x1400cee44  mov     rax, [rsi+1D0h]
0x1400cee4b  mov     [rax+350h], r12b
0x1400cee52  mov     rcx, [rbx]
0x1400cee55  add     rcx, 10h; this
0x1400cee59  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400cee5e  mov     [rsp+368h+var_328], rax
0x1400cee63  lea     r8, [rsp+368h+var_328]; __int64
0x1400cee68  lea     rdx, VMWP_PERF_MIGRATION_SOURCE_PAUSE_VM_STOP; EventDescriptor
0x1400cee6f  lea     rcx, [rsp+368h+var_1E8]; this
0x1400cee77  call    ??$EndOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::EndOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x1400cee7c  test    byte ptr [r14], 20h
0x1400cee80  jz      short loc_1400CEEBD
0x1400cee82  mov     rcx, [rbx]
0x1400cee85  lea     rax, [rcx+480h]
0x1400cee8c  mov     [rsp+368h+var_328], rax
0x1400cee91  add     rcx, 10h; this
0x1400cee95  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400cee9a  mov     [rsp+368h+var_310], rax
0x1400cee9f  lea     rax, [rsp+368h+var_328]
0x1400ceea4  mov     qword ptr [rsp+368h+var_348], rax; int
0x1400ceea9  lea     r9, [rsp+368h+var_310]
0x1400ceeae  mov     edx, r12d; unsigned int
0x1400ceeb1  lea     rcx, MSVM_WORKER_MIGRATION_SOURCE_PAUSE_VM_STOP; EventDescriptor
0x1400ceeb8  call    ??$VmEventWrite@PEBGPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@$$QEAPEBG2@Z; VmEventWrite<ushort const *,ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const * &&,ushort const * &&)
0x1400ceebd  lea     rcx, [rsi+190h]; this
0x1400ceec4  call    ?CheckCancel@WorkerTaskMigrationSource@@UEAAJXZ; WorkerTaskMigrationSource::CheckCancel(void)
0x1400ceec9  mov     rcx, [rsp+368h]; this
0x1400ceed1  test    eax, eax
0x1400ceed3  jns     short loc_1400CEEE9
0x1400ceed5  mov     r9d, eax; char *
0x1400ceed8  lea     r8, aOnecoreVmWorke_0; "onecore\\vm\\worker\\migration\\workert"...
0x1400ceedf  mov     edx, 5B3h; void *
0x1400ceee4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400ceee9  xorps   xmm0, xmm0
0x1400ceeec  movups  xmmword ptr [rsp+368h+var_310], xmm0
0x1400ceef1  lea     r15, [rsi+1C0h]
0x1400ceef8  mov     [rsp+368h+var_328], r15
0x1400ceefd  mov     r8d, r12d
0x1400cef00  mov     rdx, [r15]
0x1400cef03  lea     rcx, [rsp+368h+var_310]
0x1400cef08  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x1400cef0d  nop
0x1400cef0e  mov     r9d, dword ptr [rsp+368h+var_310+8]; char *
0x1400cef13  mov     rcx, [rsp+368h]; this
0x1400cef1b  test    r9d, r9d
0x1400cef1e  jns     short loc_1400CEF31
  ... truncated ...
```
