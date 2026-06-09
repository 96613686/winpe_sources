# WorkerTaskCapturingDebugState::InitializeGmoOperation(void)

- ea: `0x14009abe0`
- end: `0x14009b13a`
- name: `?InitializeGmoOperation@WorkerTaskCapturingDebugState@@AEAAXXZ`
- size: `1370`
- prototype: `void __fastcall(WorkerTaskCapturingDebugState *__hidden this)`
- caller_count: `1`
- callee_count: `38`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140189ccc`

## callees

- `0x14002ed70`
- `0x14006af38`
- `0x14008f838`
- `0x140095d20`
- `0x14009abe0`
- `0x14009b150`
- `0x14009b180`
- `0x14009b21c`
- `0x14009b23c`
- `0x14009b2a8`
- `0x14009b2dc`
- `0x14009b564`
- `0x14009b588`
- `0x14009b680`
- `0x14009b6a4`
- `0x14009b7e4`
- `0x14009ba10`
- `0x14009bbc4`
- `0x14009c4a0`
- `0x14009d050`
- `0x14009d7ac`
- `0x14009dba0`
- `0x1400d12f8`
- `0x1400d1548`
- `0x1400d15a4`
- `0x140132940`
- `0x140132cec`
- `0x1401335fc`
- `0x140166b30`
- `0x1401848b4`
- `0x140184c20`
- `0x14018809c`
- `0x140188660`
- `0x140188e78`
- `0x140197508`
- `0x1401975e8`
- `0x140207c20`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009af92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009af92`
- `vid!VidCloneTemplateCreate` at `0x14009af7e`
- `vid!VidCloneTemplateCreate` at `0x14009af7e`

## string_xrefs

- `0x14009ac36`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`
- `0x14009ae45`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`
- `0x14009af0c`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`
- `0x14009af3c`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`
- `0x14009afcb`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`
- `0x14009b02f`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`
- `0x14009b0a9`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`
- `0x14009b0d8`: `onecore\vm\worker\wpcore\workertaskcapturingdebugstate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall WorkerTaskCapturingDebugState::InitializeGmoOperation(WorkerTaskCapturingDebugState *this)
{
  __int64 v2; // r12
  __int64 CurrentActivity; // rbx
  const struct _GUID **v4; // rdi
  __int64 v5; // rax
  const struct _GUID **v6; // rbx
  __int64 v7; // r9
  VirtualMachine *v8; // rcx
  void *v9; // rdi
  GmoRamOperationSnapshot *v10; // rax
  GmoRamOperationSnapshot *v11; // rcx
  int v12; // eax
  void *v13; // rdi
  GmoRamOperationSave *v14; // rax
  GmoRamOperationSave *v15; // rcx
  int v16; // eax
  GmoRamOperation *GmoRamOperation; // rax
  int v18; // eax
  __int64 (__fastcall ***v19)(_QWORD); // rcx
  __int64 v20; // rax
  signed int LastError; // eax
  int v22; // eax
  unsigned __int64 *v23; // rax
  unsigned __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // r8
  int v27; // eax
  unsigned int v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v31; // [rsp+58h] [rbp-A8h] BYREF
  char v32[336]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v33[336]; // [rsp+1B0h] [rbp+B0h] BYREF
  const struct _GUID **v34; // [rsp+300h] [rbp+200h] BYREF
  __int128 v35; // [rsp+308h] [rbp+208h] BYREF
  __int128 v36; // [rsp+320h] [rbp+220h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+288h]

  v36 = 0;
  v2 = qword_1403C03A0;
  if ( qword_1403C03A0 == 3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2CA,
      (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskcapturingdebugstate.cpp",
      (const char *)0x32,
      v28);
  CurrentActivity = WorkerAsyncTask<VmWorkerTrace::SnapshottingTask>::GetCurrentActivity(this, v33);
  v4 = (const struct _GUID **)operator new(0x160u);
  v34 = v4;
  memset_0(v4, 0, 0x160u);
  v5 = VmWorkerTrace::SnapshottingTask::SnapshottingTask(v32, CurrentActivity);
  v6 = (const struct _GUID **)CaptureStateUtility::CaptureStateUtility(v4, *((_QWORD *)this + 2), v5, 0);
  v34 = v6;
  VmWorkerTrace::SnapshottingTask::~SnapshottingTask((VmWorkerTrace::SnapshottingTask *)v33);
  CaptureStateUtility::SuspendAndSaveEpf(v6, *((struct VmRepository **)this + 63));
  CaptureStateUtility::SuspendAndSaveSchedulerAssist(v6, *((struct VmRepository **)this + 63));
  CaptureStateUtility::InitializeBalloonedPagesBitmap((CaptureStateUtility *)v6);
  v29 = qword_1403C0440;
  LOBYTE(v7) = 1;
  MemoryManager::SaveRamInformation(&MemoryManager::m_Instance, *((_QWORD *)this + 63), 0, v7);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 1024LL) + 256LL))(
    *(_QWORD *)(*((_QWORD *)this + 2) + 1024LL),
    *((_QWORD *)this + 63));
  MemoryManager::SaveVtlProtections((MemoryManager *)&MemoryManager::m_Instance, *((struct VmRepository **)this + 63));
  v30 = 0;
  if ( ((*((_DWORD *)this + 116) - 1) & 0xFFFFFFFD) != 0
    || (v8 = (VirtualMachine *)*((_QWORD *)this + 2), !*((_BYTE *)v8 + 2664)) )
  {
    MemoryManager::GetRamSizeInPages((MemoryManager *)&MemoryManager::m_Instance);
  }
  else
  {
    v31 = 0;
    VirtualMachine::GetVtl2PrivateRamRange(v8, &v31, &v30);
    MemoryManager::GpaIndexToRamIndex((MemoryManager *)&MemoryManager::m_Instance, v31);
  }
  if ( *((_DWORD *)this + 116) == 2 )
  {
    v13 = operator new(0xF8u);
    v30 = (unsigned __int64)v13;
    memset_0(v13, 0, 0xF8u);
    memset_0(v13, 0, 0xF8u);
    v14 = GmoRamOperationSave::GmoRamOperationSave((GmoRamOperationSave *)v13);
    v30 = 0;
    v15 = (GmoRamOperationSave *)*((_QWORD *)this + 54);
    *((_QWORD *)this + 54) = v14;
    if ( v15 )
      GmoRamOperationSave::`scalar deleting destructor'(v15, 1);
    std::unique_ptr<GmoRamOperationSave>::~unique_ptr<GmoRamOperationSave>(&v30);
    v29 = 99;
    v16 = GmoRamOperationSource::Initialize(
            *((_QWORD *)this + 54),
            *((_QWORD *)this + 63),
            *((_QWORD *)this + 2),
            *((_QWORD *)this + 3));
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x318,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskcapturingdebugstate.cpp",
        (const char *)(unsigned int)v16,
        99);
  }
  else
  {
    v9 = operator new(0x110u);
    v30 = (unsigned __int64)v9;
    memset_0(v9, 0, 0x110u);
    v10 = GmoRamOperationSnapshot::GmoRamOperationSnapshot((GmoRamOperationSnapshot *)v9);
    v30 = 0;
    v11 = (GmoRamOperationSnapshot *)*((_QWORD *)this + 53);
    *((_QWORD *)this + 53) = v10;
    if ( v11 )
      GmoRamOperationSnapshot::`vector deleting destructor'(v11, 1);
    std::unique_ptr<GmoRamOperationSnapshot>::~unique_ptr<GmoRamOperationSnapshot>(&v30);
    v12 = GmoRamOperationSnapshot::Initialize(
            *((GmoRamOperationSnapshot **)this + 53),
            *((void **)this + 63),
            *((struct VirtualMachine **)this + 2),
            *((struct IVmSimpleTask **)this + 3));
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30A,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskcapturingdebugstate.cpp",
        (const char *)(unsigned int)v12,
        v29);
  }
  GmoRamOperation = WorkerTaskCapturingDebugState::GetGmoRamOperation(this);
  v18 = GmoRamOperation::WorkThreadsStart(GmoRamOperation);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x31F,
      (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskcapturingdebugstate.cpp",
      (const char *)(unsigned int)v18,
      v29);
  if ( v2 == 2 )
  {
    v19 = (__int64 (__fastcall ***)(_QWORD))(*(_QWORD *)(*((_QWORD *)this + 2) + 1024LL) + 24LL);
    v20 = (**v19)(v19);
    if ( !(unsigned int)VidCloneTemplateCreate(v20, 1, &v36) )
    {
      LastError = GetLastError();
      if ( (LastError & 0x1FFF0000) != 0 )
      {
        if ( LastError > 0 )
          LastError = LastError & 0xFFFFFFF | 0x80000000;
      }
      else if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
      }
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x32B,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskcapturingdebugstate.cpp",
        (const char *)(unsigned int)LastError,
        v29);
    }
  }
  else if ( *((_DWORD *)this + 116) != 2 )
  {
    if ( (unsigned int)MemoryManager::SetRamNotificationListener(
                         (MemoryManager *)&MemoryManager::m_Instance,
                         (struct MemoryNotificationListener *)((*((_QWORD *)this + 53) + 248LL)
                                                             & ((unsigned __int128)-(__int128)*((unsigned __int64 *)this
                                                                                              + 53) >> 64))) )
    {
      v22 = GmoRamOperationSnapshot::SetMemoryIntercepts(*((GmoRamOperationSnapshot **)this + 53));
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x344,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskcapturingdebugstate.cpp",
          (const char *)(unsigned int)v22,
          v29);
    }
    else
    {
      v35 = 0;
      v23 = std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(&v31);
      v24 = *v23;
      *v23 = 0;
      v30 = v24;
      VirtualizationSettings::VirtualizationSettings(&v35, v25, v26, &v30);
      std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>(&v30);
      std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>(&v31);
      if ( !VirtualizationSettings::GetAzureFeatureSetEnabled((VirtualizationSettings *)&v35) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x34D,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskcapturingdebugstate.cpp",
          (const char *)0x80070032LL,
          v29);
      v27 = GmoRamOperationSnapshot::SaveAllMemory(*((GmoRamOperationSnapshot **)this + 53));
      if ( v27 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x34E,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskcapturingdebugstate.cpp",
          (const char *)(unsigned int)v27,
          v29);
      std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>((char *)&v35 + 8);
    }
  }
  std::unique_ptr<CaptureStateUtility>::operator=<std::default_delete<CaptureStateUtility>,0>(
    (__int64 *)this + 55,
    (__int64 *)&v34);
  std::unique_ptr<CaptureStateUtility>::~unique_ptr<CaptureStateUtility>(&v34);
}

```

## disassembly

```asm
0x14009abe0  push    rbp
0x14009abe2  push    rbx
0x14009abe3  push    rsi
0x14009abe4  push    rdi
0x14009abe5  push    r12
0x14009abe7  push    r13
0x14009abe9  push    r14
0x14009abeb  push    r15
0x14009abed  lea     rbp, [rsp-248h]
0x14009abf5  sub     rsp, 348h
0x14009abfc  mov     rax, cs:__security_cookie
0x14009ac03  xor     rax, rsp
0x14009ac06  mov     [rbp+280h+var_50], rax
0x14009ac0d  mov     rsi, rcx
0x14009ac10  xor     r15d, r15d
0x14009ac13  xorps   xmm0, xmm0
0x14009ac16  movdqa  [rbp+280h+var_60], xmm0
0x14009ac1e  mov     r12, cs:qword_1403C03A0
0x14009ac25  cmp     r12, 3
0x14009ac29  jnz     short loc_14009AC48
0x14009ac2b  mov     rcx, [rbp+288h]; this
0x14009ac32  lea     r9d, [r15+32h]; char *
0x14009ac36  lea     r8, aOnecoreVmWorke_124; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009ac3d  mov     edx, 2CAh; void *
0x14009ac42  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14009ac48  lea     rdx, [rbp+280h+var_1D0]
0x14009ac4f  call    ?GetCurrentActivity@?$WorkerAsyncTask@VSnapshottingTask@VmWorkerTrace@@@@IEAA?AVSnapshottingTask@VmWorkerTrace@@XZ; WorkerAsyncTask<VmWorkerTrace::SnapshottingTask>::GetCurrentActivity(void)
0x14009ac54  mov     rbx, rax
0x14009ac57  mov     r14d, 160h
0x14009ac5d  mov     ecx, r14d; Size
0x14009ac60  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14009ac65  mov     rdi, rax
0x14009ac68  mov     [rbp+280h+var_80], rax
0x14009ac6f  mov     r8d, r14d; Size
0x14009ac72  xor     edx, edx; Val
0x14009ac74  mov     rcx, rax; void *
0x14009ac77  call    memset_0
0x14009ac7c  mov     rdx, rbx
0x14009ac7f  lea     rcx, [rsp+380h+var_320]
0x14009ac84  call    ??0SnapshottingTask@VmWorkerTrace@@QEAA@$$QEAV01@@Z; VmWorkerTrace::SnapshottingTask::SnapshottingTask(VmWorkerTrace::SnapshottingTask &&)
0x14009ac89  xor     r9d, r9d
0x14009ac8c  mov     r8, rax
0x14009ac8f  mov     rdx, [rsi+10h]
0x14009ac93  mov     rcx, rdi
0x14009ac96  call    ??0CaptureStateUtility@@QEAA@PEAVVirtualMachine@@VSnapshottingTask@VmWorkerTrace@@_N@Z; CaptureStateUtility::CaptureStateUtility(VirtualMachine *,VmWorkerTrace::SnapshottingTask,bool)
0x14009ac9b  mov     rbx, rax
0x14009ac9e  mov     [rbp+280h+var_80], rax
0x14009aca5  lea     rcx, [rbp+280h+var_1D0]; this
0x14009acac  call    ??1SnapshottingTask@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::SnapshottingTask::~SnapshottingTask(void)
0x14009acb1  mov     rdx, [rsi+1F8h]; struct VmRepository *
0x14009acb8  mov     rcx, rbx; this
0x14009acbb  call    ?SuspendAndSaveEpf@CaptureStateUtility@@QEAAXPEAVVmRepository@@@Z; CaptureStateUtility::SuspendAndSaveEpf(VmRepository *)
0x14009acc0  mov     rdx, [rsi+1F8h]; struct VmRepository *
0x14009acc7  mov     rcx, rbx; this
0x14009acca  call    ?SuspendAndSaveSchedulerAssist@CaptureStateUtility@@QEAAXPEAVVmRepository@@@Z; CaptureStateUtility::SuspendAndSaveSchedulerAssist(VmRepository *)
0x14009accf  mov     rax, [rsi+10h]
0x14009acd3  mov     rcx, [rax+588h]
0x14009acda  mov     r13d, [rcx+178h]
0x14009ace1  mov     rcx, rbx; this
0x14009ace4  call    ?InitializeBalloonedPagesBitmap@CaptureStateUtility@@QEAAXXZ; CaptureStateUtility::InitializeBalloonedPagesBitmap(void)
0x14009ace9  mov     [rsp+380h+var_358], r15; unsigned __int64
0x14009acee  mov     rax, cs:qword_1403C0440
0x14009acf5  mov     [rsp+380h+var_360], rax; int
0x14009acfa  mov     ebx, 1
0x14009acff  mov     r9b, bl
0x14009ad02  xor     r8d, r8d
0x14009ad05  mov     rdx, [rsi+1F8h]
0x14009ad0c  lea     rdi, ?m_Instance@MemoryManager@@0V1@A; MemoryManager MemoryManager::m_Instance
0x14009ad13  mov     rcx, rdi
0x14009ad16  call    ?SaveRamInformation@MemoryManager@@UEAAXPEAVVmRepository@@W4VmFastSaveType@@_NPEAVGmoBitmap@@PEAT_VM_PERSIST_FLAGS@@@Z; MemoryManager::SaveRamInformation(VmRepository *,VmFastSaveType,bool,GmoBitmap *,_VM_PERSIST_FLAGS *)
0x14009ad1b  mov     rax, [rsi+10h]
0x14009ad1f  mov     rcx, [rax+400h]
0x14009ad26  mov     rax, [rcx]
0x14009ad29  mov     rdx, [rsi+1F8h]
0x14009ad30  mov     rax, [rax+100h]
0x14009ad37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009ad3c  mov     rdx, [rsi+1F8h]; struct VmRepository *
0x14009ad43  mov     rcx, rdi; this
0x14009ad46  call    ?SaveVtlProtections@MemoryManager@@UEAAXPEAVVmRepository@@@Z; MemoryManager::SaveVtlProtections(VmRepository *)
0x14009ad4b  mov     [rsp+380h+var_330], r15
0x14009ad50  mov     eax, [rsi+1D0h]
0x14009ad56  sub     eax, ebx
0x14009ad58  test    eax, 0FFFFFFFDh
0x14009ad5d  jnz     short loc_14009AD97
0x14009ad5f  mov     rcx, [rsi+10h]; this
0x14009ad63  cmp     [rcx+0A68h], r15b
0x14009ad6a  jz      short loc_14009AD97
0x14009ad6c  mov     [rsp+380h+var_328], r15
0x14009ad71  lea     r8, [rsp+380h+var_330]; unsigned __int64 *
0x14009ad76  lea     rdx, [rsp+380h+var_328]; unsigned __int64 *
0x14009ad7b  call    ?GetVtl2PrivateRamRange@VirtualMachine@@UEBAXPEA_K0@Z; VirtualMachine::GetVtl2PrivateRamRange(unsigned __int64 *,unsigned __int64 *)
0x14009ad80  mov     rdx, [rsp+380h+var_328]; unsigned __int64
0x14009ad85  mov     rcx, rdi; this
0x14009ad88  call    ?GpaIndexToRamIndex@MemoryManager@@UEAA_K_K@Z; MemoryManager::GpaIndexToRamIndex(unsigned __int64)
0x14009ad8d  mov     r14, rax
0x14009ad90  mov     r15, [rsp+380h+var_330]
0x14009ad95  jmp     short loc_14009ADA5
0x14009ad97  mov     r14, r15
0x14009ad9a  mov     rcx, rdi; this
0x14009ad9d  call    ?GetRamSizeInPages@MemoryManager@@UEBA_KXZ; MemoryManager::GetRamSizeInPages(void)
0x14009ada2  mov     r15, rax
0x14009ada5  cmp     dword ptr [rsi+1D0h], 2
0x14009adac  jz      loc_14009AE57
0x14009adb2  mov     ecx, 110h; Size
0x14009adb7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14009adbc  mov     rdi, rax
0x14009adbf  mov     [rsp+380h+var_330], rax
0x14009adc4  xor     edx, edx; Val
0x14009adc6  mov     r8d, 110h; Size
0x14009adcc  mov     rcx, rax; void *
0x14009adcf  call    memset_0
0x14009add4  mov     rcx, rdi; this
0x14009add7  call    ??0GmoRamOperationSnapshot@@QEAA@XZ; GmoRamOperationSnapshot::GmoRamOperationSnapshot(void)
0x14009addc  mov     [rsp+380h+var_330], 0
0x14009ade5  mov     rcx, [rsi+1A8h]; this
0x14009adec  mov     [rsi+1A8h], rax
0x14009adf3  test    rcx, rcx
0x14009adf6  jz      short loc_14009ADFF
0x14009adf8  mov     edx, ebx; unsigned int
0x14009adfa  call    ??_EGmoRamOperationSnapshot@@UEAAPEAXI@Z; GmoRamOperationSnapshot::`vector deleting destructor'(uint)
0x14009adff  lea     rcx, [rsp+380h+var_330]
0x14009ae04  call    ??1?$unique_ptr@VGmoRamOperationSnapshot@@U?$default_delete@VGmoRamOperationSnapshot@@@std@@@std@@QEAA@XZ; std::unique_ptr<GmoRamOperationSnapshot>::~unique_ptr<GmoRamOperationSnapshot>(void)
0x14009ae09  mov     [rsp+380h+var_340], r13d; unsigned int
0x14009ae0e  mov     [rsp+380h+var_348], r14; unsigned __int64
0x14009ae13  mov     [rsp+380h+var_350], r15; unsigned __int64
0x14009ae18  mov     r9, [rsi+18h]; struct IVmSimpleTask *
0x14009ae1c  mov     r8, [rsi+10h]; struct VirtualMachine *
0x14009ae20  mov     rdx, [rsi+1F8h]; void *
0x14009ae27  mov     rcx, [rsi+1A8h]; this
0x14009ae2e  call    ?Initialize@GmoRamOperationSnapshot@@QEAAJPEAXPEAVVirtualMachine@@PEAUIVmSimpleTask@@_K333I@Z; GmoRamOperationSnapshot::Initialize(void *,VirtualMachine *,IVmSimpleTask *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,uint)
0x14009ae33  mov     rcx, [rbp+288h]; this
0x14009ae3a  test    eax, eax
0x14009ae3c  jns     loc_14009AF1E
0x14009ae42  mov     r9d, eax; char *
0x14009ae45  lea     r8, aOnecoreVmWorke_124; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009ae4c  mov     edx, 30Ah; void *
0x14009ae51  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009ae57  mov     ecx, 0F8h; Size
0x14009ae5c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14009ae61  mov     rdi, rax
0x14009ae64  mov     [rsp+380h+var_330], rax
0x14009ae69  xor     edx, edx; Val
0x14009ae6b  mov     r8d, 0F8h; Size
0x14009ae71  mov     rcx, rax; void *
0x14009ae74  call    memset_0
0x14009ae79  xor     edx, edx; Val
0x14009ae7b  mov     r8d, 0F8h; Size
0x14009ae81  mov     rcx, rdi; void *
0x14009ae84  call    memset_0
0x14009ae89  mov     rcx, rdi; this
0x14009ae8c  call    ??0GmoRamOperationSave@@QEAA@XZ; GmoRamOperationSave::GmoRamOperationSave(void)
0x14009ae91  mov     [rsp+380h+var_330], 0
0x14009ae9a  mov     rcx, [rsi+1B0h]; this
0x14009aea1  mov     [rsi+1B0h], rax
0x14009aea8  test    rcx, rcx
0x14009aeab  jz      short loc_14009AEB4
0x14009aead  mov     edx, ebx; unsigned int
0x14009aeaf  call    ??_GGmoRamOperationSave@@UEAAPEAXI@Z; GmoRamOperationSave::`scalar deleting destructor'(uint)
0x14009aeb4  lea     rcx, [rsp+380h+var_330]
0x14009aeb9  call    ??1?$unique_ptr@VGmoRamOperationSave@@U?$default_delete@VGmoRamOperationSave@@@std@@@std@@QEAA@XZ; std::unique_ptr<GmoRamOperationSave>::~unique_ptr<GmoRamOperationSave>(void)
0x14009aebe  mov     [rsp+380h+var_338], ebx
0x14009aec2  mov     [rsp+380h+var_340], r13d
0x14009aec7  mov     [rsp+380h+var_348], r14
0x14009aecc  mov     [rsp+380h+var_350], r15
0x14009aed1  mov     [rsp+380h+var_358], 5
0x14009aeda  mov     [rsp+380h+var_360], 63h ; 'c'; int
0x14009aee3  mov     r9, [rsi+18h]
0x14009aee7  mov     r8, [rsi+10h]
0x14009aeeb  mov     rdx, [rsi+1F8h]
0x14009aef2  mov     rcx, [rsi+1B0h]
0x14009aef9  call    ?Initialize@GmoRamOperationSource@@QEAAJPEAXPEAVVirtualMachine@@PEAUIVmSimpleTask@@_K333IW4Flags@1@@Z; GmoRamOperationSource::Initialize(void *,VirtualMachine *,IVmSimpleTask *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,uint,GmoRamOperationSource::Flags)
0x14009aefe  mov     rcx, [rbp+288h]; this
0x14009af05  test    eax, eax
0x14009af07  jns     short loc_14009AF1E
0x14009af09  mov     r9d, eax; char *
0x14009af0c  lea     r8, aOnecoreVmWorke_124; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009af13  mov     edx, 318h; void *
0x14009af18  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009af1e  mov     rcx, rsi; this
0x14009af21  call    ?GetGmoRamOperation@WorkerTaskCapturingDebugState@@AEAAPEAVGmoRamOperationSource@@XZ; WorkerTaskCapturingDebugState::GetGmoRamOperation(void)
0x14009af26  mov     rcx, rax; this
0x14009af29  call    ?WorkThreadsStart@GmoRamOperation@@QEAAJXZ; GmoRamOperation::WorkThreadsStart(void)
0x14009af2e  mov     rcx, [rbp+288h]; this
0x14009af35  test    eax, eax
0x14009af37  jns     short loc_14009AF4E
0x14009af39  mov     r9d, eax; char *
0x14009af3c  lea     r8, aOnecoreVmWorke_124; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009af43  mov     edx, 31Fh; void *
0x14009af48  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009af4e  cmp     r12, 2
0x14009af52  jnz     loc_14009AFDD
0x14009af58  mov     rax, [rsi+10h]
0x14009af5c  mov     rcx, [rax+400h]
0x14009af63  add     rcx, 18h
0x14009af67  mov     rax, [rcx]
0x14009af6a  mov     rax, [rax]
0x14009af6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009af72  lea     r8, [rbp+280h+var_60]
0x14009af79  mov     edx, ebx
0x14009af7b  mov     rcx, rax
0x14009af7e  call    cs:__imp_VidCloneTemplateCreate
0x14009af85  nop     dword ptr [rax+rax+00h]
0x14009af8a  test    eax, eax
0x14009af8c  jnz     loc_14009B0F6
0x14009af92  call    cs:__imp_GetLastError
0x14009af99  nop     dword ptr [rax+rax+00h]
0x14009af9e  test    eax, 1FFF0000h
0x14009afa3  jnz     short loc_14009AFB3
0x14009afa5  test    eax, eax
0x14009afa7  jle     short loc_14009AFC1
0x14009afa9  movzx   eax, ax
0x14009afac  or      eax, 80070000h
0x14009afb1  jmp     short loc_14009AFC1
0x14009afb3  test    eax, eax
0x14009afb5  jle     short loc_14009AFC1
0x14009afb7  and     eax, 0FFFFFFFh
0x14009afbc  or      eax, 80000000h
0x14009afc1  mov     rcx, [rbp+288h]; this
0x14009afc8  mov     r9d, eax; char *
0x14009afcb  lea     r8, aOnecoreVmWorke_124; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009afd2  mov     edx, 32Bh; void *
0x14009afd7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009afdd  cmp     dword ptr [rsi+1D0h], 2
0x14009afe4  jz      loc_14009B0F6
0x14009afea  mov     rax, [rsi+1A8h]
0x14009aff1  lea     r8, [rax+0F8h]
0x14009aff8  neg     rax
0x14009affb  sbb     rdx, rdx
0x14009affe  and     rdx, r8; struct MemoryNotificationListener *
0x14009b001  lea     rcx, ?m_Instance@MemoryManager@@0V1@A; this
0x14009b008  call    ?SetRamNotificationListener@MemoryManager@@UEAAHPEAVMemoryNotificationListener@@@Z; MemoryManager::SetRamNotificationListener(MemoryNotificationListener *)
0x14009b00d  test    eax, eax
0x14009b00f  jz      short loc_14009B041
0x14009b011  mov     rcx, [rsi+1A8h]; this
0x14009b018  call    ?SetMemoryIntercepts@GmoRamOperationSnapshot@@QEAAJXZ; GmoRamOperationSnapshot::SetMemoryIntercepts(void)
0x14009b01d  mov     rcx, [rbp+288h]; this
0x14009b024  test    eax, eax
0x14009b026  jns     loc_14009B0F6
0x14009b02c  mov     r9d, eax; char *
0x14009b02f  lea     r8, aOnecoreVmWorke_124; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009b036  mov     edx, 344h; void *
0x14009b03b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009b041  xorps   xmm0, xmm0
0x14009b044  movups  [rbp+280h+var_78], xmm0
0x14009b04b  lea     rcx, [rsp+380h+var_328]
0x14009b050  call    ??$make_unique@VVmMachineLocalSettingsStore@Vml@@$$V$0A@@std@@YA?AV?$unique_ptr@VVmMachineLocalSettingsStore@Vml@@U?$default_delete@VVmMachineLocalSettingsStore@Vml@@@std@@@0@XZ; std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(void)
0x14009b055  nop
0x14009b056  mov     rcx, [rax]
0x14009b059  mov     qword ptr [rax], 0
0x14009b060  mov     [rsp+380h+var_330], rcx
0x14009b065  lea     r9, [rsp+380h+var_330]
0x14009b06a  lea     rcx, [rbp+280h+var_78]
0x14009b071  call    ??0VirtualizationSettings@@QEAA@_NPEBG$$QEAV?$unique_ptr@VISettingsStore@@U?$default_delete@VISettingsStore@@@std@@@std@@@Z; VirtualizationSettings::VirtualizationSettings(bool,ushort const *,std::unique_ptr<ISettingsStore> &&)
0x14009b076  nop
0x14009b077  lea     rcx, [rsp+380h+var_330]
0x14009b07c  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x14009b081  nop
0x14009b082  lea     rcx, [rsp+380h+var_328]
0x14009b087  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x14009b08c  mov     rbx, [rbp+288h]
0x14009b093  lea     rcx, [rbp+280h+var_78]; this
0x14009b09a  call    ?GetAzureFeatureSetEnabled@VirtualizationSettings@@UEBA_NXZ; VirtualizationSettings::GetAzureFeatureSetEnabled(void)
0x14009b09f  test    al, al
0x14009b0a1  jnz     short loc_14009B0BE
0x14009b0a3  mov     r9d, 80070032h; char *
0x14009b0a9  lea     r8, aOnecoreVmWorke_124; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009b0b0  mov     edx, 34Dh; void *
0x14009b0b5  mov     rcx, rbx; this
0x14009b0b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009b0be  mov     rcx, [rsi+1A8h]; this
0x14009b0c5  call    ?SaveAllMemory@GmoRamOperationSnapshot@@QEAAJXZ; GmoRamOperationSnapshot::SaveAllMemory(void)
0x14009b0ca  mov     rcx, [rbp+288h]; this
0x14009b0d1  test    eax, eax
0x14009b0d3  jns     short loc_14009B0EA
0x14009b0d5  mov     r9d, eax; char *
0x14009b0d8  lea     r8, aOnecoreVmWorke_124; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009b0df  mov     edx, 34Eh; void *
0x14009b0e4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009b0ea  lea     rcx, [rbp+280h+var_78+8]
0x14009b0f1  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x14009b0f6  lea     rcx, [rsi+1B8h]
0x14009b0fd  lea     rdx, [rbp+280h+var_80]
0x14009b104  call    ??$?4U?$default_delete@VCaptureStateUtility@@@std@@$0A@@?$unique_ptr@VCaptureStateUtility@@U?$default_delete@VCaptureStateUtility@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<CaptureStateUtility>::operator=<std::default_delete<CaptureStateUtility>,0>(std::unique_ptr<CaptureStateUtility> &&)
0x14009b109  nop
0x14009b10a  lea     rcx, [rbp+280h+var_80]
0x14009b111  call    ??1?$unique_ptr@VCaptureStateUtility@@U?$default_delete@VCaptureStateUtility@@@std@@@std@@QEAA@XZ; std::unique_ptr<CaptureStateUtility>::~unique_ptr<CaptureStateUtility>(void)
0x14009b116  mov     rcx, [rbp+280h+var_50]
0x14009b11d  xor     rcx, rsp; StackCookie
0x14009b120  call    __security_check_cookie
0x14009b125  add     rsp, 348h
0x14009b12c  pop     r15
0x14009b12e  pop     r14
0x14009b130  pop     r13
0x14009b132  pop     r12
0x14009b134  pop     rdi
0x14009b135  pop     rsi
0x14009b136  pop     rbx
0x14009b137  pop     rbp
0x14009b138  retn
```
