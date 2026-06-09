# WorkerTaskSaving::StartSave(void)

- ea: `0x1400cfa88`
- end: `0x1400d1148`
- name: `?StartSave@WorkerTaskSaving@@AEAAJXZ`
- size: `5824`
- prototype: `__int64 __fastcall(WorkerTaskSaving *__hidden this)`
- caller_count: `1`
- callee_count: `72`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140184fb0`

## callees

- `0x14001e628`
- `0x14002ecd0`
- `0x14002ed70`
- `0x140031c88`
- `0x140054508`
- `0x140054630`
- `0x1400561a8`
- `0x14005b628`
- `0x14006af38`
- `0x14007a72c`
- `0x14008f85c`
- `0x14008f900`
- `0x14008ff68`
- `0x14009b588`
- `0x14009bbc4`
- `0x14009d050`
- `0x14009d7ac`
- `0x14009d800`
- `0x14009dba0`
- `0x14009e5b0`
- `0x1400b0d40`
- `0x1400cc7f8`
- `0x1400cf8a0`
- `0x1400cfa88`
- `0x1400d1150`
- `0x1400d11b0`
- `0x1400d11e4`
- `0x1400d129c`
- `0x1400d12cc`
- `0x1400d1b0c`
- `0x1400d1bcc`
- `0x1400d1bf8`
- `0x1400d1cb8`
- `0x1400d1d78`
- `0x1400d1e38`
- `0x1400d1e64`
- `0x1400d1e90`
- `0x1400d1ebc`
- `0x1400d1f7c`
- `0x1400d1fa8`
- `0x1400d1fd4`
- `0x1400d2000`
- `0x1400d2194`
- `0x1400d21c0`
- `0x1400d2280`
- `0x1400d22ac`
- `0x1400d22e8`
- `0x1400d237c`
- `0x1400d243c`
- `0x1400d2468`

## import_xrefs

- `vid!VidPhuCommit` at `0x1400d0e4e`
- `vid!VidPhuCommit` at `0x1400d0e4e`
- `vid!VidCloneTemplateCreate` at `0x1400cffcd`
- `vid!VidCloneTemplateCreate` at `0x1400cffcd`

## string_xrefs

- `0x1400cfbc9`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400cfc4f`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400cfc8e`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400cfe0b`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400cfe6f`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400cfecb`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400cffdd`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400d01e0`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400d02de`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400d03ee`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400d0519`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400d0629`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400d0751`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400d08a4`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400d0911`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400d0a68`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400d0ac1`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400d0aee`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400d0b37`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400d0b6a`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400d0cb4`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400d0d51`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400d0ebb`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400d0f90`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400d0fd2`: `onecore\vm\worker\wpcore\workertasksaving.cpp`
- `0x1400d003f`: `SaveCloneTemplate`
- `0x1400cff41`: `CreateCloneTemplate`

## pseudocode

```c
// Hidden C++ exception states: #wind=47
__int64 __fastcall WorkerTaskSaving::StartSave(WorkerTaskSaving *this)
{
  int v2; // ecx
  VirtualMachine **v3; // r14
  const struct _GUID *v4; // r9
  VirtualMachine *v5; // rcx
  int v6; // eax
  VirtualMachine *v7; // rbx
  struct VmRepository *SavedStateRepository; // rax
  int v9; // eax
  const struct _GUID *v10; // rdi
  __int64 v11; // rbx
  char v12; // r13
  unsigned int v13; // r12d
  int v14; // edi
  WorkerTaskSaving *v15; // rcx
  struct VmRepository *v16; // rax
  __int64 v17; // r9
  int v18; // ebx
  VirtualMachine *v19; // rcx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, struct VmRepository *); // rbx
  struct VmRepository *v22; // rax
  int v23; // eax
  const struct _GUID *v24; // rdi
  __int64 v25; // rbx
  __int64 v26; // rax
  const char *v27; // r9
  const struct _GUID *v28; // rdi
  __int64 v29; // rbx
  struct VmRepository *v30; // rax
  __int64 v31; // rdi
  void (__fastcall *v32)(__int64, struct VmRepository *); // rbx
  struct VmRepository *v33; // rdx
  struct VmRepository *v34; // rax
  unsigned int v35; // r13d
  int v36; // eax
  __int64 v37; // rbx
  struct VmRepository *v38; // rax
  int v39; // eax
  const struct _GUID *v40; // rdi
  __int64 v41; // rbx
  unsigned int v42; // r12d
  __int64 v43; // rdx
  int v44; // eax
  const struct _GUID *v45; // rdi
  __int64 v46; // rbx
  int v47; // r12d
  __int64 v48; // rdi
  __int64 (__fastcall *v49)(__int64, struct VmRepository *); // rbx
  struct VmRepository *v50; // rdx
  int v51; // eax
  const struct _GUID *v52; // rdi
  __int64 v53; // rbx
  unsigned int v54; // r12d
  __int64 v55; // rdx
  int v56; // eax
  const struct _GUID *v57; // rdi
  __int64 v58; // rbx
  int v59; // r12d
  __int64 v60; // rdi
  __int64 (__fastcall *v61)(__int64, struct VmRepository *); // rbx
  struct VmRepository *v62; // rdx
  int v63; // eax
  const struct _GUID *v64; // rdi
  __int64 v65; // rbx
  unsigned int v66; // r12d
  __int64 v67; // rdi
  __int64 (__fastcall *v68)(__int64, struct VmRepository *); // rbx
  struct VmRepository *v69; // rdx
  int v70; // eax
  const struct _GUID *v71; // rdi
  __int64 v72; // rbx
  unsigned int v73; // r12d
  VirtualMachine *v74; // rbx
  struct VmRepository *v75; // rax
  int v76; // eax
  int v77; // eax
  int v78; // eax
  int v79; // eax
  VirtualMachine *v80; // rdi
  __int64 v81; // rbx
  int v82; // r12d
  unsigned int v83; // r12d
  struct VmRepository *v84; // rdi
  int v85; // ebx
  __int64 v86; // rcx
  int v87; // eax
  VirtualMachine *v88; // rdi
  __int64 v89; // rbx
  const char *v90; // r9
  int v91; // eax
  int v92; // edi
  wil *v93; // rcx
  int v94; // r15d
  int v95; // eax
  int v96; // eax
  const char *v97; // r9
  VirtualMachine *v98; // rcx
  struct _EVENT_DESCRIPTOR *v99; // rcx
  unsigned int v101; // [rsp+20h] [rbp-928h]
  int v102; // [rsp+20h] [rbp-928h]
  int v103; // [rsp+20h] [rbp-928h]
  unsigned int v104[2]; // [rsp+50h] [rbp-8F8h] BYREF
  bool v105; // [rsp+58h] [rbp-8F0h]
  char v106; // [rsp+59h] [rbp-8EFh]
  char v107; // [rsp+5Ah] [rbp-8EEh]
  char v108; // [rsp+5Bh] [rbp-8EDh]
  int v109; // [rsp+5Ch] [rbp-8ECh] BYREF
  int v110; // [rsp+60h] [rbp-8E8h]
  unsigned __int64 VmName; // [rsp+68h] [rbp-8E0h] BYREF
  int v112; // [rsp+70h] [rbp-8D8h]
  int v113; // [rsp+74h] [rbp-8D4h]
  int v114; // [rsp+78h] [rbp-8D0h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+80h] [rbp-8C8h] BYREF
  __int64 v116; // [rsp+90h] [rbp-8B8h] BYREF
  _BYTE v117[336]; // [rsp+A0h] [rbp-8A8h] BYREF
  _BYTE v118[336]; // [rsp+1F0h] [rbp-758h] BYREF
  int v119; // [rsp+340h] [rbp-608h] BYREF
  int v120; // [rsp+344h] [rbp-604h] BYREF
  __int64 v121; // [rsp+348h] [rbp-600h] BYREF
  _DWORD v122[4]; // [rsp+350h] [rbp-5F8h] BYREF
  struct _GUID v123; // [rsp+360h] [rbp-5E8h] BYREF
  _QWORD v124[42]; // [rsp+370h] [rbp-5D8h] BYREF
  _QWORD v125[42]; // [rsp+4C0h] [rbp-488h] BYREF
  _BYTE v126[184]; // [rsp+610h] [rbp-338h] BYREF
  char *v127; // [rsp+6C8h] [rbp-280h]
  unsigned int v128; // [rsp+6D8h] [rbp-270h]
  _BYTE v129[40]; // [rsp+710h] [rbp-238h] BYREF
  _BYTE v130[72]; // [rsp+738h] [rbp-210h] BYREF
  _QWORD v131[42]; // [rsp+780h] [rbp-1C8h] BYREF
  __int64 v132[4]; // [rsp+8D0h] [rbp-78h] BYREF
  __int64 v133[4]; // [rsp+8F0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+948h] [rbp+0h]

  v104[0] = 0;
  memset_0(v126, 0, 0xF8u);
  GmoRamOperationSave::GmoRamOperationSave((GmoRamOperationSave *)v126);
  v109 = 0;
  v113 = 0;
  v112 = 0;
  v108 = 0;
  v119 = 0;
  v2 = *((_DWORD *)this + 101);
  v110 = v2 & 2;
  v114 = v110;
  v120 = 0;
  v122[0] = 0;
  LODWORD(VmName) = v2 & 4;
  v106 = 0;
  v107 = 0;
  v123 = 0;
  v3 = (VirtualMachine **)((char *)this + 16);
  v116 = (__int64)this + 16;
  v4 = (const struct _GUID *)(*(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::SavingTask>::GetCurrentActivity(this, v118)
                                        + 272)
                            + 8LL);
  Vml::VmPerfTraceOperation::VmPerfTraceOperation(
    (Vml::VmPerfTraceOperation *)v129,
    (struct Vml::VmPerfTraceComponent *)&g_WorkerPerfTrace,
    (const struct _GUID *)(*((_QWORD *)this + 2) + 1136LL),
    v4);
  VmWorkerTrace::SavingTask::~SavingTask((VmWorkerTrace::SavingTask *)v118);
  try
  {
    v5 = *v3;
    LODWORD(v121) = *(_DWORD *)(*((_QWORD *)*v3 + 177) + 376LL);
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)v5 + 124) + 384LL))(*((_QWORD *)v5 + 124)) )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2DE,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
        (const char *)0x32,
        v101);
    (*(void (__fastcall **)(_QWORD, int *, _DWORD *))(**((_QWORD **)*v3 + 134) + 80LL))(
      *((_QWORD *)*v3 + 134),
      &v120,
      v122);
    (*(void (__fastcall **)(_QWORD, int *))(**((_QWORD **)*v3 + 134) + 112LL))(*((_QWORD *)*v3 + 134), &v119);
    if ( v119 )
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)*v3 + 134) + 168LL))(*((_QWORD *)*v3 + 134));
      if ( v6 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2EA,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
          (const char *)(unsigned int)v6,
          v101);
    }
    v7 = *v3;
    if ( *((_BYTE *)*v3 + 2968) )
    {
      SavedStateRepository = WorkerTaskSaving::GetSavedStateRepository(this);
      v9 = VirtualMachine::SaveIgvmSaveState(v7, SavedStateRepository);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2EF,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
          (const char *)(unsigned int)v9,
          v101);
    }
    memset_0(v125, 0, sizeof(v125));
    v10 = (const struct _GUID *)*v3;
    v11 = *(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::SavingTask>::GetCurrentActivity(this, v124) + 272);
    memset_0(v125, 0, sizeof(v125));
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v125);
    v125[0] = &VmWorkerTrace::SaveGuestRamInfo::`vftable';
    v104[0] = 2;
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(v125, v11 + 8);
    VmWorkerTrace::SaveGuestRamInfo::StartActivity((VmWorkerTrace::SaveGuestRamInfo *)v125, v10 + 71);
    v12 = 1;
    v13 = 1;
    VmWorkerTrace::SavingTask::~SavingTask((VmWorkerTrace::SavingTask *)v124);
    v14 = qword_1403C0440;
    LODWORD(v11) = WorkerTaskSaving::GetFastSaveType(this);
    v16 = WorkerTaskSaving::GetSavedStateRepository(v15);
    v102 = v14;
    LOBYTE(v17) = 1;
    MemoryManager::SaveRamInformation(&MemoryManager::m_Instance, v16, (unsigned int)v11, v17);
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v125, 0);
    VmWorkerTrace::SaveGuestRamInfo::~SaveGuestRamInfo((VmWorkerTrace::SaveGuestRamInfo *)v125);
    v112 = 1;
    if ( *((_QWORD *)this + 65) )
    {
      WorkerTaskSaving::CompletePrepareTask(this, 0);
      if ( !Vml::VmWaitable::Wait((VirtualMachine *)((char *)*v3 + 2304), 0x927C0u) )
      {
        v18 = -2147217408;
LABEL_16:
        v12 = 0;
LABEL_17:
        if ( v12 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x31F,
            (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
            (const char *)(unsigned int)v18,
            v14);
        v19 = *v3;
        v121 = (__int64)*v3 + 1152;
        VmName = (unsigned __int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)v19 + 16));
        VmEventWriteAndReport<unsigned short const *,unsigned short const *>(
          (struct _EVENT_DESCRIPTOR *)&MSVML_TIMEOUT_WAITING_FINALIZE_SAVE,
          5u,
          (__int64)&VmName,
          (__int64)&v121);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x328,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
          (const char *)(unsigned int)v18,
          v103);
      }
      v18 = *((_DWORD *)*v3 + 578);
      if ( v18 < 0 )
      {
        if ( v18 == -2147467260 )
          goto LABEL_17;
        goto LABEL_16;
      }
    }
    if ( v110 && (*((_DWORD *)this + 101) & 0x40000) != 0 )
    {
      v20 = *((_QWORD *)*v3 + 128);
      v21 = *(__int64 (__fastcall **)(__int64, struct VmRepository *))(*(_QWORD *)(v20 + 8) + 80LL);
      v22 = WorkerTaskSaving::GetSavedStateRepository(this);
      v23 = v21(v20 + 8, v22);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x337,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
          (const char *)(unsigned int)v23,
          v102);
      v108 = 1;
    }
    if ( !*((_DWORD *)this + 104) )
      WorkerTaskSaving::StopVm(this);
    if ( (_DWORD)VmName )
    {
      memset_0(v124, 0, sizeof(v124));
      v24 = (const struct _GUID *)*v3;
      v25 = *(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::SavingTask>::GetCurrentActivity(this, v117) + 272);
      memset_0(v124, 0, sizeof(v124));
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v124);
      v124[0] = &VmWorkerTrace::CreateCloneTemplate::`vftable';
      v104[0] = 9;
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
        v124,
        v25 + 8);
      VmWorkerTrace::CreateCloneTemplate::StartActivity((VmWorkerTrace::CreateCloneTemplate *)v124, v24 + 71);
      VmWorkerTrace::SavingTask::~SavingTask((VmWorkerTrace::SavingTask *)v117);
      v26 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)*v3 + 128) + 24LL))(*((_QWORD *)*v3 + 128) + 24LL);
      if ( !(unsigned int)VidCloneTemplateCreate(v26, 0, &v123) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x34B,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
          v27);
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v124, 0);
      memset_0(v125, 0, sizeof(v125));
      v28 = (const struct _GUID *)*v3;
      v29 = *(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::SavingTask>::GetCurrentActivity(this, v117) + 272);
      memset_0(v125, 0, sizeof(v125));
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v125);
      v125[0] = &VmWorkerTrace::SaveCloneTemplate::`vftable';
      v104[0] = 37;
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
        v125,
        v29 + 8);
      VmWorkerTrace::SaveCloneTemplate::StartActivity((VmWorkerTrace::SaveCloneTemplate *)v125, v28 + 71);
      v13 = 21;
      VmWorkerTrace::SavingTask::~SavingTask((VmWorkerTrace::SavingTask *)v117);
      v30 = WorkerTaskSaving::GetSavedStateRepository(this);
      MemoryManager::SaveCloneTemplateId((MemoryManager *)&MemoryManager::m_Instance, v30, &v123);
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v125, 0);
      VmWorkerTrace::SaveCloneTemplate::~SaveCloneTemplate((VmWorkerTrace::SaveCloneTemplate *)v125);
      VmWorkerTrace::CreateCloneTemplate::~CreateCloneTemplate((VmWorkerTrace::CreateCloneTemplate *)v124);
    }
    if ( (*((_BYTE *)this + 424) & 0x22) != 2 )
    {
      v31 = *((_QWORD *)*v3 + 128);
      v32 = *(void (__fastcall **)(__int64, struct VmRepository *))(*(_QWORD *)v31 + 256LL);
      v33 = WorkerTaskSaving::GetSavedStateRepository(this);
      v32(v31, v33);
      if ( !v120 )
      {
        v34 = WorkerTaskSaving::GetSavedStateRepository(this);
        MemoryManager::SaveVtlProtections((MemoryManager *)&MemoryManager::m_Instance, v34);
      }
    }
    v35 = (v110 != 0 ? 2 : 0) | (*((_QWORD *)this + 53) >> 2) & 4;
    if ( (*((_BYTE *)this + 424) & 0x40) != 0 )
      v35 |= 0x40u;
    v36 = *((_DWORD *)this + 101);
    if ( (v36 & 0x400) != 0 )
      v35 |= 8u;
    if ( (v36 & 0x800) != 0 )
      v35 |= 0x10u;
    if ( (v36 & 0x1000) != 0 )
      v35 |= 0x20u;
    if ( (v36 & 0x2000) != 0 )
      v35 |= 0x80u;
    if ( (v36 & 0x40000) != 0 )
      v35 |= 0x100u;
    if ( (v36 & 0x200) == 0 )
    {
      v37 = *((_QWORD *)*v3 + 123);
      v38 = WorkerTaskSaving::GetSavedStateRepository(this);
      v39 = VirtualMotherboard::Save(v37, v38, v35);
      if ( v39 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x388,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
          (const char *)(unsigned int)v39,
          v102);
    }
    v40 = (const struct _GUID *)*v3;
    if ( *((_DWORD *)*v3 + 653) )
    {
      memset_0(v125, 0, sizeof(v125));
      v41 = *(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::SavingTask>::GetCurrentActivity(this, v117) + 272);
      memset_0(v125, 0, sizeof(v125));
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v125);
      v125[0] = &VmWorkerTrace::SuspendEpf::`vftable';
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
        v125,
        v41 + 8);
      VmWorkerTrace::SuspendEpf::StartActivity((VmWorkerTrace::SuspendEpf *)v125, v40 + 71);
      v42 = v13 & 0xFFFFFF3F | 0x40;
      v104[0] = v42;
      VmWorkerTrace::SavingTask::~SavingTask((VmWorkerTrace::SavingTask *)v117);
      LOBYTE(v43) = 1;
      v44 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)*v3 + 128) + 288LL))(*((_QWORD *)*v3 + 128), v43);
      if ( v44 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x394,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
          (const char *)(unsigned int)v44,
          v102);
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v125, 0);
      v106 = 1;
      memset_0(v124, 0, sizeof(v124));
      v45 = (const struct _GUID *)*v3;
      v46 = *(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::SavingTask>::GetCurrentActivity(this, v117) + 272);
      memset_0(v124, 0, sizeof(v124));
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v124);
      v124[0] = &VmWorkerTrace::SaveEpfState::`vftable';
      v47 = v42 | 0x200;
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
        v124,
        v46 + 8);
      VmWorkerTrace::SaveEpfState::StartActivity((VmWorkerTrace::SaveEpfState *)v124, v45 + 71);
      v104[0] = v47 & 0xFFFFFDFF;
      v13 = v47 & 0xFFFFFCFF | 0x100;
      VmWorkerTrace::SavingTask::~SavingTask((VmWorkerTrace::SavingTask *)v117);
      v48 = *((_QWORD *)*v3 + 128);
      v49 = *(__int64 (__fastcall **)(__int64, struct VmRepository *))(*(_QWORD *)v48 + 272LL);
      v50 = WorkerTaskSaving::GetSavedStateRepository(this);
      v51 = v49(v48, v50);
      if ( v51 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x39C,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
          (const char *)(unsigned int)v51,
          v102);
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v124, 0);
      VmWorkerTrace::SaveEpfState::~SaveEpfState((VmWorkerTrace::SaveEpfState *)v124);
      VmWorkerTrace::SuspendEpf::~SuspendEpf((VmWorkerTrace::SuspendEpf *)v125);
    }
    v52 = (const struct _GUID *)*v3;
    if ( *((_BYTE *)*v3 + 2616) )
    {
      memset_0(v125, 0, sizeof(v125));
      v53 = *(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::SavingTask>::GetCurrentActivity(this, v117) + 272);
      memset_0(v125, 0, sizeof(v125));
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v125);
      v125[0] = &VmWorkerTrace::SuspendSchedulerAssist::`vftable';
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
        v125,
        v53 + 8);
      VmWorkerTrace::SuspendSchedulerAssist::StartActivity((VmWorkerTrace::SuspendSchedulerAssist *)v125, v52 + 71);
      v54 = v13 & 0xFFFFF3FF | 0x400;
      v104[0] = v54;
      VmWorkerTrace::SavingTask::~SavingTask((VmWorkerTrace::SavingTask *)v117);
      LOBYTE(v55) = 1;
      v56 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)*v3 + 128) + 312LL))(*((_QWORD *)*v3 + 128), v55);
      if ( v56 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3A5,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
          (const char *)(unsigned int)v56,
          v102);
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v125, 0);
      v107 = 1;
      memset_0(v124, 0, sizeof(v124));
      v57 = (const struct _GUID *)*v3;
      v58 = *(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::SavingTask>::GetCurrentActivity(this, v117) + 272);
      memset_0(v124, 0, sizeof(v124));
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v124);
      v124[0] = &VmWorkerTrace::SaveSchedulerAssistState::`vftable';
      v59 = v54 | 0x2000;
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
        v124,
        v58 + 8);
      VmWorkerTrace::SaveSchedulerAssistState::StartActivity((VmWorkerTrace::SaveSchedulerAssistState *)v124, v57 + 71);
      v104[0] = v59 & 0xFFFFDFFF;
      v13 = v59 & 0xFFFFCFFF | 0x1000;
      VmWorkerTrace::SavingTask::~SavingTask((VmWorkerTrace::SavingTask *)v117);
      v60 = *((_QWORD *)*v3 + 128);
      v61 = *(__int64 (__fastcall **)(__int64, struct VmRepository *))(*(_QWORD *)v60 + 296LL);
      v62 = WorkerTaskSaving::GetSavedStateRepository(this);
      v63 = v61(v60, v62);
      if ( v63 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3AD,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
          (const char *)(unsigned int)v63,
          v102);
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v124, 0);
      VmWorkerTrace::SaveSchedulerAssistState::~SaveSchedulerAssistState((VmWorkerTrace::SaveSchedulerAssistState *)v124);
      VmWorkerTrace::SuspendSchedulerAssist::~SuspendSchedulerAssist((VmWorkerTrace::SuspendSchedulerAssist *)v125);
    }
    memset_0(v131, 0, sizeof(v131));
    v64 = (const struct _GUID *)*v3;
    v65 = *(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::SavingTask>::GetCurrentActivity(this, v117) + 272);
    memset_0(v131, 0, sizeof(v131));
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v131);
    v131[0] = &VmWorkerTrace::SaveIsolationControlState::`vftable';
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(v131, v65 + 8);
    VmWorkerTrace::SaveIsolationControlState::StartActivity((VmWorkerTrace::SaveIsolationControlState *)v131, v64 + 71);
    v66 = v13 & 0xFFFF3FFF | 0x4000;
    v104[0] = v66;
    VmWorkerTrace::SavingTask::~SavingTask((VmWorkerTrace::SavingTask *)v117);
    v67 = *((_QWORD *)*v3 + 130);
    v68 = *(__int64 (__fastcall **)(__int64, struct VmRepository *))(*(_QWORD *)v67 + 760LL);
    v69 = WorkerTaskSaving::GetSavedStateRepository(this);
    v70 = v68(v67, v69);
    if ( v70 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3B5,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
        (const char *)(unsigned int)v70,
        v102);
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v131, 0);
    memset_0(v124, 0, sizeof(v124));
    v71 = (const struct _GUID *)*v3;
    v72 = *(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::SavingTask>::GetCurrentActivity(this, v125) + 272);
    memset_0(v124, 0, sizeof(v124));
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v124);
    v124[0] = &VmWorkerTrace::SavePartitionStates::`vftable';
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(v124, v72 + 8);
    VmWorkerTrace::SavePartitionStates::StartActivity((VmWorkerTrace::SavePartitionStates *)v124, v71 + 71);
    v73 = v66 & 0xFFFCFFFF | 0x10000;
    v104[0] = v73;
    VmWorkerTrace::SavingTask::~SavingTask((VmWorkerTrace::SavingTask *)v125);
    v104[0] = (*((_DWORD *)this + 101) >> 6) & 8;
    if ( (unsigned int)WorkerTaskSaving::GetFastSaveType(this) == 2 && (*((_BYTE *)this + 424) & 1) != 0
      || (v105 = 0, (unsigned int)WorkerTaskSaving::GetFastSaveType(this) == 4) && (*((_BYTE *)this + 424) & 0x21) == 1 )
    {
      v105 = 1;
    }
    v74 = *v3;
    v75 = WorkerTaskSaving::GetSavedStateRepository(this);
    v76 = VirtualMachine::SavePartitionStates(v74, v75, v105, v104[0]);
    if ( v76 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3D0,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
        (const char *)(unsigned int)v76,
        v102);
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v124, 0);
    VmWorkerTrace::SavePartitionStates::~SavePartitionStates((VmWorkerTrace::SavePartitionStates *)v124);
    WorkerAsyncTaskBase::UpdateStatusProgress(this, 0x14u, &v109);
    if ( !v110 && !(_DWORD)VmName )
    {
      if ( v109 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3DE,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
          (const char *)0x80042001LL,
          v102);
      memset_0(v124, 0, sizeof(v124));
      EventDescriptor = (EVENT_DESCRIPTOR)VMWP_PERF_WORKER_SAVE_START;
      VmPerf::StartVmlActivity_VmWorkerTrace::SaveGuestRam_(
        (VmWorkerTrace::SaveGuestRam *)v124,
        (struct _GUID *)*v3 + 71,
        (Vml::VmPerfTraceOperation *)v129,
        &EventDescriptor);
      *(_QWORD *)&EventDescriptor.Id = WorkerTaskSaving::GetSavedStateRepository(this);
      *(_QWORD *)v104 = 0;
      if ( (*((_DWORD *)this + 101) & 0x20000) != 0 )
      {
        VmName = 0;
        VirtualMachine::GetVtl2PrivateRamRange(*v3, &VmName, (unsigned __int64 *)v104);
        MemoryManager::GpaIndexToRamIndex((MemoryManager *)&MemoryManager::m_Instance, VmName);
        if ( !*(_QWORD *)v104 )
          MemoryManager::GetRamSizeInPages((MemoryManager *)&MemoryManager::m_Instance);
      }
      else
      {
        MemoryManager::GetRamSizeInPages((MemoryManager *)&MemoryManager::m_Instance);
      }
      v102 = 98;
      v77 = GmoRamOperationSource::Initialize(v126, *(_QWORD *)&EventDescriptor.Id, *v3, *((_QWORD *)this + 3));
      if ( v77 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x415,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
          (const char *)(unsigned int)v77,
          98);
      v113 = 1;
      if ( v119 )
      {
        v78 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**((_QWORD **)*v3 + 134) + 184LL))(
                *((_QWORD *)*v3 + 134),
                v128,
                256,
                2);
        if ( v78 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x421,
            (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
            (const char *)(unsigned int)v78,
            98);
      }
      v79 = GmoRamOperation::WorkThreadsStart((GmoRamOperation *)v126);
      if ( v79 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x427,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
          (const char *)(unsigned int)v79,
          98);
      GmoRamOperation::WorkDispatch((GmoRamOperation *)v126);
      WorkerAsyncTaskBase::UpdateStatusProgress(this, 0x28u, &v109);
      if ( v109 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x430,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
          (const char *)0x80042001LL,
          98);
      GmoRamOperation::WorkThreadsWaitForExit((GmoRamOperation *)v126);
      if ( (int)v127 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x437,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
          (const char *)(unsigned int)v127,
          98);
      EventDescriptor = (EVENT_DESCRIPTOR)VMWP_PERF_WORKER_SAVE_STOP;
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v124, 0);
      Vml::VmPerfTraceOperation::EndOperation<>((Vml::VmPerfTraceOperation *)v129, &EventDescriptor);
      VmWorkerTrace::SaveGuestRam::~SaveGuestRam((VmWorkerTrace::SaveGuestRam *)v124);
    }
    memset_0(v124, 0, sizeof(v124));
    v80 = *v3;
    v81 = *(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::SavingTask>::GetCurrentActivity(this, v117) + 272);
    memset_0(v124, 0, sizeof(v124));
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v124);
    v124[0] = &VmWorkerTrace::FinalizeRepository::`vftable';
    v82 = v73 | 0x80000;
    v104[0] = v82;
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(v124, v81 + 8);
    VmWorkerTrace::FinalizeRepository::StartActivity(
      (VmWorkerTrace::FinalizeRepository *)v124,
      (const struct _GUID *)v80 + 71);
    v83 = v82 & 0xFFF3FFFF | 0x40000;
    v104[0] = v83;
    VmWorkerTrace::SavingTask::~SavingTask((VmWorkerTrace::SavingTask *)v117);
    v84 = WorkerTaskSaving::GetSavedStateRepository(this);
    EventDescriptor = 0;
    v85 = 1;
    VmRepositoryAutoLock::VmRepositoryAutoLock(&EventDescriptor, v84, 1);
    if ( SLODWORD(EventDescriptor.Keyword) < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x441,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
        (const char *)LODWORD(EventDescriptor.Keyword),
        v102);
    VmName = 0;
    if ( (*((_BYTE *)this + 404) & 0x10) != 0 )
    {
      LODWORD(v121) = 1;
      v102 = 0;
      (*(void (__fastcall **)(struct VmRepository *, _QWORD, __int64 *, __int64))(*(_QWORD *)v84 + 272LL))(
        v84,
        0,
        &v121,
        4);
      wil::details::unique_storage<wil::details::resource_policy<VmRepository *,void (*)(VmRepository *),&void Details::ReenableFlushes(VmRepository *),wistd::integral_constant<unsigned __int64,0>,VmRepository *,VmRepository *,0,std::nullptr_t>>::reset(
        &VmName,
        v84);
    }
    if ( v110 )
    {
      v86 = *((_QWORD *)*v3 + 179);
      if ( v86 )
        *(_DWORD *)(v86 + 24) = 1;
    }
    v87 = (*(__int64 (__fastcall **)(struct VmRepository *))(*(_QWORD *)v84 + 224LL))(v84);
    if ( v87 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x454,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
        (const char *)(unsigned int)v87,
        v102);
    wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v124, 0);
    wil::details::unique_storage<wil::details::resource_policy<VmRepository *,void (*)(VmRepository *),&void Details::ReenableFlushes(VmRepository *),wistd::integral_constant<unsigned __int64,0>,VmRepository *,VmRepository *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<VmRepository *,void (*)(VmRepository *),&void Details::ReenableFlushes(VmRepository *),wistd::integral_constant<unsigned __int64,0>,VmRepository *,VmRepository *,0,std::nullptr_t>>(&VmName);
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)&EventDescriptor);
    VmWorkerTrace::FinalizeRepository::~FinalizeRepository((VmWorkerTrace::FinalizeRepository *)v124);
    if ( v110 )
    {
      memset_0(v124, 0, sizeof(v124));
      v88 = *v3;
      v89 = *(_QWORD *)(WorkerAsyncTask<VmWorkerTrace::SavingTask>::GetCurrentActivity(this, v117) + 272);
      memset_0(v124, 0, sizeof(v124));
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v124);
      v124[0] = &VmWorkerTrace::PersistRamInformation::`vftable';
      v104[0] = v83 | 0x200000;
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
        v124,
        v89 + 8);
      VmWorkerTrace::PersistRamInformation::StartActivity(
        (VmWorkerTrace::PersistRamInformation *)v124,
        (const struct _GUID *)v88 + 71);
      VmWorkerTrace::SavingTask::~SavingTask((VmWorkerTrace::SavingTask *)v117);
      if ( !(unsigned int)VidPhuCommit(xmmword_1403C0360) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x1CE9,
          (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
          v90);
      wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v124, 0);
      if ( (*((_DWORD *)this + 101) & 0x400) != 0 )
      {
        v91 = VirtualMotherboard::PerformHandleTransfer(*((_QWORD *)*v3 + 123), v35, *((_QWORD *)this + 51));
        if ( v91 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x46E,
            (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
            (const char *)(unsigned int)v91,
            v102);
      }
      VmWorkerTrace::PersistRamInformation::~PersistRamInformation((VmWorkerTrace::PersistRamInformation *)v124);
      v85 = 1;
    }
    v92 = 0;
    v109 = 0;
    VmWorkerTrace::SaveIsolationControlState::~SaveIsolationControlState((VmWorkerTrace::SaveIsolationControlState *)v131);
    v94 = v110;
  }
  catch ( ... )
  {
    v109 = wil::ResultFromCaughtException(v93);
    v92 = v109;
    v85 = v112;
    v94 = v114;
    v3 = (VirtualMachine **)v116;
  }
  if ( v113 )
    GmoRamOperation::Teardown((GmoRamOperation *)v126);
  if ( v119 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)*v3 + 134) + 192LL))(*((_QWORD *)*v3 + 134));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)*v3 + 134) + 176LL))(*((_QWORD *)*v3 + 134));
  }
  if ( v106 )
  {
    v95 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)*v3 + 128) + 288LL))(*((_QWORD *)*v3 + 128), 0);
    if ( v95 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x489,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
        (const char *)(unsigned int)v95,
        v102);
  }
  if ( v107 )
  {
    v96 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)*v3 + 128) + 312LL))(*((_QWORD *)*v3 + 128), 0);
    if ( v96 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x491,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
        (const char *)(unsigned int)v96,
        v102);
  }
  if ( v92 < 0 )
  {
    if ( v85 && v94 )
    {
      try
      {
        MemoryManager::UnPersistRamInformation((MemoryManager *)&MemoryManager::m_Instance);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x4A0,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksaving.cpp",
          v97);
        v92 = v109;
        v94 = v114;
        v3 = (VirtualMachine **)v116;
      }
    }
    if ( v108 && v94 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)*v3 + 128) + 8LL) + 96LL))(*((_QWORD *)*v3 + 128) + 8LL);
    if ( v92 != -2147213311 )
    {
      _snwprintf_s<16>(v133, 16, L"%%%%%u", v92 & 0xEFFFFFFF);
      _snwprintf_s<16>(v132, 16, L"0x%08X", v92 & 0xEFFFFFFF);
      v98 = *v3;
      *(_QWORD *)&EventDescriptor.Id = (char *)*v3 + 1152;
      v116 = (__int64)VirtualMachine::GetVmName((VirtualMachine *)((char *)v98 + 16));
      v99 = (struct _EVENT_DESCRIPTOR *)MSVML_GMO_FAST_SAVE_ERROR;
      if ( !v94 )
        v99 = (struct _EVENT_DESCRIPTOR *)&MSVML_GMO_SAVE_ERROR;
      VmEventWriteAndReport<unsigned short const *,unsigned short const *,unsigned short (&)[16],unsigned short (&)[16]>(
        v99,
        5u,
        (__int64)&v116,
        (__int64)&EventDescriptor,
        (__int64)v133,
        (__int64)v132);
    }
  }
  std::wstring::_Tidy_deallocate(v130);
  GmoRamOperationSave::~GmoRamOperationSave((GmoRamOperationSave *)v126);
  return (unsigned int)v92;
}

```

## disassembly

```asm
0x1400cfa88  mov     [rsp+arg_8], rbx
0x1400cfa8d  mov     [rsp+arg_10], rsi
0x1400cfa92  push    rdi
0x1400cfa93  push    r12
0x1400cfa95  push    r13
0x1400cfa97  push    r14
0x1400cfa99  push    r15
0x1400cfa9b  sub     rsp, 920h
0x1400cfaa2  mov     rax, cs:__security_cookie
0x1400cfaa9  xor     rax, rsp
0x1400cfaac  mov     [rsp+948h+var_38], rax
0x1400cfab4  mov     r15, rcx
0x1400cfab7  xor     esi, esi
0x1400cfab9  mov     [rsp+948h+var_8F8], esi
0x1400cfabd  xor     edx, edx; Val
0x1400cfabf  mov     r8d, 0F8h; Size
0x1400cfac5  lea     rcx, [rsp+948h+var_338]; void *
0x1400cfacd  call    memset_0
0x1400cfad2  lea     rcx, [rsp+948h+var_338]; this
0x1400cfada  call    ??0GmoRamOperationSave@@QEAA@XZ; GmoRamOperationSave::GmoRamOperationSave(void)
0x1400cfadf  nop
0x1400cfae0  mov     [rsp+948h+var_8EC], esi
0x1400cfae4  mov     [rsp+948h+var_8D4], esi
0x1400cfae8  mov     [rsp+948h+var_8D8], esi
0x1400cfaec  mov     [rsp+948h+var_8ED], sil
0x1400cfaf1  mov     [rsp+948h+var_608], esi
0x1400cfaf8  mov     ecx, [r15+194h]
0x1400cfaff  mov     eax, ecx
0x1400cfb01  and     eax, 2
0x1400cfb04  mov     [rsp+948h+var_8E8], eax
0x1400cfb08  mov     [rsp+948h+var_8D0], eax
0x1400cfb0c  mov     [rsp+948h+var_604], esi
0x1400cfb13  mov     [rsp+948h+var_5F8], esi
0x1400cfb1a  and     ecx, 4
0x1400cfb1d  mov     dword ptr [rsp+948h+var_8E0], ecx
0x1400cfb21  mov     [rsp+948h+var_8EF], sil
0x1400cfb26  mov     [rsp+948h+var_8EE], sil
0x1400cfb2b  xorps   xmm0, xmm0
0x1400cfb2e  movdqa  xmmword ptr [rsp+948h+var_5E8.Data1], xmm0
0x1400cfb37  lea     rdx, [rsp+948h+var_758]
0x1400cfb3f  mov     rcx, r15
0x1400cfb42  call    ?GetCurrentActivity@?$WorkerAsyncTask@VSavingTask@VmWorkerTrace@@@@IEAA?AVSavingTask@VmWorkerTrace@@XZ; WorkerAsyncTask<VmWorkerTrace::SavingTask>::GetCurrentActivity(void)
0x1400cfb47  nop
0x1400cfb48  lea     r14, [r15+10h]
0x1400cfb4c  mov     [rsp+948h+var_8B8], r14
0x1400cfb54  mov     r9, [rax+110h]
0x1400cfb5b  add     r9, 8; struct _GUID *
0x1400cfb5f  mov     r8, [r14]
0x1400cfb62  add     r8, 470h; struct _GUID *
0x1400cfb69  lea     rdx, ?g_WorkerPerfTrace@@3VVmPerfTraceComponent@Vml@@A; struct Vml::VmPerfTraceComponent *
0x1400cfb70  lea     rcx, [rsp+948h+var_238]; this
0x1400cfb78  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x1400cfb7d  nop
0x1400cfb7e  lea     rcx, [rsp+948h+var_758]; this
0x1400cfb86  call    ??1SavingTask@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::SavingTask::~SavingTask(void)
0x1400cfb8b  nop
0x1400cfb8c  mov     rcx, [r14]
0x1400cfb8f  mov     rax, [rcx+588h]
0x1400cfb96  mov     eax, [rax+178h]
0x1400cfb9c  mov     dword ptr [rsp+948h+var_600], eax
0x1400cfba3  mov     rcx, [rcx+3E0h]
0x1400cfbaa  mov     rax, [rcx]
0x1400cfbad  mov     rax, [rax+180h]
0x1400cfbb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cfbb9  test    al, al
0x1400cfbbb  jnz     short loc_1400CFBDA
0x1400cfbbd  mov     rcx, [rsp+948h]; this
0x1400cfbc5  lea     r9d, [rsi+32h]; char *
0x1400cfbc9  lea     r8, aOnecoreVmWorke_80; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400cfbd0  mov     edx, 2DEh; void *
0x1400cfbd5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400cfbda  mov     rax, [r14]
0x1400cfbdd  mov     rcx, [rax+430h]
0x1400cfbe4  mov     rax, [rcx]
0x1400cfbe7  lea     r8, [rsp+948h+var_5F8]
0x1400cfbef  lea     rdx, [rsp+948h+var_604]
0x1400cfbf7  mov     rax, [rax+50h]
0x1400cfbfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cfc00  mov     rax, [r14]
0x1400cfc03  mov     rcx, [rax+430h]
0x1400cfc0a  mov     rax, [rcx]
0x1400cfc0d  lea     rdx, [rsp+948h+var_608]
0x1400cfc15  mov     rax, [rax+70h]
0x1400cfc19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cfc1e  cmp     [rsp+948h+var_608], esi
0x1400cfc25  jz      short loc_1400CFC60
0x1400cfc27  mov     rax, [r14]
0x1400cfc2a  mov     rcx, [rax+430h]
0x1400cfc31  mov     rax, [rcx]
0x1400cfc34  mov     rax, [rax+0A8h]
0x1400cfc3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cfc40  mov     rcx, [rsp+948h]; this
0x1400cfc48  test    eax, eax
0x1400cfc4a  jns     short loc_1400CFC60
0x1400cfc4c  mov     r9d, eax; char *
0x1400cfc4f  lea     r8, aOnecoreVmWorke_80; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400cfc56  mov     edx, 2EAh; void *
0x1400cfc5b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cfc60  mov     rbx, [r14]
0x1400cfc63  cmp     [rbx+0B98h], sil
0x1400cfc6a  jz      short loc_1400CFC9F
0x1400cfc6c  mov     rcx, r15; this
0x1400cfc6f  call    ?GetSavedStateRepository@WorkerTaskSaving@@AEAAPEAVVmRepository@@XZ; WorkerTaskSaving::GetSavedStateRepository(void)
0x1400cfc74  mov     rdx, rax; struct VmRepository *
0x1400cfc77  mov     rcx, rbx; this
0x1400cfc7a  call    ?SaveIgvmSaveState@VirtualMachine@@UEAAJPEAVVmRepository@@@Z; VirtualMachine::SaveIgvmSaveState(VmRepository *)
0x1400cfc7f  mov     rcx, [rsp+948h]; this
0x1400cfc87  test    eax, eax
0x1400cfc89  jns     short loc_1400CFC9F
0x1400cfc8b  mov     r9d, eax; char *
0x1400cfc8e  lea     r8, aOnecoreVmWorke_80; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400cfc95  mov     edx, 2EFh; void *
0x1400cfc9a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cfc9f  mov     r12d, 150h
0x1400cfca5  mov     r8d, r12d; Size
0x1400cfca8  xor     edx, edx; Val
0x1400cfcaa  lea     rcx, [rsp+948h+var_488]; void *
0x1400cfcb2  call    memset_0
0x1400cfcb7  mov     rdi, [r14]
0x1400cfcba  lea     rdx, [rsp+948h+var_5D8]
0x1400cfcc2  mov     rcx, r15
0x1400cfcc5  call    ?GetCurrentActivity@?$WorkerAsyncTask@VSavingTask@VmWorkerTrace@@@@IEAA?AVSavingTask@VmWorkerTrace@@XZ; WorkerAsyncTask<VmWorkerTrace::SavingTask>::GetCurrentActivity(void)
0x1400cfcca  nop
0x1400cfccb  mov     rbx, [rax+110h]
0x1400cfcd2  mov     r8d, r12d; Size
0x1400cfcd5  xor     edx, edx; Val
0x1400cfcd7  lea     rcx, [rsp+948h+var_488]; void *
0x1400cfcdf  call    memset_0
0x1400cfce4  lea     rdx, aSaveguestramin; "SaveGuestRamInfo"
0x1400cfceb  lea     rcx, [rsp+948h+var_488]; struct wil::details::IFailureCallback *
0x1400cfcf3  call    ??0?$ActivityBase@VVmWorkerTrace@@$0A@$0BA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400cfcf8  lea     rax, ??_7SaveGuestRamInfo@VmWorkerTrace@@6B@; const VmWorkerTrace::SaveGuestRamInfo::`vftable'
0x1400cfcff  mov     [rsp+948h+var_488], rax
0x1400cfd07  mov     [rsp+948h+var_8F8], 2
0x1400cfd0f  lea     rdx, [rbx+8]
0x1400cfd13  lea     rcx, [rsp+948h+var_488]
0x1400cfd1b  call    ?SetRelatedActivityId@?$ActivityBase@VVmWorkerTrace@@$0A@$0BA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x1400cfd20  lea     rdx, [rdi+470h]; struct _GUID *
0x1400cfd27  lea     rcx, [rsp+948h+var_488]; this
0x1400cfd2f  call    ?StartActivity@SaveGuestRamInfo@VmWorkerTrace@@QEAAXAEBU_GUID@@@Z; VmWorkerTrace::SaveGuestRamInfo::StartActivity(_GUID const &)
0x1400cfd34  nop
0x1400cfd35  mov     r13d, 1
0x1400cfd3b  mov     r12d, r13d
0x1400cfd3e  lea     rcx, [rsp+948h+var_5D8]; this
0x1400cfd46  call    ??1SavingTask@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::SavingTask::~SavingTask(void)
0x1400cfd4b  mov     rdi, cs:qword_1403C0440
0x1400cfd52  mov     rcx, r15
0x1400cfd55  call    ?GetFastSaveType@WorkerTaskSaving@@AEAA?AW4VmFastSaveType@@XZ; WorkerTaskSaving::GetFastSaveType(void)
0x1400cfd5a  mov     ebx, eax
0x1400cfd5c  call    ?GetSavedStateRepository@WorkerTaskSaving@@AEAAPEAVVmRepository@@XZ; WorkerTaskSaving::GetSavedStateRepository(void)
0x1400cfd61  lea     rcx, [r15+1A8h]
0x1400cfd68  mov     [rsp+948h+var_920], rcx
0x1400cfd6d  mov     [rsp+948h+var_928], rdi; int
0x1400cfd72  mov     r9b, r13b
0x1400cfd75  mov     r8d, ebx
0x1400cfd78  mov     rdx, rax
0x1400cfd7b  lea     rcx, ?m_Instance@MemoryManager@@0V1@A; MemoryManager MemoryManager::m_Instance
0x1400cfd82  call    ?SaveRamInformation@MemoryManager@@UEAAXPEAVVmRepository@@W4VmFastSaveType@@_NPEAVGmoBitmap@@PEAT_VM_PERSIST_FLAGS@@@Z; MemoryManager::SaveRamInformation(VmRepository *,VmFastSaveType,bool,GmoBitmap *,_VM_PERSIST_FLAGS *)
0x1400cfd87  xor     edx, edx
0x1400cfd89  lea     rcx, [rsp+948h+var_488]
0x1400cfd91  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0BA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400cfd96  nop
0x1400cfd97  lea     rcx, [rsp+948h+var_488]; this
0x1400cfd9f  call    ??1SaveGuestRamInfo@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::SaveGuestRamInfo::~SaveGuestRamInfo(void)
0x1400cfda4  mov     [rsp+948h+var_8D8], r13d
0x1400cfda9  cmp     [r15+208h], rsi
0x1400cfdb0  jz      loc_1400CFE80
0x1400cfdb6  xor     edx, edx; int
0x1400cfdb8  mov     rcx, r15; this
0x1400cfdbb  call    ?CompletePrepareTask@WorkerTaskSaving@@AEAAXJ@Z; WorkerTaskSaving::CompletePrepareTask(long)
0x1400cfdc0  mov     rcx, [r14]
0x1400cfdc3  add     rcx, 900h; this
0x1400cfdca  mov     edx, 927C0h; unsigned int
0x1400cfdcf  call    ?Wait@VmWaitable@Vml@@QEBAHI@Z; Vml::VmWaitable::Wait(uint)
0x1400cfdd4  test    eax, eax
0x1400cfdd6  jz      short loc_1400CFDF3
0x1400cfdd8  mov     rax, [r14]
0x1400cfddb  mov     ebx, [rax+908h]
0x1400cfde1  test    ebx, ebx
0x1400cfde3  jns     loc_1400CFE80
0x1400cfde9  cmp     ebx, 80004004h
0x1400cfdef  jz      short loc_1400CFDFB
0x1400cfdf1  jmp     short loc_1400CFDF8
0x1400cfdf3  mov     ebx, 80041000h
0x1400cfdf8  mov     r13b, sil
0x1400cfdfb  mov     rcx, [rsp+948h]; this
0x1400cfe03  test    r13b, r13b
0x1400cfe06  jz      short loc_1400CFE1C
0x1400cfe08  mov     r9d, ebx; char *
0x1400cfe0b  lea     r8, aOnecoreVmWorke_80; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400cfe12  mov     edx, 31Fh; void *
0x1400cfe17  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cfe1c  mov     rcx, [r14]
0x1400cfe1f  lea     rax, [rcx+480h]
0x1400cfe26  mov     [rsp+948h+var_600], rax
0x1400cfe2e  add     rcx, 10h; this
0x1400cfe32  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400cfe37  mov     [rsp+948h+var_8E0], rax
0x1400cfe3c  lea     rax, [rsp+948h+var_600]
0x1400cfe44  mov     [rsp+948h+var_920], rax; __int64
0x1400cfe49  lea     rax, [rsp+948h+var_8E0]
0x1400cfe4e  mov     [rsp+948h+var_928], rax; int
0x1400cfe53  mov     edx, 5; unsigned int
0x1400cfe58  lea     rcx, MSVML_TIMEOUT_WAITING_FINALIZE_SAVE; struct _EVENT_DESCRIPTOR *
0x1400cfe5f  call    ??$VmEventWriteAndReport@PEBGPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBG$$QEAPEBG3@Z; VmEventWriteAndReport<ushort const *,ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,ushort const * &&,ushort const * &&)
0x1400cfe64  mov     rcx, [rsp+948h]; this
0x1400cfe6c  mov     r9d, ebx; char *
0x1400cfe6f  lea     r8, aOnecoreVmWorke_80; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400cfe76  mov     edx, 328h; void *
0x1400cfe7b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cfe80  cmp     [rsp+948h+var_8E8], esi
0x1400cfe84  jz      short loc_1400CFEE1
0x1400cfe86  test    dword ptr [r15+194h], 40000h
0x1400cfe91  jz      short loc_1400CFEE1
0x1400cfe93  mov     rax, [r14]
0x1400cfe96  mov     rdi, [rax+400h]
0x1400cfe9d  mov     rax, [rdi+8]
0x1400cfea1  mov     rbx, [rax+50h]
0x1400cfea5  mov     rcx, r15; this
0x1400cfea8  call    ?GetSavedStateRepository@WorkerTaskSaving@@AEAAPEAVVmRepository@@XZ; WorkerTaskSaving::GetSavedStateRepository(void)
0x1400cfead  mov     rdx, rax
0x1400cfeb0  lea     rcx, [rdi+8]
0x1400cfeb4  mov     rax, rbx
0x1400cfeb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cfebc  mov     rcx, [rsp+948h]; this
0x1400cfec4  test    eax, eax
0x1400cfec6  jns     short loc_1400CFEDC
0x1400cfec8  mov     r9d, eax; char *
0x1400cfecb  lea     r8, aOnecoreVmWorke_80; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400cfed2  mov     edx, 337h; void *
0x1400cfed7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cfedc  mov     [rsp+948h+var_8ED], r13b
0x1400cfee1  cmp     [r15+1A0h], esi
0x1400cfee8  jnz     short loc_1400CFEF2
0x1400cfeea  mov     rcx, r15; this
0x1400cfeed  call    ?StopVm@WorkerTaskSaving@@AEAAXXZ; WorkerTaskSaving::StopVm(void)
0x1400cfef2  cmp     dword ptr [rsp+948h+var_8E0], esi
0x1400cfef6  jz      loc_1400D00ED
0x1400cfefc  mov     r12d, 150h
0x1400cff02  mov     r8d, r12d; Size
0x1400cff05  xor     edx, edx; Val
0x1400cff07  lea     rcx, [rsp+948h+var_5D8]; void *
0x1400cff0f  call    memset_0
0x1400cff14  mov     rdi, [r14]
0x1400cff17  lea     rdx, [rsp+948h+var_8A8]
0x1400cff1f  mov     rcx, r15
0x1400cff22  call    ?GetCurrentActivity@?$WorkerAsyncTask@VSavingTask@VmWorkerTrace@@@@IEAA?AVSavingTask@VmWorkerTrace@@XZ; WorkerAsyncTask<VmWorkerTrace::SavingTask>::GetCurrentActivity(void)
0x1400cff27  nop
0x1400cff28  mov     rbx, [rax+110h]
0x1400cff2f  mov     r8d, r12d; Size
0x1400cff32  xor     edx, edx; Val
0x1400cff34  lea     rcx, [rsp+948h+var_5D8]; void *
0x1400cff3c  call    memset_0
0x1400cff41  lea     rdx, aCreateclonetem; "CreateCloneTemplate"
0x1400cff48  lea     rcx, [rsp+948h+var_5D8]; struct wil::details::IFailureCallback *
0x1400cff50  call    ??0?$ActivityBase@VVmWorkerTrace@@$0A@$0BA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400cff55  lea     rax, ??_7CreateCloneTemplate@VmWorkerTrace@@6B@; const VmWorkerTrace::CreateCloneTemplate::`vftable'
0x1400cff5c  mov     [rsp+948h+var_5D8], rax
0x1400cff64  mov     [rsp+948h+var_8F8], 9
0x1400cff6c  lea     rdx, [rbx+8]
0x1400cff70  lea     rcx, [rsp+948h+var_5D8]
0x1400cff78  call    ?SetRelatedActivityId@?$ActivityBase@VVmWorkerTrace@@$0A@$0BA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x1400cff7d  lea     rdx, [rdi+470h]; struct _GUID *
0x1400cff84  lea     rcx, [rsp+948h+var_5D8]; this
0x1400cff8c  call    ?StartActivity@CreateCloneTemplate@VmWorkerTrace@@QEAAXAEBU_GUID@@@Z; VmWorkerTrace::CreateCloneTemplate::StartActivity(_GUID const &)
0x1400cff91  nop
0x1400cff92  lea     rcx, [rsp+948h+var_8A8]; this
0x1400cff9a  call    ??1SavingTask@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::SavingTask::~SavingTask(void)
0x1400cff9f  mov     rax, [r14]
0x1400cffa2  mov     rcx, [rax+400h]
0x1400cffa9  add     rcx, 18h
0x1400cffad  mov     rax, [rcx]
0x1400cffb0  mov     rax, [rax]
0x1400cffb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cffb8  mov     rbx, [rsp+948h]
0x1400cffc0  lea     r8, [rsp+948h+var_5E8]
0x1400cffc8  mov     edx, esi
0x1400cffca  mov     rcx, rax
0x1400cffcd  call    cs:__imp_VidCloneTemplateCreate
0x1400cffd4  nop     dword ptr [rax+rax+00h]
0x1400cffd9  test    eax, eax
0x1400cffdb  jnz     short loc_1400CFFF1
0x1400cffdd  lea     r8, aOnecoreVmWorke_80; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400cffe4  mov     edx, 34Bh; void *
0x1400cffe9  mov     rcx, rbx; this
0x1400cffec  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400cfff1  xor     edx, edx
0x1400cfff3  lea     rcx, [rsp+948h+var_5D8]
0x1400cfffb  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0BA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,16,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400d0000  mov     r8, r12; Size
0x1400d0003  xor     edx, edx; Val
0x1400d0005  lea     rcx, [rsp+948h+var_488]; void *
0x1400d000d  call    memset_0
0x1400d0012  mov     rdi, [r14]
0x1400d0015  lea     rdx, [rsp+948h+var_8A8]
0x1400d001d  mov     rcx, r15
0x1400d0020  call    ?GetCurrentActivity@?$WorkerAsyncTask@VSavingTask@VmWorkerTrace@@@@IEAA?AVSavingTask@VmWorkerTrace@@XZ; WorkerAsyncTask<VmWorkerTrace::SavingTask>::GetCurrentActivity(void)
0x1400d0025  nop
0x1400d0026  mov     rbx, [rax+110h]
0x1400d002d  mov     r8, r12; Size
  ... truncated ...
```
