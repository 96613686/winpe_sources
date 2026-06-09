# WorkerTaskStarting::RunRestoreStartSteps(void)

- ea: `0x14017e700`
- end: `0x14017fb33`
- name: `?RunRestoreStartSteps@WorkerTaskStarting@@AEAAJXZ`
- size: `5171`
- prototype: `__int64 __fastcall(WorkerTaskStarting *this, __int64)`
- caller_count: `1`
- callee_count: `68`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14017fb40`

## callees

- `0x14001e628`
- `0x140021d00`
- `0x14002ecd0`
- `0x14002ed70`
- `0x140031094`
- `0x140031c88`
- `0x14003364c`
- `0x140042240`
- `0x140054508`
- `0x140054630`
- `0x140054af0`
- `0x14005606c`
- `0x1400561a8`
- `0x14005ddd0`
- `0x14005eca0`
- `0x14008f85c`
- `0x14008f900`
- `0x140092f64`
- `0x140093b34`
- `0x140093d34`
- `0x140093f84`
- `0x140094074`
- `0x1400941dc`
- `0x1400996b8`
- `0x14009b588`
- `0x14009c720`
- `0x14009e5b0`
- `0x1400b0d40`
- `0x1400b2bd0`
- `0x1400c0bf0`
- `0x1400c5a1c`
- `0x1400cf8a0`
- `0x1400d1150`
- `0x1400d11e4`
- `0x1400df13c`
- `0x1400ed794`
- `0x1400f5994`
- `0x1400f8dc4`
- `0x140111070`
- `0x140119298`
- `0x14011fd34`
- `0x140132940`
- `0x140132d30`
- `0x1401335fc`
- `0x14014c9c8`
- `0x14016186c`
- `0x140166320`
- `0x14016ad80`
- `0x140170910`
- `0x14017cf24`

## import_xrefs

- `vid!VidTrimPartitionMemory` at `0x14017f864`
- `vid!VidTrimPartitionMemory` at `0x14017f864`

## string_xrefs

- `0x14017ed6f`: `onecore\vm\worker\wpcore\workertaskstarting.cpp`
- `0x14017f579`: `onecore\vm\worker\wpcore\workertaskstarting.cpp`
- `0x14017f6d9`: `onecore\vm\worker\wpcore\workertaskstarting.cpp`
- `0x14017e926`: `ConfigReadFail:%ld`
- `0x14017e886`: `'WorkerTaskStarting::RunRestoreStartSteps': Failed to call '%hs'; hr=0x%08X\n`
- `0x14017ea4e`: `'WorkerTaskStarting::RunRestoreStartSteps': Failed to call '%hs'; hr=0x%08X\n`
- `0x14017eb6e`: `'WorkerTaskStarting::RunRestoreStartSteps': Failed to call '%hs'; hr=0x%08X\n`
- `0x14017e87f`: `Failed to create version manager`
- `0x14017f16b`: `EnableAllZeroBufferWrite`

## pseudocode

```c
// Hidden C++ exception states: #wind=26 #try_helpers=1
__int64 __fastcall WorkerTaskStarting::RunRestoreStartSteps(WorkerTaskStarting *this, __int64 a2)
{
  _DWORD *v3; // r13
  __int64 v4; // rdx
  __int64 v5; // rdx
  VirtualMachine **v6; // r14
  int started; // edi
  __int64 SavedStateRepositoryForRestore; // rax
  struct VmRepository *v9; // rbx
  int v10; // eax
  VmPrefixRepository *v11; // rax
  const unsigned __int16 *v12; // r8
  VmPrefixRepository *v13; // r15
  __int128 *v14; // rax
  VirtualMachine *v15; // rcx
  unsigned __int64 v16; // rbx
  char v17; // al
  __int16 v18; // r12
  VirtualMachine *v19; // rdx
  __int64 v20; // rcx
  int v21; // ecx
  wil *v22; // rcx
  VirtualMachine *v23; // rdi
  __int64 CurrentActivity; // rax
  int v25; // eax
  wil *v26; // rcx
  VirtualMachine *v27; // r13
  __int64 v28; // rdi
  int v29; // r12d
  WorkerTaskStarting *v30; // rbx
  unsigned int v31; // edi
  WorkerTaskStarting *v32; // r13
  int v33; // eax
  unsigned int v34; // ebx
  VirtualMachine *v35; // rcx
  int v36; // eax
  VirtualMachine *v37; // rcx
  int v38; // eax
  int v39; // eax
  unsigned int v40; // r9d
  int v41; // eax
  int v42; // eax
  VirtualMachine *v43; // rdi
  __int64 v44; // rbx
  int v45; // eax
  VirtualMachine *v46; // rdi
  __int64 v47; // rbx
  int v48; // eax
  __int64 v49; // rdi
  __int64 v50; // r15
  __int64 (__fastcall *v51)(__int64, __int64, __int64, _QWORD); // r13
  unsigned int v52; // ebx
  __int64 v53; // r12
  __int64 v54; // rax
  int v55; // eax
  int v56; // eax
  __int64 v57; // rax
  VirtualMachine *v58; // r15
  __int64 v59; // rbx
  const char *v60; // r9
  int v61; // edx
  VirtualMachine *v62; // r8
  int v64; // [rsp+20h] [rbp-508h]
  unsigned __int64 RamSizeInPages; // [rsp+30h] [rbp-4F8h]
  int v66; // [rsp+50h] [rbp-4D8h]
  __int64 v68; // [rsp+68h] [rbp-4C0h] BYREF
  __int64 v69; // [rsp+70h] [rbp-4B8h] BYREF
  char v70; // [rsp+78h] [rbp-4B0h]
  int v71; // [rsp+7Ch] [rbp-4ACh]
  int v72; // [rsp+80h] [rbp-4A8h]
  int v73; // [rsp+84h] [rbp-4A4h]
  __int64 v74; // [rsp+88h] [rbp-4A0h] BYREF
  VirtualMachine **v75; // [rsp+90h] [rbp-498h]
  __int64 VmName; // [rsp+98h] [rbp-490h] BYREF
  struct VmRepository *v77; // [rsp+A0h] [rbp-488h] BYREF
  struct IVersionManager *v78; // [rsp+A8h] [rbp-480h] BYREF
  VmPrefixRepository *v79; // [rsp+B0h] [rbp-478h] BYREF
  _BYTE v80[336]; // [rsp+C0h] [rbp-468h] BYREF
  unsigned int v81[2]; // [rsp+210h] [rbp-318h] BYREF
  int v82; // [rsp+218h] [rbp-310h] BYREF
  unsigned int v83; // [rsp+21Ch] [rbp-30Ch] BYREF
  HKEY phkResult; // [rsp+220h] [rbp-308h] BYREF
  __int128 v85; // [rsp+228h] [rbp-300h] BYREF
  __m128i si128; // [rsp+238h] [rbp-2F0h]
  _OWORD v87[2]; // [rsp+248h] [rbp-2E0h] BYREF
  _QWORD v88[42]; // [rsp+270h] [rbp-2B8h] BYREF
  GmoBufferPool *v89[23]; // [rsp+3C0h] [rbp-168h] BYREF
  int v90; // [rsp+478h] [rbp-B0h]
  unsigned int v91; // [rsp+488h] [rbp-A0h]
  int v92; // [rsp+494h] [rbp-94h]
  __int64 v93[4]; // [rsp+4B0h] [rbp-78h] BYREF
  __int64 v94[4]; // [rsp+4D0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+0h]

  v74 = (__int64)this;
  LODWORD(v69) = 0;
  v3 = (_DWORD *)((char *)this + 404);
  v68 = (__int64)this + 404;
  LOBYTE(a2) = *((_BYTE *)this + 404) & 1;
  WorkerAsyncTask<VmWorkerTrace::StartingTask>::LogFlag(this, a2, L"VmPhu");
  v4 = *v3 >> 2;
  LOBYTE(v4) = (*v3 & 4) != 0;
  WorkerAsyncTask<VmWorkerTrace::StartingTask>::LogFlag(this, v4, L"DisableFlushes");
  v5 = *v3 >> 4;
  LOBYTE(v5) = (*v3 & 0x10) != 0;
  WorkerAsyncTask<VmWorkerTrace::StartingTask>::LogFlag(this, v5, L"HandleTransfer");
  v73 = 0;
  v71 = 0;
  LODWORD(phkResult) = 0;
  v72 = 0;
  v82 = 0;
  memset_0(v89, 0, 0xF0u);
  GmoRamOperation::GmoRamOperation((GmoRamOperation *)v89);
  v89[0] = (GmoBufferPool *)&GmoRamOperationRestore::`vftable';
  v79 = 0;
  v78 = 0;
  v87[0] = 0;
  v87[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v87[0]) = 0;
  v77 = 0;
  v6 = (VirtualMachine **)((char *)this + 16);
  v75 = (VirtualMachine **)((char *)this + 16);
  (*(void (__fastcall **)(_QWORD, int *))(**(_QWORD **)(*((_QWORD *)this + 2) + 1072LL) + 112LL))(
    *(_QWORD *)(*((_QWORD *)this + 2) + 1072LL),
    &v82);
  started = VersionManagerDefaultFactory::CreateVersionManagerInstance(&v78);
  v66 = started;
  if ( started < 0 )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
      VmlDebugTrace(
        16416,
        L"'WorkerTaskStarting::RunRestoreStartSteps': Failed to call '%hs'; hr=0x%08X\n",
        "Failed to create version manager",
        (unsigned int)started);
    goto LABEL_126;
  }
  SavedStateRepositoryForRestore = VirtualMachine::GetSavedStateRepositoryForRestore(
                                     *v6,
                                     v81,
                                     *(unsigned int *)(*((_QWORD *)*v6 + 177) + 108LL));
  Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::operator=(&v77, SavedStateRepositoryForRestore);
  Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(v81);
  v85 = 0;
  v9 = v77;
  VmRepositoryAutoLock::VmRepositoryAutoLock(&v85, v77, 0);
  if ( (SDWORD2(v85) & 0x80000000) == 0 )
  {
    v10 = (*(__int64 (__fastcall **)(struct VmRepository *, const unsigned __int16 *, _OWORD *))(*(_QWORD *)v9 + 104LL))(
            v9,
            L"/savedstate/VmwpVersion",
            v87);
    if ( v10 < 0 )
      Vml::FormatString(v87, L"ConfigReadFail:%ld", (unsigned int)v10);
    started = 0;
    v66 = 0;
  }
  VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)&v85);
  v11 = (VmPrefixRepository *)operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
  VmName = (__int64)v11;
  if ( v11 )
    v13 = VmPrefixRepository::VmPrefixRepository(v11, v9, v12);
  else
    v13 = 0;
  if ( !v13 )
  {
    v79 = 0;
    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
      VmlDebugTrace(16416, L"Failed to allocate prefix repository!\n");
    goto LABEL_126;
  }
  Vml::VmSharableObject::IncrementUserCount((VmPrefixRepository *)((char *)v13 + 8));
  v79 = v13;
  v83 = 0;
  v85 = 0;
  VmRepositoryAutoLock::VmRepositoryAutoLock(&v85, v9, 1);
  started = DWORD2(v85);
  if ( SDWORD2(v85) < 0 )
  {
    v66 = DWORD2(v85);
    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
      VmlDebugTraceWithError(16416, &off_1402D9BF8, (unsigned int)started);
LABEL_15:
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)&v85);
LABEL_126:
    v30 = this;
    goto LABEL_127;
  }
  *(_QWORD *)v81 = 0;
  started = (*(__int64 (__fastcall **)(struct VmRepository *, const unsigned __int16 *, unsigned int *))(*(_QWORD *)v9 + 112LL))(
              v9,
              L"/savedstate/VmVersion",
              v81);
  v66 = started;
  if ( started < 0 )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
      VmlDebugTrace(
        16416,
        L"'WorkerTaskStarting::RunRestoreStartSteps': Failed to call '%hs'; hr=0x%08X\n",
        "Failed to get saved state VmVersion",
        (unsigned int)started);
    goto LABEL_15;
  }
  v83 = v81[0];
  VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)&v85);
  if ( !(**(unsigned __int8 (__fastcall ***)(struct IVersionManager *, unsigned int *))v78)(v78, &v83) )
  {
    v85 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v85) = 0;
    GetVmVersionString(v83, &v85);
    v14 = &v85;
    if ( si128.m128i_i64[1] > 7uLL )
      v14 = (__int128 *)v85;
    v74 = (__int64)v14;
    v15 = *v6;
    v68 = (__int64)*v6 + 1152;
    *(_QWORD *)v81 = VirtualMachine::GetVmName((VirtualMachine *)((char *)v15 + 16));
    VmEventWriteAndReport<unsigned short const *,unsigned short const *,unsigned short const *>(
      (struct _EVENT_DESCRIPTOR *)&MSVML_WP_SAVEDSTATE_VERSION_INCOMPATIBLE_ERROR,
      5u,
      (__int64)v81,
      (__int64)&v68,
      (__int64)&v74);
    started = -2147188714;
    v66 = -2147188714;
    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
      VmlDebugTrace(
        16416,
        L"'WorkerTaskStarting::RunRestoreStartSteps': Failed to call '%hs'; hr=0x%08X\n",
        "Saved state VmVersion is not supported",
        2147778582LL);
    std::wstring::_Tidy_deallocate(&v85);
    goto LABEL_126;
  }
  v81[0] = 0;
  v16 = 0;
  v17 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)*v6 + 130) + 504LL))(*((_QWORD *)*v6 + 130));
  v70 = v17;
  v18 = 2;
  v19 = *v6;
  v20 = *((_QWORD *)*v6 + 177);
  if ( *(_DWORD *)(v20 + 108) )
  {
    v16 = *((_QWORD *)v19 + 331);
    v21 = (v16 >> 1) & 8 | 6;
    if ( (v16 & 0x40) != 0 )
      v21 = (*((_QWORD *)v19 + 331) >> 1) & 8 | 0x86;
    if ( (*(_BYTE *)v3 & 0x10) != 0 )
      LOWORD(v21) = v21 | 0x10;
    if ( (*(_BYTE *)v3 & 0x20) != 0 )
      LOWORD(v21) = v21 | 0x20;
    if ( (*(_BYTE *)v3 & 0x40) != 0 )
      LOWORD(v21) = v21 | 0x40;
    v18 = v21 | 0x100;
    if ( !v17 )
      v18 = v21;
  }
  try
  {
    if ( *(_BYTE *)(MemoryManager::RestoreCloneTemplateId(&MemoryManager::m_Instance, &v85, v13) + 16) )
    {
      v81[0] = 1;
    }
    else if ( (unsigned int)VmlIsDebugTraceEnabled(49184) )
    {
      VmlDebugTrace(49184, L"Restoring memory from saved state.");
    }
  }
  catch ( ... )
  {
    v66 = wil::ResultFromCaughtException(v22);
    started = v66;
    v30 = (WorkerTaskStarting *)v74;
    v6 = v75;
    v3 = (_DWORD *)v68;
    goto LABEL_127;
  }
  if ( (*(_BYTE *)v3 & 1) != 0 )
  {
    started = VirtualMachine::RestoreIgvmSaveState(*v6, v13);
    v66 = started;
    if ( started < 0 )
      goto LABEL_126;
  }
  started = VirtualMotherboard::StartReservingResources(*((_QWORD *)*v6 + 123), v13, v18);
  v66 = started;
  if ( started < 0 )
    goto LABEL_126;
  if ( v82 )
  {
    started = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)*v6 + 134) + 168LL))(*((_QWORD *)*v6 + 134));
    v66 = started;
    if ( started < 0 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
        VmlDebugTrace(16416, L"Failed to initialize encryption keys.");
      goto LABEL_126;
    }
  }
  memset_0(v88, 0, sizeof(v88));
  v23 = *v6;
  CurrentActivity = WorkerAsyncTask<VmWorkerTrace::StartingTask>::GetCurrentActivity(this, v80);
  VmPerf::StartRelatedActivity_VmWorkerTrace::ConstructGuestRam_VmWorkerTrace::StartingTask__GUID_const___(
    (VmWorkerTrace::ConstructGuestRam *)v88,
    CurrentActivity,
    (const struct _GUID *)v23 + 71);
  VmWorkerTrace::StartingTask::~StartingTask((VmWorkerTrace::StartingTask *)v80);
  v25 = VirtualMachine::ConstructGuestRam(
          *v6,
          v13,
          *((struct IVmSimpleTask **)this + 3),
          (const struct _GUID *)(v88[34] + 8LL));
  started = v25;
  v66 = v25;
  if ( v25 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x409,
      (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskstarting.cpp",
      (const char *)(unsigned int)v25,
      v64);
  wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v88, (unsigned int)started);
  VmWorkerTrace::ConstructGuestRam::~ConstructGuestRam((VmWorkerTrace::ConstructGuestRam *)v88);
  if ( started < 0 )
    goto LABEL_126;
  if ( (v16 & 2) == 0 )
  {
    try
    {
      (*(void (__fastcall **)(_QWORD, VmPrefixRepository *))(**((_QWORD **)*v6 + 128) + 264LL))(
        *((_QWORD *)*v6 + 128),
        v13);
      MemoryManager::RestoreVtlProtections((MemoryManager *)&MemoryManager::m_Instance, v13, 0);
    }
    catch ( ... )
    {
      v66 = wil::ResultFromCaughtException(v26);
      started = v66;
      v30 = (WorkerTaskStarting *)v74;
      v6 = v75;
      v3 = (_DWORD *)v68;
      goto LABEL_127;
    }
  }
  WorkerAsyncTaskBase::UpdateStatusProgress(this, 0x32u, (int *)&phkResult);
  if ( (_DWORD)phkResult )
  {
    started = -2147023673;
    v66 = -2147023673;
    goto LABEL_126;
  }
  v27 = *v6;
  if ( *(_DWORD *)(*((_QWORD *)*v6 + 177) + 108LL) || v81[0] )
  {
    v32 = this;
    v29 = v69;
  }
  else
  {
    memset_0(v88, 0, sizeof(v88));
    v28 = *(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::StartingTask>::GetCurrentActivity(this, v80) + 272);
    memset_0(v88, 0, sizeof(v88));
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>(
      (struct wil::details::IFailureCallback *)v88,
      (__int64)"RestoreGuestRam");
    v88[0] = &VmWorkerTrace::RestoreGuestRam::`vftable';
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(v88, v28 + 8);
    VmWorkerTrace::RestoreGuestRam::StartActivity((VmWorkerTrace::RestoreGuestRam *)v88, (const struct _GUID *)v27 + 71);
    v29 = 1;
    LODWORD(v69) = 1;
    VmWorkerTrace::StartingTask::~StartingTask((VmWorkerTrace::StartingTask *)v80);
    v85 = 0;
    VmRepositoryAutoLock::VmRepositoryAutoLock(&v85, v13, 0);
    started = DWORD2(v85);
    if ( SDWORD2(v85) < 0 )
    {
      v66 = DWORD2(v85);
      if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
        VmlDebugTrace(16416, L"Failed to lock memory repository.\n");
LABEL_59:
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)&v85);
      VmWorkerTrace::RestoreGuestRam::~RestoreGuestRam((VmWorkerTrace::RestoreGuestRam *)v88);
      v30 = this;
      v3 = (_DWORD *)v68;
      goto LABEL_127;
    }
    v31 = v83;
    RamSizeInPages = MemoryManager::GetRamSizeInPages((MemoryManager *)&MemoryManager::m_Instance);
    v32 = this;
    v33 = GmoRamOperation::Initialize(
            (GmoRamOperation *)v89,
            v13,
            *v6,
            *((struct IVmSimpleTask **)this + 3),
            0x63u,
            0x32u,
            RamSizeInPages,
            0,
            v31);
    started = v33;
    if ( v33 < 0 )
    {
      v66 = v33;
      v34 = v33 & 0xEFFFFFFF;
      _snwprintf_s<16>(v94, 16, L"%%%%%u", v33 & 0xEFFFFFFF);
      _snwprintf_s<16>(v93, 16, L"0x%08X", v34);
      v35 = *v6;
      v69 = (__int64)*v6 + 1152;
      VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)v35 + 16));
      VmEventWriteAndReport<unsigned short const *,unsigned short const *,unsigned short (&)[16],unsigned short (&)[16]>(
        (struct _EVENT_DESCRIPTOR *)&MSVML_GMO_RESTORE_INIT_ERROR,
        5u,
        (__int64)&VmName,
        (__int64)&v69,
        (__int64)v94,
        (__int64)v93);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)&v85);
      VmWorkerTrace::RestoreGuestRam::~RestoreGuestRam((VmWorkerTrace::RestoreGuestRam *)v88);
      v30 = this;
      v3 = (_DWORD *)v68;
      goto LABEL_127;
    }
    v72 = 1;
    if ( v82 )
    {
      v36 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**((_QWORD **)*v6 + 134) + 184LL))(
              *((_QWORD *)*v6 + 134),
              v91,
              256,
              3);
      started = v36;
      if ( v36 < 0 )
      {
        v66 = v36;
        if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
          VmlDebugTrace(16416, L"Failed to allocate VID buffers.\n");
        goto LABEL_59;
      }
    }
    phkResult = 0;
    Vml::VmRegistryKey::Open(
      &phkResult,
      HKEY_LOCAL_MACHINE,
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization",
      0x20019u);
    v81[0] = 0;
    if ( (!Vml::VmRegistryKey::QueryValue((Vml::VmRegistryKey *)&phkResult, L"EnableAllZeroBufferWrite", v81)
       || v81[0] != 1)
      && !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)*v6 + 124) + 800LL))(*((_QWORD *)*v6 + 124)) )
    {
      v92 = 1;
    }
    started = GmoRamOperation::WorkThreadsStart((GmoRamOperation *)v89);
    v66 = started;
    if ( started < 0 )
    {
      Vml::VmRegistryKey::Close((Vml::VmRegistryKey *)&phkResult);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)&v85);
      VmWorkerTrace::RestoreGuestRam::~RestoreGuestRam((VmWorkerTrace::RestoreGuestRam *)v88);
      v30 = this;
      v3 = (_DWORD *)v68;
      goto LABEL_127;
    }
    GmoRamOperation::WorkDispatch((GmoRamOperation *)v89);
    GmoRamOperation::WorkThreadsWaitForExit((GmoRamOperation *)v89);
    started = v90;
    v66 = v90;
    if ( v90 < 0 )
    {
      if ( v90 == -2147213311 )
      {
        v37 = *v6;
        VmName = (__int64)*v6 + 1152;
        v69 = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)v37 + 16));
        VmEventWriteAndReport<unsigned short const *,unsigned short const *>(
          (struct _EVENT_DESCRIPTOR *)&MSVML_RESTORE_CANCELED,
          5u,
          (__int64)&v69,
          (__int64)&VmName);
      }
      Vml::VmRegistryKey::Close((Vml::VmRegistryKey *)&phkResult);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)&v85);
      VmWorkerTrace::RestoreGuestRam::~RestoreGuestRam((VmWorkerTrace::RestoreGuestRam *)v88);
      v30 = this;
      v3 = (_DWORD *)v68;
      goto LABEL_127;
    }
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v88, 0);
    Vml::VmRegistryKey::Close((Vml::VmRegistryKey *)&phkResult);
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)&v85);
    VmWorkerTrace::RestoreGuestRam::~RestoreGuestRam((VmWorkerTrace::RestoreGuestRam *)v88);
  }
  if ( *(_DWORD *)(*((_QWORD *)*v6 + 177) + 108LL) )
  {
    if ( v70 )
    {
      started = (*(__int64 (__fastcall **)(__int64, VmPrefixRepository *))(*(_QWORD *)(*((_QWORD *)*v6 + 128) + 8LL)
                                                                         + 104LL))(
                  *((_QWORD *)*v6 + 128) + 8LL,
                  v13);
      v66 = started;
      if ( started < 0 )
      {
        v30 = this;
        v3 = (_DWORD *)v68;
        goto LABEL_127;
      }
    }
  }
  v38 = WorkerTaskStarting::PowerOnVirtualMotherboard(v32, v13, v16);
  started = v38;
  if ( v38 < 0 )
  {
    v66 = v38;
    v30 = this;
    v3 = (_DWORD *)v68;
    goto LABEL_127;
  }
  v73 = 1;
  started = VirtualMachine::RegisterGuestCrashManager(*v6);
  v66 = started;
  if ( started < 0 )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
      VmlDebugTraceWithError(16416, &off_1402D9BE0, (unsigned int)started);
    v30 = this;
    v3 = (_DWORD *)v68;
    goto LABEL_127;
  }
  v39 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)*v6 + 133) + 48LL))(*((_QWORD *)*v6 + 133));
  started = v39;
  if ( v39 < 0 )
  {
    v66 = v39;
    v30 = this;
    v3 = (_DWORD *)v68;
    goto LABEL_127;
  }
  v41 = VirtualMachine::RestorePartitionStates(*v6, v13, v16 & 1, v40);
  started = v41;
  if ( v41 < 0 )
  {
    v66 = v41;
    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
      VmlDebugTrace(16416, L"Failed to restore partition.\n");
    v30 = this;
    v3 = (_DWORD *)v68;
    goto LABEL_127;
  }
  v42 = (*(__int64 (__fastcall **)(_QWORD, VmPrefixRepository *))(**((_QWORD **)*v6 + 130) + 768LL))(
          *((_QWORD *)*v6 + 130),
          v13);
  started = v42;
  if ( v42 < 0 )
  {
    v66 = v42;
    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
      VmlDebugTrace(16416, L"Failed to restore isolation control state.\n");
    v30 = this;
    v3 = (_DWORD *)v68;
    goto LABEL_127;
  }
  v43 = *v6;
  if ( *((_DWORD *)*v6 + 653) )
  {
    memset_0(v88, 0, sizeof(v88));
    v44 = *(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::StartingTask>::GetCurrentActivity(v32, v80) + 272);
    memset_0(v88, 0, sizeof(v88));
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>(
      (struct wil::details::IFailureCallback *)v88,
      (__int64)"RestoreEpfState");
    v88[0] = &VmWorkerTrace::RestoreEpfState::`vftable';
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(v88, v44 + 8);
    VmWorkerTrace::RestoreEpfState::StartActivity((VmWorkerTrace::RestoreEpfState *)v88, (const struct _GUID *)v43 + 71);
    v29 = v29 & 0xFFFFFFF3 | 4;
    LODWORD(v69) = v29;
    VmWorkerTrace::StartingTask::~StartingTask((VmWorkerTrace::StartingTask *)v80);
    v45 = (*(__int64 (__fastcall **)(_QWORD, VmPrefixRepository *))(**((_QWORD **)*v6 + 128) + 280LL))(
            *((_QWORD *)*v6 + 128),
            v13);
    started = v45;
    if ( v45 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4F1,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskstarting.cpp",
        (const char *)(unsigned int)v45,
        v64);
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v88, (unsigned int)started);
    if ( started < 0 )
    {
      v66 = started;
      if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
        VmlDebugTrace(16416, L"Failed to restore partition EPF state.\n");
      VmWorkerTrace::RestoreEpfState::~RestoreEpfState((VmWorkerTrace::RestoreEpfState *)v88);
      v30 = this;
      v3 = (_DWORD *)v68;
      goto LABEL_127;
    }
    VmWorkerTrace::RestoreEpfState::~RestoreEpfState((VmWorkerTrace::RestoreEpfState *)v88);
  }
  v46 = *v6;
  if ( *((_BYTE *)*v6 + 2616) )
  {
    memset_0(v88, 0, sizeof(v88));
    v47 = *(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::StartingTask>::GetCurrentActivity(v32, v80) + 272);
    memset_0(v88, 0, sizeof(v88));
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>(
      (struct wil::details::IFailureCallback *)v88,
      (__int64)"RestoreSchedulerAssistState");
    v88[0] = &VmWorkerTrace::RestoreSchedulerAssistState::`vftable';
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(v88, v47 + 8);
    VmWorkerTrace::RestoreSchedulerAssistState::StartActivity(
      (VmWorkerTrace::RestoreSchedulerAssistState *)v88,
      (const struct _GUID *)v46 + 71);
    LODWORD(v69) = v29 & 0xFFFFFFCF | 0x10;
    VmWorkerTrace::StartingTask::~StartingTask((VmWorkerTrace::StartingTask *)v80);
    v48 = (*(__int64 (__fastcall **)(_QWORD, VmPrefixRepository *))(**((_QWORD **)*v6 + 128) + 304LL))(
            *((_QWORD *)*v6 + 128),
            v13);
    started = v48;
    if ( v48 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x506,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskstarting.cpp",
        (const char *)(unsigned int)v48,
        v64);
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v88, (unsigned int)started);
    if ( started < 0 )
    {
      v66 = started;
      if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
        VmlDebugTrace(16416, L"Failed to restore partition scheduler assist state.\n");
      VmWorkerTrace::RestoreSchedulerAssistState::~RestoreSchedulerAssistState((VmWorkerTrace::RestoreSchedulerAssistState *)v88);
      v30 = this;
      v3 = (_DWORD *)v68;
      goto LABEL_127;
    }
    VmWorkerTrace::RestoreSchedulerAssistState::~RestoreSchedulerAssistState((VmWorkerTrace::RestoreSchedulerAssistState *)v88);
  }
  v49 = *((_QWORD *)*v6 + 124);
  v50 = *((_QWORD *)*v6 + 132);
  v51 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v50 + 24LL);
  v52 = (*(_DWORD *)v68 >> 2) & 1;
  v53 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 528LL))(v49);
  v54 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 512LL))(v49);
  v55 = v51(v50, v54, v53, v52);
  started = v55;
  if ( v55 >= 0 )
  {
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)*v6 + 130) + 656LL))(*((_QWORD *)*v6 + 130), 1);
    v30 = this;
    v3 = (_DWORD *)v68;
    if ( *((_DWORD *)this + 100) != 4 )
    {
      v56 = VirtualMachine::StartVm(*v6, 4 * (*(_DWORD *)v68 & 0x10u), 14);
      started = v56;
      if ( v56 < 0 )
      {
        v66 = v56;
        goto LABEL_127;
      }
      v71 = 1;
    }
    v57 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)*v6 + 128) + 24LL))(*((_QWORD *)*v6 + 128) + 24LL);
    VidTrimPartitionMemory(v57);
    started = 0;
    v66 = 0;
  }
  else
  {
    v66 = v55;
    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
      VmlDebugTrace(16416, L"Failed to restore saved state manager.\n");
    v30 = this;
    v3 = (_DWORD *)v68;
  }
LABEL_127:
  WorkerTaskStarting::UploadRestoreTelemetry(v30, v87, (unsigned int)started);
  if ( v72 )
    GmoRamOperation::Teardown(v89);
  if ( v82 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)*v6 + 134) + 192LL))(*((_QWORD *)*v6 + 134));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)*v6 + 134) + 176LL))(*((_QWORD *)*v6 + 134));
  }
  if ( started < 0 )
  {
    if ( v71 )
      VirtualMachine::StopVm(*v6, 0, 17);
    if ( v73 )
    {
      v61 = 2048;
      v62 = *v6;
      if ( *(_DWORD *)(*((_QWORD *)*v6 + 177) + 108LL)
        && (*((_BYTE *)v62 + 2648) & 0x10) != 0
        && (*(_BYTE *)v3 & 0x10) != 0 )
      {
        v61 = *v3 & 0x20 | 0x81C;
        if ( (*(_BYTE *)v3 & 0x40) != 0 )
          v61 = *v3 & 0x20 | 0x85C;
        if ( *(char *)v3 < 0 )
          v61 |= 0x100u;
      }
      VirtualMotherboard::PowerOff(*((VirtualMotherboard **)v62 + 123), v61);
    }
  }
  else
  {
    v58 = *v6;
    if ( *(_DWORD *)(*((_QWORD *)*v6 + 177) + 108LL) )
    {
      memset_0(v88, 0, sizeof(v88));
      v59 = *(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::StartingTask>::GetCurrentActivity(v30, v80) + 272);
      memset_0(v88, 0, sizeof(v88));
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>(
        (struct wil::details::IFailureCallback *)v88,
        (__int64)"UnpersistRamInformation");
      v88[0] = &VmWorkerTrace::UnpersistRamInformation::`vftable';
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
        v88,
        v59 + 8);
      VmWorkerTrace::UnpersistRamInformation::StartActivity(
        (VmWorkerTrace::UnpersistRamInformation *)v88,
        (const struct _GUID *)v58 + 71);
      VmWorkerTrace::StartingTask::~StartingTask((VmWorkerTrace::StartingTask *)v80);
      try
      {
        MemoryManager::UnPersistRamInformation((MemoryManager *)&MemoryManager::m_Instance);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x55C,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskstarting.cpp",
          v60);
        started = v66;
        v6 = v75;
      }
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v88, 0);
      VmWorkerTrace::UnpersistRamInformation::~UnpersistRamInformation((VmWorkerTrace::UnpersistRamInformation *)v88);
    }
    if ( v71 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)*v6 + 133) + 56LL))(*((_QWORD *)*v6 + 133));
  }
  if ( !v82 )
    std::unique_ptr<GmoBitmap>::reset((char **)&qword_1403C0440, 0);
  Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(&v77);
  std::wstring::_Tidy_deallocate(v87);
  Vml::VmReferencePtr<IMemoryContentsFileSizeChangeCallback,Vml::VmUserReferenceTraits>::~VmReferencePtr<IMemoryContentsFileSizeChangeCallback,Vml::VmUserReferenceTraits>(&v78);
  Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(&v79);
  GmoRamOperationRestore::~GmoRamOperationRestore((GmoRamOperationRestore *)v89);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x14017e700  mov     [rsp+arg_8], rbx
0x14017e705  mov     [rsp+arg_10], rsi
0x14017e70a  push    rdi
0x14017e70b  push    r12
0x14017e70d  push    r13
0x14017e70f  push    r14
0x14017e711  push    r15
0x14017e713  sub     rsp, 500h
0x14017e71a  mov     rax, cs:__security_cookie
0x14017e721  xor     rax, rsp
0x14017e724  mov     [rsp+528h+var_38], rax
0x14017e72c  mov     rbx, rcx
0x14017e72f  mov     [rsp+528h+var_4D0], rcx
0x14017e734  mov     [rsp+528h+var_4A0], rcx
0x14017e73c  xor     esi, esi
0x14017e73e  mov     r12d, esi
0x14017e741  mov     dword ptr [rsp+528h+var_4B8], esi
0x14017e745  mov     [rsp+528h+var_4C8], esi
0x14017e749  lea     r13, [rcx+194h]
0x14017e750  mov     [rsp+528h+var_4C0], r13
0x14017e755  mov     dl, [r13+0]
0x14017e759  and     dl, 1
0x14017e75c  lea     r8, aVmphu; "VmPhu"
0x14017e763  call    ?LogFlag@?$WorkerAsyncTask@VStartingTask@VmWorkerTrace@@@@IEAAX_NPEBG@Z; WorkerAsyncTask<VmWorkerTrace::StartingTask>::LogFlag(bool,ushort const *)
0x14017e768  mov     edx, [r13+0]
0x14017e76c  shr     edx, 2
0x14017e76f  and     dl, 1
0x14017e772  lea     r8, aDisableflushes; "DisableFlushes"
0x14017e779  mov     rcx, rbx
0x14017e77c  call    ?LogFlag@?$WorkerAsyncTask@VStartingTask@VmWorkerTrace@@@@IEAAX_NPEBG@Z; WorkerAsyncTask<VmWorkerTrace::StartingTask>::LogFlag(bool,ushort const *)
0x14017e781  mov     edx, [r13+0]
0x14017e785  shr     edx, 4
0x14017e788  and     dl, 1
0x14017e78b  lea     r8, aHandletransfer_1; "HandleTransfer"
0x14017e792  mov     rcx, rbx
0x14017e795  call    ?LogFlag@?$WorkerAsyncTask@VStartingTask@VmWorkerTrace@@@@IEAAX_NPEBG@Z; WorkerAsyncTask<VmWorkerTrace::StartingTask>::LogFlag(bool,ushort const *)
0x14017e79a  mov     [rsp+528h+var_4A4], esi
0x14017e7a1  mov     [rsp+528h+var_4AC], esi
0x14017e7a5  mov     dword ptr [rsp+528h+phkResult], esi
0x14017e7ac  mov     [rsp+528h+var_4A8], esi
0x14017e7b3  mov     [rsp+528h+var_310], esi
0x14017e7ba  xor     edx, edx; Val
0x14017e7bc  mov     r8d, 0F0h; Size
0x14017e7c2  lea     rcx, [rsp+528h+var_168]; void *
0x14017e7ca  call    memset_0
0x14017e7cf  lea     rcx, [rsp+528h+var_168]; this
0x14017e7d7  call    ??0GmoRamOperation@@QEAA@XZ; GmoRamOperation::GmoRamOperation(void)
0x14017e7dc  lea     rax, ??_7GmoRamOperationRestore@@6B@; const GmoRamOperationRestore::`vftable'
0x14017e7e3  mov     [rsp+528h+var_168], rax
0x14017e7eb  mov     [rsp+528h+var_478], rsi
0x14017e7f3  mov     [rsp+528h+var_480], rsi
0x14017e7fb  xorps   xmm0, xmm0
0x14017e7fe  movups  [rsp+528h+var_2E0], xmm0
0x14017e806  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14017e80e  movdqu  [rsp+528h+var_2D0], xmm1
0x14017e817  mov     word ptr [rsp+528h+var_2E0], si
0x14017e81f  mov     [rsp+528h+var_488], rsi
0x14017e827  lea     r14, [rbx+10h]
0x14017e82b  mov     [rsp+528h+var_498], r14
0x14017e833  mov     rax, [r14]
0x14017e836  mov     rcx, [rax+430h]
0x14017e83d  mov     rax, [rcx]
0x14017e840  lea     rdx, [rsp+528h+var_310]
0x14017e848  mov     rax, [rax+70h]
0x14017e84c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14017e851  lea     rcx, [rsp+528h+var_480]; struct IVersionManager **
0x14017e859  call    ?CreateVersionManagerInstance@VersionManagerDefaultFactory@@SAJPEAPEAUIVersionManager@@@Z; VersionManagerDefaultFactory::CreateVersionManagerInstance(IVersionManager * *)
0x14017e85e  mov     edi, eax
0x14017e860  mov     [rsp+528h+var_4D8], eax
0x14017e864  test    eax, eax
0x14017e866  jns     short loc_14017E899
0x14017e868  mov     ebx, 4020h
0x14017e86d  mov     ecx, ebx
0x14017e86f  call    VmlIsDebugTraceEnabled
0x14017e874  test    eax, eax
0x14017e876  jz      loc_14017F8AD
0x14017e87c  mov     r9d, edi
0x14017e87f  lea     r8, aFailedToCreate_3; "Failed to create version manager"
0x14017e886  lea     rdx, aWorkertaskstar_3; "'WorkerTaskStarting::RunRestoreStartSte"...
0x14017e88d  mov     ecx, ebx
0x14017e88f  call    VmlDebugTrace
0x14017e894  jmp     loc_14017F8AD
0x14017e899  mov     rcx, [r14]
0x14017e89c  mov     r8, [rcx+588h]
0x14017e8a3  mov     r8d, [r8+6Ch]
0x14017e8a7  lea     rdx, [rsp+528h+var_318]
0x14017e8af  call    ?GetSavedStateRepositoryForRestore@VirtualMachine@@UEAA?AV?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@H@Z; VirtualMachine::GetSavedStateRepositoryForRestore(int)
0x14017e8b4  mov     rdx, rax
0x14017e8b7  lea     rcx, [rsp+528h+var_488]
0x14017e8bf  call    ??4?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAAEBV01@$$QEAV01@@Z; Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::operator=(Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> &&)
0x14017e8c4  lea     rcx, [rsp+528h+var_318]
0x14017e8cc  call    ??1?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(void)
0x14017e8d1  xorps   xmm0, xmm0
0x14017e8d4  movups  [rsp+528h+var_300], xmm0
0x14017e8dc  xor     r8d, r8d
0x14017e8df  mov     rbx, [rsp+528h+var_488]
0x14017e8e7  mov     rdx, rbx
0x14017e8ea  lea     rcx, [rsp+528h+var_300]
0x14017e8f2  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x14017e8f7  nop
0x14017e8f8  cmp     dword ptr [rsp+528h+var_300+8], esi
0x14017e8ff  jl      short loc_14017E940
0x14017e901  mov     rax, [rbx]
0x14017e904  lea     r8, [rsp+528h+var_2E0]
0x14017e90c  lea     rdx, ?VM_SAVED_STATE_VMWP_VERSION@@3QBGB; "/savedstate/VmwpVersion"
0x14017e913  mov     rcx, rbx
0x14017e916  mov     rax, [rax+68h]
0x14017e91a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14017e91f  test    eax, eax
0x14017e921  jns     short loc_14017E93A
0x14017e923  mov     r8d, eax
0x14017e926  lea     rdx, aConfigreadfail; "ConfigReadFail:%ld"
0x14017e92d  lea     rcx, [rsp+528h+var_2E0]
0x14017e935  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x14017e93a  mov     edi, esi
0x14017e93c  mov     [rsp+528h+var_4D8], esi
0x14017e940  lea     rcx, [rsp+528h+var_300]; this
0x14017e948  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x14017e94d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14017e954  mov     ecx, 80h; unsigned __int64
0x14017e959  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14017e95e  mov     [rsp+528h+var_490], rax
0x14017e966  test    rax, rax
0x14017e969  jz      short loc_14017E97B
0x14017e96b  mov     rdx, rbx; struct VmRepository *
0x14017e96e  mov     rcx, rax; this
0x14017e971  call    ??0VmPrefixRepository@@QEAA@PEAVVmRepository@@PEBG@Z; VmPrefixRepository::VmPrefixRepository(VmRepository *,ushort const *)
0x14017e976  mov     r15, rax
0x14017e979  jmp     short loc_14017E97E
0x14017e97b  mov     r15, rsi
0x14017e97e  test    r15, r15
0x14017e981  jz      loc_14017F887
0x14017e987  lea     rcx, [r15+8]; this
0x14017e98b  call    ?IncrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::IncrementUserCount(void)
0x14017e990  mov     [rsp+528h+var_478], r15
0x14017e998  mov     [rsp+528h+var_30C], esi
0x14017e99f  xorps   xmm0, xmm0
0x14017e9a2  movups  [rsp+528h+var_300], xmm0
0x14017e9aa  mov     r8d, 1
0x14017e9b0  mov     rdx, rbx
0x14017e9b3  lea     rcx, [rsp+528h+var_300]
0x14017e9bb  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x14017e9c0  nop
0x14017e9c1  mov     edi, dword ptr [rsp+528h+var_300+8]
0x14017e9c8  test    edi, edi
0x14017e9ca  jns     short loc_14017EA04
0x14017e9cc  mov     [rsp+528h+var_4D8], edi
0x14017e9d0  mov     ebx, 4020h
0x14017e9d5  mov     ecx, ebx
0x14017e9d7  call    VmlIsDebugTraceEnabled
0x14017e9dc  test    eax, eax
0x14017e9de  jz      short loc_14017E9F2
0x14017e9e0  mov     r8d, edi
0x14017e9e3  lea     rdx, off_1402D9BF8; "Failed to lock runtime repository"
0x14017e9ea  mov     ecx, ebx
0x14017e9ec  call    VmlDebugTraceWithError
0x14017e9f1  nop
0x14017e9f2  lea     rcx, [rsp+528h+var_300]; this
0x14017e9fa  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x14017e9ff  jmp     loc_14017F8AD
0x14017ea04  mov     qword ptr [rsp+528h+var_318], rsi
0x14017ea0c  mov     rax, [rbx]
0x14017ea0f  lea     r8, [rsp+528h+var_318]
0x14017ea17  lea     rdx, ?VM_SAVED_STATE_VM_VERSION@@3QBGB; "/savedstate/VmVersion"
0x14017ea1e  mov     rcx, rbx
0x14017ea21  mov     rax, [rax+70h]
0x14017ea25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14017ea2a  mov     edi, eax
0x14017ea2c  mov     [rsp+528h+var_4D8], eax
0x14017ea30  test    eax, eax
0x14017ea32  jns     short loc_14017EA5E
0x14017ea34  mov     ebx, 4020h
0x14017ea39  mov     ecx, ebx
0x14017ea3b  call    VmlIsDebugTraceEnabled
0x14017ea40  test    eax, eax
0x14017ea42  jz      short loc_14017E9F2
0x14017ea44  mov     r9d, edi
0x14017ea47  lea     r8, aFailedToGetSav; "Failed to get saved state VmVersion"
0x14017ea4e  lea     rdx, aWorkertaskstar_3; "'WorkerTaskStarting::RunRestoreStartSte"...
0x14017ea55  mov     ecx, ebx
0x14017ea57  call    VmlDebugTrace
0x14017ea5c  jmp     short loc_14017E9F2
0x14017ea5e  mov     eax, [rsp+528h+var_318]
0x14017ea65  mov     [rsp+528h+var_30C], eax
0x14017ea6c  lea     rcx, [rsp+528h+var_300]; this
0x14017ea74  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x14017ea79  mov     rcx, [rsp+528h+var_480]
0x14017ea81  mov     rax, [rcx]
0x14017ea84  lea     rdx, [rsp+528h+var_30C]
0x14017ea8c  mov     rax, [rax]
0x14017ea8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14017ea94  test    al, al
0x14017ea96  jnz     loc_14017EB8F
0x14017ea9c  xorps   xmm0, xmm0
0x14017ea9f  movups  [rsp+528h+var_300], xmm0
0x14017eaa7  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14017eaaf  movdqu  [rsp+528h+var_2F0], xmm1
0x14017eab8  mov     word ptr [rsp+528h+var_300], si
0x14017eac0  lea     rdx, [rsp+528h+var_300]
0x14017eac8  mov     ecx, [rsp+528h+var_30C]
0x14017eacf  call    ?GetVmVersionString@@YAXIAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetVmVersionString(uint,std::wstring &)
0x14017ead4  lea     rax, [rsp+528h+var_300]
0x14017eadc  cmp     qword ptr [rsp+528h+var_2F0+8], 7
0x14017eae5  cmova   rax, qword ptr [rsp+528h+var_300]
0x14017eaee  mov     [rsp+528h+var_4A0], rax
0x14017eaf6  mov     rcx, [r14]
0x14017eaf9  lea     rax, [rcx+480h]
0x14017eb00  mov     [rsp+528h+var_4C0], rax
0x14017eb05  add     rcx, 10h; this
0x14017eb09  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x14017eb0e  mov     qword ptr [rsp+528h+var_318], rax
0x14017eb16  lea     rax, [rsp+528h+var_4A0]
0x14017eb1e  mov     [rsp+528h+var_4F8], rax; __int64
0x14017eb23  lea     rax, [rsp+528h+var_4C0]
0x14017eb28  mov     [rsp+528h+var_500], rax; __int64
0x14017eb2d  lea     rax, [rsp+528h+var_318]
0x14017eb35  mov     [rsp+528h+var_508], rax; __int64
0x14017eb3a  mov     edx, 5; unsigned int
0x14017eb3f  lea     rcx, MSVML_WP_SAVEDSTATE_VERSION_INCOMPATIBLE_ERROR; struct _EVENT_DESCRIPTOR *
0x14017eb46  call    ??$VmEventWriteAndReport@PEBGPEBGPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBG$$QEAPEBG33@Z; VmEventWriteAndReport<ushort const *,ushort const *,ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,ushort const * &&,ushort const * &&,ushort const * &&)
0x14017eb4b  mov     edi, 80048016h
0x14017eb50  mov     [rsp+528h+var_4D8], edi
0x14017eb54  mov     ebx, 4020h
0x14017eb59  mov     ecx, ebx
0x14017eb5b  call    VmlIsDebugTraceEnabled
0x14017eb60  test    eax, eax
0x14017eb62  jz      short loc_14017EB7D
0x14017eb64  mov     r9d, edi
0x14017eb67  lea     r8, aSavedStateVmve; "Saved state VmVersion is not supported"
0x14017eb6e  lea     rdx, aWorkertaskstar_3; "'WorkerTaskStarting::RunRestoreStartSte"...
0x14017eb75  mov     ecx, ebx
0x14017eb77  call    VmlDebugTrace
0x14017eb7c  nop
0x14017eb7d  lea     rcx, [rsp+528h+var_300]
0x14017eb85  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14017eb8a  jmp     loc_14017F8AD
0x14017eb8f  mov     [rsp+528h+var_318], esi
0x14017eb96  mov     rbx, rsi
0x14017eb99  mov     rax, [r14]
0x14017eb9c  mov     rcx, [rax+410h]
0x14017eba3  mov     rax, [rcx]
0x14017eba6  mov     rax, [rax+1F8h]
0x14017ebad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14017ebb2  mov     [rsp+528h+var_4B0], al
0x14017ebb6  mov     r12d, 2
0x14017ebbc  mov     rdx, [r14]
0x14017ebbf  mov     rcx, [rdx+588h]
0x14017ebc6  cmp     [rcx+6Ch], esi
0x14017ebc9  jz      short loc_14017EC13
0x14017ebcb  mov     rbx, [rdx+0A58h]
0x14017ebd2  mov     rcx, rbx
0x14017ebd5  shr     rcx, 1
0x14017ebd8  and     ecx, 8
0x14017ebdb  or      ecx, 6
0x14017ebde  test    bl, 40h
0x14017ebe1  jz      short loc_14017EBE7
0x14017ebe3  bts     ecx, 7
0x14017ebe7  test    byte ptr [r13+0], 10h
0x14017ebec  jz      short loc_14017EBF1
0x14017ebee  or      ecx, 10h
0x14017ebf1  test    byte ptr [r13+0], 20h
0x14017ebf6  jz      short loc_14017EBFB
0x14017ebf8  or      ecx, 20h
0x14017ebfb  test    byte ptr [r13+0], 40h
0x14017ec00  jz      short loc_14017EC05
0x14017ec02  or      ecx, 40h
0x14017ec05  mov     r12d, ecx
0x14017ec08  bts     r12d, 8
0x14017ec0d  test    al, al
0x14017ec0f  cmovz   r12d, ecx
0x14017ec13  mov     r8, r15
0x14017ec16  lea     rdx, [rsp+528h+var_300]
0x14017ec1e  lea     rcx, ?m_Instance@MemoryManager@@0V1@A; MemoryManager MemoryManager::m_Instance
0x14017ec25  call    ?RestoreCloneTemplateId@MemoryManager@@QEAA?AV?$optional@U_GUID@@@std@@PEAVVmRepository@@@Z; MemoryManager::RestoreCloneTemplateId(VmRepository *)
0x14017ec2a  cmp     [rax+10h], sil
0x14017ec2e  jz      short loc_14017EC3D
0x14017ec30  mov     [rsp+528h+var_318], 1
0x14017ec3b  jmp     short loc_14017EC5C
0x14017ec3d  mov     edi, 0C020h
0x14017ec42  mov     ecx, edi
0x14017ec44  call    VmlIsDebugTraceEnabled
0x14017ec49  test    eax, eax
0x14017ec4b  jz      short loc_14017EC5C
0x14017ec4d  lea     rdx, aRestoringMemor; "Restoring memory from saved state."
0x14017ec54  mov     ecx, edi
0x14017ec56  call    VmlDebugTrace
0x14017ec5b  nop
0x14017ec5c  test    byte ptr [r13+0], 1
0x14017ec61  jz      short loc_14017EC78
0x14017ec63  mov     rdx, r15; struct VmRepository *
0x14017ec66  mov     rcx, [r14]; this
0x14017ec69  call    ?RestoreIgvmSaveState@VirtualMachine@@UEAAJPEAVVmRepository@@@Z; VirtualMachine::RestoreIgvmSaveState(VmRepository *)
0x14017ec6e  mov     edi, eax
0x14017ec70  mov     [rsp+528h+var_4D8], eax
0x14017ec74  test    eax, eax
0x14017ec76  js      short loc_14017ECE1
0x14017ec78  mov     rcx, [r14]
0x14017ec7b  mov     r8d, r12d
0x14017ec7e  mov     rdx, r15
0x14017ec81  mov     rcx, [rcx+3D8h]
  ... truncated ...
```
