# WorkerTaskMigrationTarget::RestoreWorkerProcess(IVmSimpleTask *)

- ea: `0x1400cce94`
- end: `0x1400cda10`
- name: `?RestoreWorkerProcess@WorkerTaskMigrationTarget@@AEAAJPEAUIVmSimpleTask@@@Z`
- size: `2940`
- prototype: `__int64 __fastcall(WorkerTaskMigrationTarget *__hidden this, struct IVmSimpleTask *)`
- caller_count: `1`
- callee_count: `37`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140223ac4`

## callees

- `0x1400222f8`
- `0x14002ecd0`
- `0x140030100`
- `0x140031c88`
- `0x140042240`
- `0x140054508`
- `0x140054630`
- `0x1400549dc`
- `0x140062e00`
- `0x14006af38`
- `0x140079e6c`
- `0x14007a72c`
- `0x14008ff68`
- `0x140090390`
- `0x1400941dc`
- `0x1400b3810`
- `0x1400b7ae8`
- `0x1400cc1b4`
- `0x1400cc1e4`
- `0x1400ccb00`
- `0x1400ccc40`
- `0x1400ccd74`
- `0x1400cce94`
- `0x1400ce7c4`
- `0x1400ce884`
- `0x1400eb528`
- `0x1400ed0f8`
- `0x1400f5994`
- `0x140111070`
- `0x14011a084`
- `0x140132940`
- `0x1401eb9e0`
- `0x1402180e8`
- `0x1402215a4`
- `0x140222c74`
- `0x14022e4d0`
- `0x1402c2010`

## import_xrefs

- `vid!VidChangePartitionLifeState` at `0x1400cd215`
- `vid!VidChangePartitionLifeState` at `0x1400cd269`
- `vid!VidChangePartitionLifeState` at `0x1400cd215`
- `vid!VidChangePartitionLifeState` at `0x1400cd269`

## string_xrefs

- `0x1400ccf20`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400ccffd`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd025`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd142`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd198`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd1e0`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd323`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd3f7`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd4b1`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd4ed`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd597`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd5fa`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd868`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x1400cd892`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`

## pseudocode

```c
__int64 __fastcall WorkerTaskMigrationTarget::RestoreWorkerProcess(
        WorkerTaskMigrationTarget *this,
        struct IVmSimpleTask *a2)
{
  WorkerTaskMigrationTarget *v2; // r14
  VirtualMachine **v3; // rsi
  int v4; // eax
  int v5; // eax
  struct VmRepository **v6; // r12
  VirtualMachine *v7; // rbx
  __int64 v8; // rax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rax
  unsigned int v14; // r9d
  int v15; // r13d
  __int64 *v16; // r13
  __int64 v17; // rdx
  __int64 v18; // rax
  int v19; // r13d
  int v20; // r13d
  int v21; // eax
  __int64 v22; // r13
  int started; // eax
  __int64 (__fastcall *v24)(__int64, __int64, __int64, _QWORD); // rbx
  __int64 v25; // rax
  _QWORD *v26; // rax
  VirtualMachine *v27; // rcx
  const char *v28; // r9
  HyperVRepository *v29; // rbx
  int v30; // eax
  const char *v31; // r9
  const char *v32; // r9
  const char *v33; // r9
  VirtualMachine *v34; // rcx
  const struct Vml::ExceptionTraceParameters *v35; // r8
  int v37; // [rsp+20h] [rbp-288h]
  int v38; // [rsp+20h] [rbp-288h]
  __int64 VmName; // [rsp+30h] [rbp-278h] BYREF
  __int64 v40; // [rsp+38h] [rbp-270h] BYREF
  int HResultFromThrownExceptionAndTrace; // [rsp+40h] [rbp-268h]
  char *v42[2]; // [rsp+48h] [rbp-260h] BYREF
  VirtualMachine **v43; // [rsp+58h] [rbp-250h]
  WorkerTaskMigrationTarget *v44; // [rsp+60h] [rbp-248h]
  struct _GUID v45; // [rsp+68h] [rbp-240h] BYREF
  unsigned __int64 v46; // [rsp+78h] [rbp-230h]
  __int64 (__fastcall *v47)(__int64, __int64, __int64, _QWORD); // [rsp+80h] [rbp-228h]
  _BYTE *v48; // [rsp+88h] [rbp-220h]
  WorkerTaskMigrationTarget *v49; // [rsp+90h] [rbp-218h]
  __int64 v50; // [rsp+98h] [rbp-210h]
  _DWORD v51[3]; // [rsp+A0h] [rbp-208h] BYREF
  char v52; // [rsp+ACh] [rbp-1FCh]
  _BYTE v53[64]; // [rsp+B0h] [rbp-1F8h] BYREF
  wchar_t Buffer[16]; // [rsp+F0h] [rbp-1B8h] BYREF
  __int64 v55; // [rsp+110h] [rbp-198h] BYREF
  __int64 v56; // [rsp+118h] [rbp-190h] BYREF
  _BYTE v57[12]; // [rsp+120h] [rbp-188h] BYREF
  int v58; // [rsp+12Ch] [rbp-17Ch]
  __int64 v59; // [rsp+138h] [rbp-170h]
  __int64 v60; // [rsp+140h] [rbp-168h]
  _BYTE v61[72]; // [rsp+148h] [rbp-160h] BYREF
  _QWORD v62[4]; // [rsp+190h] [rbp-118h] BYREF
  _BYTE v63[40]; // [rsp+1B0h] [rbp-F8h] BYREF
  _BYTE v64[72]; // [rsp+1D8h] [rbp-D0h] BYREF
  _BYTE v65[96]; // [rsp+220h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  try
  {
    v2 = this;
    v44 = this;
    HResultFromThrownExceptionAndTrace = 0;
    v3 = (VirtualMachine **)((char *)this + 16);
    if ( (*((_BYTE *)this + 480) & 0x20) != 0 && !(unsigned int)VirtualMachine::SetState(*v3, 1, 19) )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
        VmlDebugTraceEx(16866, &off_1402DB310);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5AB,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)0x8000FFFFLL,
        v37);
    }
    v43 = v3;
    v45 = 0;
    Vml::VmPerfTraceOperation::VmPerfTraceOperation(
      (Vml::VmPerfTraceOperation *)v63,
      (struct Vml::VmPerfTraceComponent *)&g_MigrationPerfTrace,
      (const struct _GUID *)((char *)v2 + 412),
      &v45);
    v45 = 0;
    Vml::VmPerfTraceOperation::VmPerfTraceOperation(
      (Vml::VmPerfTraceOperation *)v57,
      (struct Vml::VmPerfTraceComponent *)&g_MigrationPerfTrace,
      (const struct _GUID *)((char *)v2 + 412),
      &v45);
    VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v3 + 16));
    Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v63,
      &VMWP_PERF_MIGRATION_TARGET_RESTORE_WORKER_START);
    v50 = 1;
    v48 = v63;
    v49 = v2;
    v4 = WorkerTaskMigrationTarget::CheckCancel(v2);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5BE,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v4,
        v37);
    v5 = WorkerTaskMigrationTarget::PrepareVmForRestore(v2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5C1,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v5,
        v37);
    VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v3 + 16));
    Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v57,
      &VMWP_PERF_MIGRATION_TARGET_RESTORE_VSM_START);
    v6 = (struct VmRepository **)((char *)v2 + 568);
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)*v3 + 128) + 264LL))(
      *((_QWORD *)*v3 + 128),
      *((_QWORD *)v2 + 71));
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)v2 + 58) + 408LL))(
      *((_QWORD *)v2 + 58),
      *((_QWORD *)v2 + 71),
      0);
    VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v3 + 16));
    Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v57,
      &VMWP_PERF_MIGRATION_TARGET_RESTORE_VSM_STOP,
      (__int64)&VmName);
    v59 = 0;
    v60 = 0;
    v58 = 1;
    VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v3 + 16));
    Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v57,
      &VMWP_PERF_MIGRATION_TARGET_RESTORE_RUNTIME_CHANGES_START);
    v7 = *v3;
    v8 = Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(
           &VmName,
           (char *)v2 + 568);
    v9 = VirtualMachine::ApplyMigrationRuntimeStateChanges(v7, v8);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5DB,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v9,
        v37);
    VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v3 + 16));
    Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v57,
      &VMWP_PERF_MIGRATION_TARGET_RESTORE_RUNTIME_CHANGES_STOP,
      (__int64)&VmName);
    v10 = WorkerTaskMigrationTarget::RestoreVmb(v2, *v6);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5E4,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v10,
        v37);
    VmName = (__int64)v2 + 448;
    *((_DWORD *)v2 + 112) = 6;
    if ( *((_BYTE *)v2 + 409) )
    {
      v11 = WorkerTaskMigrationTarget::DoTdxImportEnd(v2);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5F3,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v11,
          v37);
      v12 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)*v3 + 128) + 24LL))(*((_QWORD *)*v3 + 128) + 24LL);
      if ( !(unsigned int)VidChangePartitionLifeState(v12, 0, 0, 0) && (unsigned int)VmlIsDebugTraceEnabled(16866) )
        VmlDebugTraceEx(16866, &off_1402DB4F0);
      v13 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)*v3 + 128) + 24LL))(*((_QWORD *)*v3 + 128) + 24LL);
      if ( !(unsigned int)VidChangePartitionLifeState(v13, 2, 0, 0) && (unsigned int)VmlIsDebugTraceEnabled(16866) )
        VmlDebugTraceEx(16866, &off_1402DB220);
    }
    v59 = 0;
    v60 = 0;
    v58 = 1;
    v40 = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v3 + 16));
    Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v57,
      &VMWP_PERF_MIGRATION_TARGET_MOVE_RESTORE_PARTITION_START);
    v15 = VirtualMachine::RestorePartitionStates(*v3, *v6, 0, v14);
    if ( v15 < 0 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
        VmlDebugTraceWithError(16866, &off_1402DB2A0, (unsigned int)v15);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x624,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v15,
        v37);
    }
    v16 = (__int64 *)*((_QWORD *)*v3 + 124);
    v17 = *v16;
    if ( *((_BYTE *)*v3 + 2665) )
      v55 = (*(__int64 (__fastcall **)(__int64 *))(v17 + 520))(v16);
    else
      v55 = (*(__int64 (__fastcall **)(__int64 *))(v17 + 512))(v16);
    v40 = *((_QWORD *)*v3 + 132);
    v47 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v40 + 24LL);
    v18 = (*(__int64 (__fastcall **)(__int64 *))(*v16 + 528))(v16);
    v19 = v47(v40, v55, v18, 0);
    if ( v19 < 0 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
        VmlDebugTraceWithError(16866, &off_1402DB3A0, (unsigned int)v19);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x63A,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v19,
        v37);
    }
    v40 = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v3 + 16));
    Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v57,
      &VMWP_PERF_MIGRATION_TARGET_MOVE_RESTORE_PARTITION_STOP,
      (__int64)&v40);
    v59 = 0;
    v60 = 0;
    v58 = 1;
    Vml::VmPerfTraceOperation::BeginOperation<>(
      (Vml::VmPerfTraceOperation *)v57,
      &VMWP_PERF_MIGRATION_TARGET_MOVE_RESTORE_METRICS_START);
    v20 = (*(__int64 (__fastcall **)(_QWORD, struct VmRepository *))(**((_QWORD **)*v3 + 133) + 40LL))(
            *((_QWORD *)*v3 + 133),
            *v6);
    if ( v20 < 0 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
        VmlDebugTraceWithError(16866, &off_1402DB258, (unsigned int)v20);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x64A,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v20,
        v37);
    }
    Vml::VmPerfTraceOperation::EndOperation<>(
      (Vml::VmPerfTraceOperation *)v57,
      &VMWP_PERF_MIGRATION_TARGET_MOVE_RESTORE_METRICS_STOP);
    v21 = WorkerTaskMigrationTarget::CheckCancel(v2);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x654,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v21,
        v37);
    *(_DWORD *)VmName = 7;
    v59 = 0;
    v60 = 0;
    v58 = 1;
    v40 = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)*v3 + 16));
    Vml::VmPerfTraceOperation::BeginOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v57,
      &VMWP_PERF_MIGRATION_TARGET_MOVE_RESUME_VM_START);
    *(_QWORD *)&v45.Data1 = (char *)v2 + 432;
    if ( !*(_DWORD *)(*((_QWORD *)v2 + 54) + 88LL) )
    {
      v22 = (__int64)v3;
      v40 = (__int64)v3;
      started = VirtualMachine::StartVm(*v3, 32, 15);
      if ( started < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x662,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)started,
          v37);
      try
      {
        v24 = (__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD))CurrentFileTime();
        v47 = v24;
        std::wstring::wstring(v62, L"n/a");
        *(_OWORD *)v42 = 0;
        VmRepositoryAutoLock::VmRepositoryAutoLock(v42, *v6, 0);
        if ( SLODWORD(v42[1]) < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x67A,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            (const char *)LODWORD(v42[1]),
            v37);
        v46 = 0;
        v56 = 0;
        if ( (int)SavedStateRepository::ReadInteger(*v6, L"/migration/blackout_start_timestamp", &v56) >= 0 )
        {
          v46 = ((unsigned __int64)HIDWORD(v47) << 32) + (unsigned int)v24;
          v55 = 0;
          SavedStateRepository::ReadInteger(*v6, L"/migration/clock_drift", &v55);
          v46 += v55 - v56;
          v25 = Vml::FormatString(Buffer);
          std::wstring::operator=(v62, v25);
          std::wstring::_Tidy_deallocate(Buffer);
        }
        VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v42);
        v26 = v62;
        if ( v62[3] > 7u )
          v26 = (_QWORD *)v62[0];
        v56 = (__int64)v26;
        v27 = *v3;
        v55 = (__int64)*v3 + 1152;
        v42[0] = (char *)VirtualMachine::GetVmName((VirtualMachine *)((char *)v27 + 16));
        VmEventWrite<unsigned short const *,unsigned short const *,unsigned short const *>(
          &MSVM_WORKER_MIGRATION_LEAVE_BLACKOUT,
          (__int64)&v55,
          (__int64)&v56);
        v42[0] = (char *)(v46 / 0x2710);
        v42[1] = (char *)__PAIR64__(HIDWORD(v47), (unsigned int)v24);
        v51[0] = 1;
        v51[1] = 4;
        v51[2] = 1;
        v52 = 1;
        Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
          v53,
          v42);
        std::variant<std::monostate,Compute::Responses::System::WorkerCoreNotification,Schema::Responses::System::OperationSystemMigrationNotificationInfo>::variant<std::monostate,Compute::Responses::System::WorkerCoreNotification,Schema::Responses::System::OperationSystemMigrationNotificationInfo>(
          v65,
          v51);
        (*(void (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)v2 + 57) + 128LL))(*((_QWORD *)v2 + 57), v65);
        std::_Variant_destroy_layer_<std::monostate,Compute::Responses::System::WorkerCoreNotification,Schema::Responses::System::OperationSystemMigrationNotificationInfo>::~_Variant_destroy_layer_<std::monostate,Compute::Responses::System::WorkerCoreNotification,Schema::Responses::System::OperationSystemMigrationNotificationInfo>(v65);
        Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::~DelayedBase<void,Marshal::Details::DelayedJsonTraits>(v53);
        std::wstring::_Tidy_deallocate(v62);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x6AA,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          v28);
        v22 = v40;
        v2 = v44;
        v3 = v43;
      }
      try
      {
        v29 = *(HyperVRepository **)(*(_QWORD *)(*(_QWORD *)v22 + 1416LL) + 88LL);
        *(_OWORD *)v42 = 0;
        VmRepositoryAutoLock::VmRepositoryAutoLock(v42, v29, 1);
        if ( SLODWORD(v42[1]) < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6B7,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            (const char *)LODWORD(v42[1]),
            v38);
        v30 = HyperVRepository::Compact(v29, 1);
        if ( v30 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6B8,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            (const char *)(unsigned int)v30,
            v38);
        VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v42);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x6BA,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          v31);
        v22 = v40;
        v2 = v44;
        v3 = v43;
      }
      try
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)v22 + 1064LL) + 56LL))(*(_QWORD *)(*(_QWORD *)v22 + 1064LL));
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x6C0,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          v32);
        v2 = v44;
        v3 = v43;
      }
      try
      {
        VirtualDeviceMigrationTargetCollection::OnMigrationResumeCompletionAtTarget(*((VirtualDeviceMigrationTargetCollection **)v2
                                                                                    + 84));
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x6C9,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          v33);
        v2 = v44;
        v3 = v43;
      }
    }
    *(_DWORD *)VmName = 8;
    v34 = *v3;
    if ( *(_DWORD *)(**(_QWORD **)&v45.Data1 + 88LL) )
      VirtualMachine::SetState(v34, 3, 24);
    else
      VirtualMachine::SetState(v34, 2, 24);
    *(_QWORD *)&v45.Data1 = VirtualMachine::GetVmName((VirtualMachine *)((char *)*v3 + 16));
    Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v57,
      &VMWP_PERF_MIGRATION_TARGET_MOVE_RESUME_VM_STOP,
      (__int64)&v45);
    *(_QWORD *)&v45.Data1 = VirtualMachine::GetVmName((VirtualMachine *)(*((_QWORD *)v49 + 2) + 16LL));
    Vml::VmPerfTraceOperation::EndOperation<unsigned short const *>(
      (Vml::VmPerfTraceOperation *)v63,
      &VMWP_PERF_MIGRATION_TARGET_RESTORE_WORKER_STOP,
      (__int64)&v45);
    std::wstring::_Tidy_deallocate(v61);
    std::wstring::_Tidy_deallocate(v64);
  }
  catch ( ... )
  {
    HResultFromThrownExceptionAndTrace = Vml::GetHResultFromThrownExceptionAndTrace(
                                           (Vml *)0x41E2,
                                           (unsigned __int16)&off_1402DB300,
                                           v35);
    v2 = v44;
  }
  if ( a2 && HResultFromThrownExceptionAndTrace >= 0 )
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)v2 + 78) + 96LL))(*((_QWORD *)v2 + 78), 0, 0);
  return (unsigned int)HResultFromThrownExceptionAndTrace;
}

```

## disassembly

```asm
0x1400cce94  mov     [rsp+arg_10], rbx
0x1400cce99  mov     [rsp+arg_18], rsi
0x1400cce9e  mov     [rsp+arg_8], rdx
0x1400ccea3  push    r12
0x1400ccea5  push    r13
0x1400ccea7  push    r14
0x1400ccea9  sub     rsp, 290h
0x1400cceb0  mov     rax, cs:__security_cookie
0x1400cceb7  xor     rax, rsp
0x1400cceba  mov     [rsp+2A8h+var_28], rax
0x1400ccec2  mov     r14, rcx
0x1400ccec5  mov     [rsp+2A8h+var_248], rcx
0x1400cceca  mov     [rsp+2A8h+var_268], 0
0x1400cced2  lea     rsi, [rcx+10h]
0x1400cced6  test    byte ptr [rcx+1E0h], 20h
0x1400ccedd  jz      short loc_1400CCF31
0x1400ccedf  mov     edx, 1
0x1400ccee4  lea     r8d, [rdx+12h]
0x1400ccee8  mov     rcx, [rsi]
0x1400cceeb  call    ?SetState@VirtualMachine@@QEAAHW4_VM_STATE@@W4_VM_STATE_REASON_CODE@@@Z; VirtualMachine::SetState(_VM_STATE,_VM_STATE_REASON_CODE)
0x1400ccef0  test    eax, eax
0x1400ccef2  jnz     short loc_1400CCF31
0x1400ccef4  mov     ebx, 41E2h
0x1400ccef9  mov     ecx, ebx
0x1400ccefb  call    VmlIsDebugTraceEnabled
0x1400ccf00  test    eax, eax
0x1400ccf02  jz      short loc_1400CCF12
0x1400ccf04  lea     rdx, off_1402DB310; "Failed to set state of VM to starting."
0x1400ccf0b  mov     ecx, ebx
0x1400ccf0d  call    VmlDebugTraceEx
0x1400ccf12  mov     rcx, [rsp+2A8h]; this
0x1400ccf1a  mov     r9d, 8000FFFFh; char *
0x1400ccf20  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400ccf27  mov     edx, 5ABh; void *
0x1400ccf2c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400ccf31  mov     [rsp+2A8h+var_250], rsi
0x1400ccf36  xorps   xmm0, xmm0
0x1400ccf39  movups  xmmword ptr [rsp+2A8h+var_240.Data1], xmm0
0x1400ccf3e  lea     rbx, [r14+19Ch]
0x1400ccf45  lea     r9, [rsp+2A8h+var_240]; struct _GUID *
0x1400ccf4a  mov     r8, rbx; struct _GUID *
0x1400ccf4d  lea     rdx, ?g_MigrationPerfTrace@@3VVmPerfTraceComponent@Vml@@A; struct Vml::VmPerfTraceComponent *
0x1400ccf54  lea     rcx, [rsp+2A8h+var_F8]; this
0x1400ccf5c  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x1400ccf61  nop
0x1400ccf62  xorps   xmm0, xmm0
0x1400ccf65  movups  xmmword ptr [rsp+2A8h+var_240.Data1], xmm0
0x1400ccf6a  lea     r9, [rsp+2A8h+var_240]; struct _GUID *
0x1400ccf6f  mov     r8, rbx; struct _GUID *
0x1400ccf72  lea     rdx, ?g_MigrationPerfTrace@@3VVmPerfTraceComponent@Vml@@A; struct Vml::VmPerfTraceComponent *
0x1400ccf79  lea     rcx, [rsp+2A8h+var_188]; this
0x1400ccf81  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x1400ccf86  nop
0x1400ccf87  mov     rcx, [rsi]
0x1400ccf8a  add     rcx, 10h; this
0x1400ccf8e  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400ccf93  mov     [rsp+2A8h+var_278], rax
0x1400ccf98  lea     r8, [rsp+2A8h+var_278]
0x1400ccf9d  lea     rdx, VMWP_PERF_MIGRATION_TARGET_RESTORE_WORKER_START; EventDescriptor
0x1400ccfa4  lea     rcx, [rsp+2A8h+var_F8]; this
0x1400ccfac  call    ??$BeginOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::BeginOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x1400ccfb1  xorps   xmm0, xmm0
0x1400ccfb4  xor     eax, eax
0x1400ccfb6  movups  [rsp+2A8h+var_220], xmm0
0x1400ccfbe  mov     [rsp+2A8h+var_210], rax
0x1400ccfc6  lea     rax, [rsp+2A8h+var_F8]
0x1400ccfce  mov     qword ptr [rsp+2A8h+var_220], rax
0x1400ccfd6  mov     qword ptr [rsp+2A8h+var_220+8], r14
0x1400ccfde  mov     byte ptr [rsp+2A8h+var_210], 1
0x1400ccfe6  mov     rcx, r14; this
0x1400ccfe9  call    ?CheckCancel@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::CheckCancel(void)
0x1400ccfee  mov     rcx, [rsp+2A8h]; this
0x1400ccff6  test    eax, eax
0x1400ccff8  jns     short loc_1400CD00E
0x1400ccffa  mov     r9d, eax; char *
0x1400ccffd  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400cd004  mov     edx, 5BEh; void *
0x1400cd009  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cd00e  mov     rcx, r14; this
0x1400cd011  call    ?PrepareVmForRestore@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::PrepareVmForRestore(void)
0x1400cd016  mov     rcx, [rsp+2A8h]; this
0x1400cd01e  test    eax, eax
0x1400cd020  jns     short loc_1400CD036
0x1400cd022  mov     r9d, eax; char *
0x1400cd025  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400cd02c  mov     edx, 5C1h; void *
0x1400cd031  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cd036  mov     rcx, [rsi]
0x1400cd039  add     rcx, 10h; this
0x1400cd03d  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400cd042  mov     [rsp+2A8h+var_278], rax
0x1400cd047  lea     r8, [rsp+2A8h+var_278]
0x1400cd04c  lea     rdx, VMWP_PERF_MIGRATION_TARGET_RESTORE_VSM_START; EventDescriptor
0x1400cd053  lea     rcx, [rsp+2A8h+var_188]; this
0x1400cd05b  call    ??$BeginOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::BeginOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x1400cd060  mov     rax, [rsi]
0x1400cd063  mov     rcx, [rax+400h]
0x1400cd06a  lea     r12, [r14+238h]
0x1400cd071  mov     rax, [rcx]
0x1400cd074  mov     rdx, [r12]
0x1400cd078  mov     rax, [rax+108h]
0x1400cd07f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd084  mov     rcx, [r14+1D0h]
0x1400cd08b  mov     rax, [rcx]
0x1400cd08e  xor     r8d, r8d
0x1400cd091  mov     rdx, [r12]
0x1400cd095  mov     rax, [rax+198h]
0x1400cd09c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd0a1  mov     rcx, [rsi]
0x1400cd0a4  add     rcx, 10h; this
0x1400cd0a8  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400cd0ad  mov     [rsp+2A8h+var_278], rax
0x1400cd0b2  lea     r8, [rsp+2A8h+var_278]; __int64
0x1400cd0b7  lea     rdx, VMWP_PERF_MIGRATION_TARGET_RESTORE_VSM_STOP; EventDescriptor
0x1400cd0be  lea     rcx, [rsp+2A8h+var_188]; this
0x1400cd0c6  call    ??$EndOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::EndOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x1400cd0cb  mov     [rsp+2A8h+var_170], 0
0x1400cd0d7  mov     [rsp+2A8h+var_168], 0
0x1400cd0e3  mov     [rsp+2A8h+var_17C], 1
0x1400cd0ee  mov     rcx, [rsi]
0x1400cd0f1  add     rcx, 10h; this
0x1400cd0f5  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400cd0fa  mov     [rsp+2A8h+var_278], rax
0x1400cd0ff  lea     r8, [rsp+2A8h+var_278]
0x1400cd104  lea     rdx, VMWP_PERF_MIGRATION_TARGET_RESTORE_RUNTIME_CHANGES_START; EventDescriptor
0x1400cd10b  lea     rcx, [rsp+2A8h+var_188]; this
0x1400cd113  call    ??$BeginOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::BeginOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x1400cd118  mov     rbx, [rsi]
0x1400cd11b  mov     rdx, r12
0x1400cd11e  lea     rcx, [rsp+2A8h+var_278]
0x1400cd123  call    ??0?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@AEBV01@@Z; Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> const &)
0x1400cd128  mov     rdx, rax
0x1400cd12b  mov     rcx, rbx
0x1400cd12e  call    ?ApplyMigrationRuntimeStateChanges@VirtualMachine@@QEAAJV?$VmReferencePtr@VSavedStateRepository@@VVmUserReferenceTraits@Vml@@@Vml@@@Z; VirtualMachine::ApplyMigrationRuntimeStateChanges(Vml::VmReferencePtr<SavedStateRepository,Vml::VmUserReferenceTraits>)
0x1400cd133  mov     rcx, [rsp+2A8h]; this
0x1400cd13b  test    eax, eax
0x1400cd13d  jns     short loc_1400CD153
0x1400cd13f  mov     r9d, eax; char *
0x1400cd142  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400cd149  mov     edx, 5DBh; void *
0x1400cd14e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cd153  mov     rcx, [rsi]
0x1400cd156  add     rcx, 10h; this
0x1400cd15a  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400cd15f  mov     [rsp+2A8h+var_278], rax
0x1400cd164  lea     r8, [rsp+2A8h+var_278]; __int64
0x1400cd169  lea     rdx, VMWP_PERF_MIGRATION_TARGET_RESTORE_RUNTIME_CHANGES_STOP; EventDescriptor
0x1400cd170  lea     rcx, [rsp+2A8h+var_188]; this
0x1400cd178  call    ??$EndOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::EndOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x1400cd17d  mov     rdx, [r12]; struct VmRepository *
0x1400cd181  mov     rcx, r14; this
0x1400cd184  call    ?RestoreVmb@WorkerTaskMigrationTarget@@AEAAJPEAVVmRepository@@@Z; WorkerTaskMigrationTarget::RestoreVmb(VmRepository *)
0x1400cd189  mov     rcx, [rsp+2A8h]; this
0x1400cd191  test    eax, eax
0x1400cd193  jns     short loc_1400CD1A9
0x1400cd195  mov     r9d, eax; char *
0x1400cd198  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400cd19f  mov     edx, 5E4h; void *
0x1400cd1a4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cd1a9  lea     rax, [r14+1C0h]
0x1400cd1b0  mov     [rsp+2A8h+var_278], rax
0x1400cd1b5  mov     dword ptr [rax], 6
0x1400cd1bb  cmp     byte ptr [r14+199h], 0
0x1400cd1c3  jz      loc_1400CD294
0x1400cd1c9  mov     rcx, r14; this
0x1400cd1cc  call    ?DoTdxImportEnd@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::DoTdxImportEnd(void)
0x1400cd1d1  mov     rcx, [rsp+2A8h]; this
0x1400cd1d9  test    eax, eax
0x1400cd1db  jns     short loc_1400CD1F1
0x1400cd1dd  mov     r9d, eax; char *
0x1400cd1e0  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400cd1e7  mov     edx, 5F3h; void *
0x1400cd1ec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cd1f1  mov     rax, [rsi]
0x1400cd1f4  mov     rcx, [rax+400h]
0x1400cd1fb  add     rcx, 18h
0x1400cd1ff  mov     rax, [rcx]
0x1400cd202  mov     rax, [rax]
0x1400cd205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd20a  xor     r9d, r9d
0x1400cd20d  xor     r8d, r8d
0x1400cd210  xor     edx, edx
0x1400cd212  mov     rcx, rax
0x1400cd215  call    cs:__imp_VidChangePartitionLifeState
0x1400cd21c  nop     dword ptr [rax+rax+00h]
0x1400cd221  mov     ebx, 41E2h
0x1400cd226  test    eax, eax
0x1400cd228  jnz     short loc_1400CD243
0x1400cd22a  mov     ecx, ebx
0x1400cd22c  call    VmlIsDebugTraceEnabled
0x1400cd231  test    eax, eax
0x1400cd233  jz      short loc_1400CD243
0x1400cd235  lea     rdx, off_1402DB4F0; "Failed to transition partition into sec"...
0x1400cd23c  mov     ecx, ebx
0x1400cd23e  call    VmlDebugTraceEx
0x1400cd243  mov     rax, [rsi]
0x1400cd246  mov     rcx, [rax+400h]
0x1400cd24d  add     rcx, 18h
0x1400cd251  mov     rax, [rcx]
0x1400cd254  mov     rax, [rax]
0x1400cd257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd25c  xor     r9d, r9d
0x1400cd25f  xor     r8d, r8d
0x1400cd262  lea     edx, [r9+2]
0x1400cd266  mov     rcx, rax
0x1400cd269  call    cs:__imp_VidChangePartitionLifeState
0x1400cd270  nop     dword ptr [rax+rax+00h]
0x1400cd275  test    eax, eax
0x1400cd277  jnz     short loc_1400CD299
0x1400cd279  mov     ecx, ebx
0x1400cd27b  call    VmlIsDebugTraceEnabled
0x1400cd280  test    eax, eax
0x1400cd282  jz      short loc_1400CD299
0x1400cd284  lea     rdx, off_1402DB220; "Failed to transition partition into com"...
0x1400cd28b  mov     ecx, ebx
0x1400cd28d  call    VmlDebugTraceEx
0x1400cd292  jmp     short loc_1400CD299
0x1400cd294  mov     ebx, 41E2h
0x1400cd299  mov     [rsp+2A8h+var_170], 0
0x1400cd2a5  mov     [rsp+2A8h+var_168], 0
0x1400cd2b1  mov     [rsp+2A8h+var_17C], 1
0x1400cd2bc  mov     rcx, [rsi]
0x1400cd2bf  add     rcx, 10h; this
0x1400cd2c3  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400cd2c8  mov     [rsp+2A8h+var_270], rax
0x1400cd2cd  lea     r8, [rsp+2A8h+var_270]
0x1400cd2d2  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_RESTORE_PARTITION_START; EventDescriptor
0x1400cd2d9  lea     rcx, [rsp+2A8h+var_188]; this
0x1400cd2e1  call    ??$BeginOperation@PEBG@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@$$QEAPEBG@Z; Vml::VmPerfTraceOperation::BeginOperation<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const * &&)
0x1400cd2e6  xor     r8d, r8d; bool
0x1400cd2e9  mov     rdx, [r12]; struct VmRepository *
0x1400cd2ed  mov     rcx, [rsi]; this
0x1400cd2f0  call    ?RestorePartitionStates@VirtualMachine@@QEAAJPEAVVmRepository@@_NI@Z; VirtualMachine::RestorePartitionStates(VmRepository *,bool,uint)
0x1400cd2f5  mov     r13d, eax
0x1400cd2f8  test    eax, eax
0x1400cd2fa  jns     short loc_1400CD334
0x1400cd2fc  mov     ecx, ebx
0x1400cd2fe  call    VmlIsDebugTraceEnabled
0x1400cd303  test    eax, eax
0x1400cd305  jz      short loc_1400CD318
0x1400cd307  mov     r8d, r13d
0x1400cd30a  lea     rdx, off_1402DB2A0; "Failed to restore partition state"
0x1400cd311  mov     ecx, ebx
0x1400cd313  call    VmlDebugTraceWithError
0x1400cd318  mov     rcx, [rsp+2A8h]; this
0x1400cd320  mov     r9d, r13d; char *
0x1400cd323  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400cd32a  mov     edx, 624h; void *
0x1400cd32f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cd334  mov     rax, [rsi]
0x1400cd337  mov     r13, [rax+3E0h]
0x1400cd33e  mov     rdx, [r13+0]
0x1400cd342  mov     rcx, r13
0x1400cd345  cmp     byte ptr [rax+0A69h], 0
0x1400cd34c  jz      short loc_1400CD364
0x1400cd34e  mov     rax, [rdx+208h]
0x1400cd355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd35a  mov     [rsp+2A8h+var_198], rax
0x1400cd362  jmp     short loc_1400CD378
0x1400cd364  mov     rax, [rdx+200h]
0x1400cd36b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd370  mov     [rsp+2A8h+var_198], rax
0x1400cd378  mov     rax, [rsi]
0x1400cd37b  mov     rax, [rax+420h]
0x1400cd382  mov     [rsp+2A8h+var_270], rax
0x1400cd387  mov     rax, [rax]
0x1400cd38a  mov     rax, [rax+18h]
0x1400cd38e  mov     [rsp+2A8h+var_228], rax
0x1400cd396  mov     rdx, [r13+0]
0x1400cd39a  mov     rcx, r13
0x1400cd39d  mov     rax, [rdx+210h]
0x1400cd3a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd3a9  xor     r9d, r9d
0x1400cd3ac  mov     r8, rax
0x1400cd3af  mov     rdx, [rsp+2A8h+var_198]
0x1400cd3b7  mov     rcx, [rsp+2A8h+var_270]
0x1400cd3bc  mov     rax, [rsp+2A8h+var_228]
0x1400cd3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cd3c9  mov     r13d, eax
0x1400cd3cc  test    eax, eax
0x1400cd3ce  jns     short loc_1400CD408
0x1400cd3d0  mov     ecx, ebx
0x1400cd3d2  call    VmlIsDebugTraceEnabled
0x1400cd3d7  test    eax, eax
0x1400cd3d9  jz      short loc_1400CD3EC
0x1400cd3db  mov     r8d, r13d
0x1400cd3de  lea     rdx, off_1402DB3A0; "Failed to restore saved state manager s"...
0x1400cd3e5  mov     ecx, ebx
0x1400cd3e7  call    VmlDebugTraceWithError
0x1400cd3ec  mov     rcx, [rsp+2A8h]; this
0x1400cd3f4  mov     r9d, r13d; char *
0x1400cd3f7  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x1400cd3fe  mov     edx, 63Ah; void *
0x1400cd403  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cd408  mov     rcx, [rsi]
0x1400cd40b  add     rcx, 10h; this
0x1400cd40f  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400cd414  mov     [rsp+2A8h+var_270], rax
0x1400cd419  lea     r8, [rsp+2A8h+var_270]; __int64
0x1400cd41e  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_RESTORE_PARTITION_STOP; EventDescriptor
  ... truncated ...
```
