# WorkerTaskSnapshotting::InitializeGmoOperation(void)

- ea: `0x14009c004`
- end: `0x14009c48e`
- name: `?InitializeGmoOperation@WorkerTaskSnapshotting@@AEAAXXZ`
- size: `1162`
- prototype: `void __fastcall(WorkerTaskSnapshotting *__hidden this)`
- caller_count: `1`
- callee_count: `25`
- tags: `service_task, installer_update`

## callers

- `0x14018c5fc`

## callees

- `0x14002ed70`
- `0x14006af38`
- `0x14009b21c`
- `0x14009b2a8`
- `0x14009b588`
- `0x14009b6a4`
- `0x14009b7e4`
- `0x14009c004`
- `0x14009c4a0`
- `0x14009d050`
- `0x14009d7ac`
- `0x14009d800`
- `0x14009dba0`
- `0x14009f9ec`
- `0x1400d12f8`
- `0x1400d1548`
- `0x1400d15a4`
- `0x140132940`
- `0x140132cec`
- `0x1401335fc`
- `0x14018809c`
- `0x140188e78`
- `0x140197508`
- `0x1401975e8`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009c39a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009c39a`
- `vid!VidCloneTemplateCreate` at `0x14009c386`
- `vid!VidCloneTemplateCreate` at `0x14009c386`

## string_xrefs

- `0x14009c061`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`
- `0x14009c089`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`
- `0x14009c1e2`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`
- `0x14009c293`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`
- `0x14009c342`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`
- `0x14009c3d3`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`
- `0x14009c40d`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`
- `0x14009c438`: `onecore\vm\worker\wpcore\workertasksnapshotting.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall WorkerTaskSnapshotting::InitializeGmoOperation(WorkerTaskSnapshotting *this)
{
  __int64 v2; // r15
  bool v3; // si
  __int64 CurrentActivity; // rbx
  void *v5; // rdi
  __int64 v6; // rax
  __int64 v7; // r9
  __int64 v8; // rbx
  __int64 v9; // r9
  int v10; // eax
  VirtualMachine *v11; // rcx
  int v12; // eax
  int v13; // eax
  const char *v14; // r9
  int v15; // eax
  int v16; // eax
  __int64 (__fastcall ***v17)(_QWORD); // rcx
  __int64 v18; // rax
  signed int LastError; // eax
  struct MemoryNotificationListener *v20; // rdx
  int v21; // eax
  unsigned int v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+20h] [rbp-E0h]
  char v24[336]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[336]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v26; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int64 v27; // [rsp+2F8h] [rbp+1F8h] BYREF
  __int128 v28; // [rsp+300h] [rbp+200h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  v26 = 0;
  v28 = 0;
  v2 = qword_1403C03A0;
  if ( qword_1403C03A0 == 3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x38F,
      (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksnapshotting.cpp",
      (const char *)0x32,
      v22);
  if ( BYTE6(qword_1403C05AC) )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x397,
      (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksnapshotting.cpp",
      (const char *)0x32,
      v22);
  (*(void (__fastcall **)(_QWORD, int *))(**(_QWORD **)(*((_QWORD *)this + 2) + 1072LL) + 112LL))(
    *(_QWORD *)(*((_QWORD *)this + 2) + 1072LL),
    &v26);
  v3 = v26 != 0;
  CurrentActivity = WorkerAsyncTask<VmWorkerTrace::SnapshottingTask>::GetCurrentActivity(this, v25);
  v5 = operator new(0x160u);
  v27 = (__int64)v5;
  memset_0(v5, 0, 0x160u);
  v6 = VmWorkerTrace::SnapshottingTask::SnapshottingTask(v24, CurrentActivity);
  LOBYTE(v7) = v3;
  v8 = CaptureStateUtility::CaptureStateUtility(v5, *((_QWORD *)this + 2), v6, v7);
  v27 = v8;
  VmWorkerTrace::SnapshottingTask::~SnapshottingTask((VmWorkerTrace::SnapshottingTask *)v25);
  CaptureStateUtility::SuspendAndSaveEpf((const struct _GUID **)v8, *((struct VmRepository **)this + 133));
  CaptureStateUtility::SuspendAndSaveSchedulerAssist((const struct _GUID **)v8, *((struct VmRepository **)this + 133));
  if ( v26 )
  {
    if ( *(_BYTE *)(v8 + 344) )
    {
      v10 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)v8 + 1072LL) + 168LL))(*(_QWORD *)(*(_QWORD *)v8 + 1072LL));
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB3,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\capturestateutility.cpp",
          (const char *)(unsigned int)v10,
          v22);
      *(_BYTE *)(v8 + 347) = 1;
    }
  }
  else
  {
    CaptureStateUtility::InitializeBalloonedPagesBitmap((CaptureStateUtility *)v8);
  }
  v11 = (VirtualMachine *)*((_QWORD *)this + 2);
  if ( *((_BYTE *)v11 + 2968) )
  {
    v12 = VirtualMachine::SaveIgvmSaveState(v11, *((struct VmRepository **)this + 133));
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3B9,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksnapshotting.cpp",
        (const char *)(unsigned int)v12,
        v22);
  }
  v23 = qword_1403C0440;
  LOBYTE(v9) = 1;
  MemoryManager::SaveRamInformation(&MemoryManager::m_Instance, *((_QWORD *)this + 133), 0, v9);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 1024LL) + 256LL))(
    *(_QWORD *)(*((_QWORD *)this + 2) + 1024LL),
    *((_QWORD *)this + 133));
  MemoryManager::SaveVtlProtections((MemoryManager *)&MemoryManager::m_Instance, *((struct VmRepository **)this + 133));
  MemoryManager::GetRamSizeInPages((MemoryManager *)&MemoryManager::m_Instance);
  v13 = GmoRamOperationSnapshot::Initialize(
          (WorkerTaskSnapshotting *)((char *)this + 672),
          *((void **)this + 133),
          *((struct VirtualMachine **)this + 2),
          *((struct IVmSimpleTask **)this + 3));
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3D8,
      (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksnapshotting.cpp",
      (const char *)(unsigned int)v13,
      v23);
  if ( v26 && *(_BYTE *)(v8 + 344) )
  {
    if ( !*(_BYTE *)(v8 + 347) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC0,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\capturestateutility.cpp",
        v14);
    v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**(_QWORD **)(*(_QWORD *)v8 + 1072LL) + 184LL))(
            *(_QWORD *)(*(_QWORD *)v8 + 1072LL),
            *((unsigned int *)this + 218),
            256,
            2);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC4,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\capturestateutility.cpp",
        (const char *)(unsigned int)v15,
        v23);
    *(_BYTE *)(v8 + 348) = 1;
  }
  v16 = GmoRamOperation::WorkThreadsStart((WorkerTaskSnapshotting *)((char *)this + 672));
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3E2,
      (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksnapshotting.cpp",
      (const char *)(unsigned int)v16,
      v23);
  if ( v2 == 2 )
  {
    v17 = (__int64 (__fastcall ***)(_QWORD))(*(_QWORD *)(*((_QWORD *)this + 2) + 1024LL) + 24LL);
    v18 = (**v17)(v17);
    if ( !(unsigned int)VidCloneTemplateCreate(v18, 1, &v28) )
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
        (void *)0x3EE,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksnapshotting.cpp",
        (const char *)(unsigned int)LastError,
        v23);
    }
  }
  else
  {
    v20 = (WorkerTaskSnapshotting *)((char *)this + 920);
    if ( this == (WorkerTaskSnapshotting *)-672LL )
      v20 = 0;
    if ( !(unsigned int)MemoryManager::SetRamNotificationListener((MemoryManager *)&MemoryManager::m_Instance, v20) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3FA,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksnapshotting.cpp",
        (const char *)0x80004005LL,
        v23);
    v21 = GmoRamOperationSnapshot::SetMemoryIntercepts((WorkerTaskSnapshotting *)((char *)this + 672));
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3FF,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertasksnapshotting.cpp",
        (const char *)(unsigned int)v21,
        v23);
  }
  std::unique_ptr<CaptureStateUtility>::operator=<std::default_delete<CaptureStateUtility>,0>(
    (__int64 *)this + 118,
    &v27);
  std::unique_ptr<CaptureStateUtility>::~unique_ptr<CaptureStateUtility>(&v27);
}

```

## disassembly

```asm
0x14009c004  push    rbp
0x14009c006  push    rbx
0x14009c007  push    rsi
0x14009c008  push    rdi
0x14009c009  push    r12
0x14009c00b  push    r13
0x14009c00d  push    r14
0x14009c00f  push    r15
0x14009c011  lea     rbp, [rsp-228h]
0x14009c019  sub     rsp, 328h
0x14009c020  mov     rax, cs:__security_cookie
0x14009c027  xor     rax, rsp
0x14009c02a  mov     [rbp+260h+var_50], rax
0x14009c031  mov     r14, rcx
0x14009c034  xor     r13d, r13d
0x14009c037  mov     [rbp+260h+var_70], r13d
0x14009c03e  xorps   xmm0, xmm0
0x14009c041  movdqa  [rbp+260h+var_60], xmm0
0x14009c049  mov     r15, cs:qword_1403C03A0
0x14009c050  cmp     r15, 3
0x14009c054  jnz     short loc_14009C073
0x14009c056  mov     rcx, [rbp+268h]; this
0x14009c05d  lea     r9d, [r13+32h]; char *
0x14009c061  lea     r8, aOnecoreVmWorke_140; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009c068  mov     edx, 38Fh; void *
0x14009c06d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14009c073  cmp     byte ptr cs:qword_1403C05AC+6, r13b
0x14009c07a  jz      short loc_14009C09B
0x14009c07c  mov     rcx, [rbp+268h]; this
0x14009c083  mov     r9d, 32h ; '2'; char *
0x14009c089  lea     r8, aOnecoreVmWorke_140; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009c090  mov     edx, 397h; void *
0x14009c095  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14009c09b  mov     rax, [rcx+10h]
0x14009c09f  mov     rcx, [rax+430h]
0x14009c0a6  mov     rax, [rcx]
0x14009c0a9  lea     rdx, [rbp+260h+var_70]
0x14009c0b0  mov     rax, [rax+70h]
0x14009c0b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009c0b9  cmp     [rbp+260h+var_70], r13d
0x14009c0c0  setnz   sil
0x14009c0c4  lea     rdx, [rbp+260h+var_1C0]
0x14009c0cb  mov     rcx, r14
0x14009c0ce  call    ?GetCurrentActivity@?$WorkerAsyncTask@VSnapshottingTask@VmWorkerTrace@@@@IEAA?AVSnapshottingTask@VmWorkerTrace@@XZ; WorkerAsyncTask<VmWorkerTrace::SnapshottingTask>::GetCurrentActivity(void)
0x14009c0d3  mov     rbx, rax
0x14009c0d6  mov     r12d, 160h
0x14009c0dc  mov     ecx, r12d; Size
0x14009c0df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14009c0e4  mov     rdi, rax
0x14009c0e7  mov     [rbp+260h+var_68], rax
0x14009c0ee  mov     r8d, r12d; Size
0x14009c0f1  xor     edx, edx; Val
0x14009c0f3  mov     rcx, rax; void *
0x14009c0f6  call    memset_0
0x14009c0fb  mov     rdx, rbx
0x14009c0fe  lea     rcx, [rsp+360h+var_310]
0x14009c103  call    ??0SnapshottingTask@VmWorkerTrace@@QEAA@$$QEAV01@@Z; VmWorkerTrace::SnapshottingTask::SnapshottingTask(VmWorkerTrace::SnapshottingTask &&)
0x14009c108  mov     r9b, sil
0x14009c10b  mov     r8, rax
0x14009c10e  mov     rdx, [r14+10h]
0x14009c112  mov     rcx, rdi
0x14009c115  call    ??0CaptureStateUtility@@QEAA@PEAVVirtualMachine@@VSnapshottingTask@VmWorkerTrace@@_N@Z; CaptureStateUtility::CaptureStateUtility(VirtualMachine *,VmWorkerTrace::SnapshottingTask,bool)
0x14009c11a  mov     rbx, rax
0x14009c11d  mov     [rbp+260h+var_68], rax
0x14009c124  lea     rcx, [rbp+260h+var_1C0]; this
0x14009c12b  call    ??1SnapshottingTask@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::SnapshottingTask::~SnapshottingTask(void)
0x14009c130  mov     rdx, [r14+428h]; struct VmRepository *
0x14009c137  mov     rcx, rbx; this
0x14009c13a  call    ?SuspendAndSaveEpf@CaptureStateUtility@@QEAAXPEAVVmRepository@@@Z; CaptureStateUtility::SuspendAndSaveEpf(VmRepository *)
0x14009c13f  mov     rdx, [r14+428h]; struct VmRepository *
0x14009c146  mov     rcx, rbx; this
0x14009c149  call    ?SuspendAndSaveSchedulerAssist@CaptureStateUtility@@QEAAXPEAVVmRepository@@@Z; CaptureStateUtility::SuspendAndSaveSchedulerAssist(VmRepository *)
0x14009c14e  mov     rax, [r14+10h]
0x14009c152  mov     rcx, [rax+588h]
0x14009c159  mov     esi, [rcx+178h]
0x14009c15f  cmp     [rbp+260h+var_70], r13d
0x14009c166  jz      short loc_14009C1B3
0x14009c168  cmp     [rbx+158h], r13b
0x14009c16f  jz      short loc_14009C1BB
0x14009c171  mov     rax, [rbx]
0x14009c174  mov     rcx, [rax+430h]
0x14009c17b  mov     rax, [rcx]
0x14009c17e  mov     rax, [rax+0A8h]
0x14009c185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009c18a  mov     rcx, [rbp+268h]; this
0x14009c191  test    eax, eax
0x14009c193  jns     short loc_14009C1AA
0x14009c195  mov     r9d, eax; char *
0x14009c198  lea     r8, aOnecoreVmWorke_120; "onecore\\vm\\worker\\wpcore\\capturesta"...
0x14009c19f  mov     edx, 0B3h; void *
0x14009c1a4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009c1aa  mov     byte ptr [rbx+15Bh], 1
0x14009c1b1  jmp     short loc_14009C1BB
0x14009c1b3  mov     rcx, rbx; this
0x14009c1b6  call    ?InitializeBalloonedPagesBitmap@CaptureStateUtility@@QEAAXXZ; CaptureStateUtility::InitializeBalloonedPagesBitmap(void)
0x14009c1bb  mov     rcx, [r14+10h]; this
0x14009c1bf  cmp     [rcx+0B98h], r13b
0x14009c1c6  jz      short loc_14009C1F4
0x14009c1c8  mov     rdx, [r14+428h]; struct VmRepository *
0x14009c1cf  call    ?SaveIgvmSaveState@VirtualMachine@@UEAAJPEAVVmRepository@@@Z; VirtualMachine::SaveIgvmSaveState(VmRepository *)
0x14009c1d4  mov     rcx, [rbp+268h]; this
0x14009c1db  test    eax, eax
0x14009c1dd  jns     short loc_14009C1F4
0x14009c1df  mov     r9d, eax; char *
0x14009c1e2  lea     r8, aOnecoreVmWorke_140; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009c1e9  mov     edx, 3B9h; void *
0x14009c1ee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009c1f4  mov     [rsp+360h+var_338], r13; unsigned __int64
0x14009c1f9  mov     rax, cs:qword_1403C0440
0x14009c200  mov     [rsp+360h+var_340], rax; int
0x14009c205  mov     r9b, 1
0x14009c208  xor     r8d, r8d
0x14009c20b  mov     rdx, [r14+428h]
0x14009c212  lea     r12, ?m_Instance@MemoryManager@@0V1@A; MemoryManager MemoryManager::m_Instance
0x14009c219  mov     rcx, r12
0x14009c21c  call    ?SaveRamInformation@MemoryManager@@UEAAXPEAVVmRepository@@W4VmFastSaveType@@_NPEAVGmoBitmap@@PEAT_VM_PERSIST_FLAGS@@@Z; MemoryManager::SaveRamInformation(VmRepository *,VmFastSaveType,bool,GmoBitmap *,_VM_PERSIST_FLAGS *)
0x14009c221  mov     rax, [r14+10h]
0x14009c225  mov     rcx, [rax+400h]
0x14009c22c  mov     rax, [rcx]
0x14009c22f  mov     rdx, [r14+428h]
0x14009c236  mov     rax, [rax+100h]
0x14009c23d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009c242  mov     rdx, [r14+428h]; struct VmRepository *
0x14009c249  mov     rcx, r12; this
0x14009c24c  call    ?SaveVtlProtections@MemoryManager@@UEAAXPEAVVmRepository@@@Z; MemoryManager::SaveVtlProtections(VmRepository *)
0x14009c251  mov     rcx, r12; this
0x14009c254  call    ?GetRamSizeInPages@MemoryManager@@UEBA_KXZ; MemoryManager::GetRamSizeInPages(void)
0x14009c259  lea     rdi, [r14+2A0h]
0x14009c260  mov     [rsp+360h+var_320], esi; unsigned int
0x14009c264  mov     [rsp+360h+var_328], r13; unsigned __int64
0x14009c269  mov     [rsp+360h+var_330], rax; unsigned __int64
0x14009c26e  mov     r9, [r14+18h]; struct IVmSimpleTask *
0x14009c272  mov     r8, [r14+10h]; struct VirtualMachine *
0x14009c276  mov     rdx, [r14+428h]; void *
0x14009c27d  mov     rcx, rdi; this
0x14009c280  call    ?Initialize@GmoRamOperationSnapshot@@QEAAJPEAXPEAVVirtualMachine@@PEAUIVmSimpleTask@@_K333I@Z; GmoRamOperationSnapshot::Initialize(void *,VirtualMachine *,IVmSimpleTask *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,uint)
0x14009c285  mov     rcx, [rbp+268h]; this
0x14009c28c  test    eax, eax
0x14009c28e  jns     short loc_14009C2A5
0x14009c290  mov     r9d, eax; char *
0x14009c293  lea     r8, aOnecoreVmWorke_140; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009c29a  mov     edx, 3D8h; void *
0x14009c29f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009c2a5  cmp     [rbp+260h+var_70], r13d
0x14009c2ac  jz      short loc_14009C32C
0x14009c2ae  cmp     [rbx+158h], r13b
0x14009c2b5  jz      short loc_14009C32C
0x14009c2b7  mov     rcx, [rbp+268h]; this
0x14009c2be  cmp     [rbx+15Bh], r13b
0x14009c2c5  jnz     short loc_14009C2D9
0x14009c2c7  lea     r8, aOnecoreVmWorke_120; "onecore\\vm\\worker\\wpcore\\capturesta"...
0x14009c2ce  mov     edx, 0C0h; void *
0x14009c2d3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14009c2d9  mov     rax, [rbx]
0x14009c2dc  mov     rcx, [rax+430h]
0x14009c2e3  mov     rax, [rcx]
0x14009c2e6  mov     r9d, 2
0x14009c2ec  mov     r8d, 100h
0x14009c2f2  mov     edx, [r14+368h]
0x14009c2f9  mov     rax, [rax+0B8h]
0x14009c300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009c305  mov     rcx, [rbp+268h]; this
0x14009c30c  test    eax, eax
0x14009c30e  jns     short loc_14009C325
0x14009c310  mov     r9d, eax; char *
0x14009c313  lea     r8, aOnecoreVmWorke_120; "onecore\\vm\\worker\\wpcore\\capturesta"...
0x14009c31a  mov     edx, 0C4h; void *
0x14009c31f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009c325  mov     byte ptr [rbx+15Ch], 1
0x14009c32c  mov     rcx, rdi; this
0x14009c32f  call    ?WorkThreadsStart@GmoRamOperation@@QEAAJXZ; GmoRamOperation::WorkThreadsStart(void)
0x14009c334  mov     rcx, [rbp+268h]; this
0x14009c33b  test    eax, eax
0x14009c33d  jns     short loc_14009C354
0x14009c33f  mov     r9d, eax; char *
0x14009c342  lea     r8, aOnecoreVmWorke_140; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009c349  mov     edx, 3E2h; void *
0x14009c34e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009c354  cmp     r15, 2
0x14009c358  jnz     loc_14009C3E5
0x14009c35e  mov     rax, [r14+10h]
0x14009c362  mov     rcx, [rax+400h]
0x14009c369  add     rcx, 18h
0x14009c36d  mov     rax, [rcx]
0x14009c370  mov     rax, [rax]
0x14009c373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009c378  lea     r8, [rbp+260h+var_60]
0x14009c37f  lea     edx, [r15-1]
0x14009c383  mov     rcx, rax
0x14009c386  call    cs:__imp_VidCloneTemplateCreate
0x14009c38d  nop     dword ptr [rax+rax+00h]
0x14009c392  test    eax, eax
0x14009c394  jnz     loc_14009C44A
0x14009c39a  call    cs:__imp_GetLastError
0x14009c3a1  nop     dword ptr [rax+rax+00h]
0x14009c3a6  test    eax, 1FFF0000h
0x14009c3ab  jnz     short loc_14009C3BB
0x14009c3ad  test    eax, eax
0x14009c3af  jle     short loc_14009C3C9
0x14009c3b1  movzx   eax, ax
0x14009c3b4  or      eax, 80070000h
0x14009c3b9  jmp     short loc_14009C3C9
0x14009c3bb  test    eax, eax
0x14009c3bd  jle     short loc_14009C3C9
0x14009c3bf  and     eax, 0FFFFFFFh
0x14009c3c4  or      eax, 80000000h
0x14009c3c9  mov     rcx, [rbp+268h]; this
0x14009c3d0  mov     r9d, eax; char *
0x14009c3d3  lea     r8, aOnecoreVmWorke_140; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009c3da  mov     edx, 3EEh; void *
0x14009c3df  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009c3e5  test    rdi, rdi
0x14009c3e8  lea     rdx, [r14+398h]
0x14009c3ef  jnz     short loc_14009C3F4
0x14009c3f1  mov     rdx, r13; struct MemoryNotificationListener *
0x14009c3f4  mov     rbx, [rbp+268h]
0x14009c3fb  mov     rcx, r12; this
0x14009c3fe  call    ?SetRamNotificationListener@MemoryManager@@UEAAHPEAVMemoryNotificationListener@@@Z; MemoryManager::SetRamNotificationListener(MemoryNotificationListener *)
0x14009c403  test    eax, eax
0x14009c405  jnz     short loc_14009C422
0x14009c407  mov     r9d, 80004005h; char *
0x14009c40d  lea     r8, aOnecoreVmWorke_140; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009c414  mov     edx, 3FAh; void *
0x14009c419  mov     rcx, rbx; this
0x14009c41c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009c422  mov     rcx, rdi; this
0x14009c425  call    ?SetMemoryIntercepts@GmoRamOperationSnapshot@@QEAAJXZ; GmoRamOperationSnapshot::SetMemoryIntercepts(void)
0x14009c42a  mov     rcx, [rbp+268h]; this
0x14009c431  test    eax, eax
0x14009c433  jns     short loc_14009C44A
0x14009c435  mov     r9d, eax; char *
0x14009c438  lea     r8, aOnecoreVmWorke_140; "onecore\\vm\\worker\\wpcore\\workertask"...
0x14009c43f  mov     edx, 3FFh; void *
0x14009c444  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009c44a  lea     rcx, [r14+3B0h]
0x14009c451  lea     rdx, [rbp+260h+var_68]
0x14009c458  call    ??$?4U?$default_delete@VCaptureStateUtility@@@std@@$0A@@?$unique_ptr@VCaptureStateUtility@@U?$default_delete@VCaptureStateUtility@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<CaptureStateUtility>::operator=<std::default_delete<CaptureStateUtility>,0>(std::unique_ptr<CaptureStateUtility> &&)
0x14009c45d  nop
0x14009c45e  lea     rcx, [rbp+260h+var_68]
0x14009c465  call    ??1?$unique_ptr@VCaptureStateUtility@@U?$default_delete@VCaptureStateUtility@@@std@@@std@@QEAA@XZ; std::unique_ptr<CaptureStateUtility>::~unique_ptr<CaptureStateUtility>(void)
0x14009c46a  mov     rcx, [rbp+260h+var_50]
0x14009c471  xor     rcx, rsp; StackCookie
0x14009c474  call    __security_check_cookie
0x14009c479  add     rsp, 328h
0x14009c480  pop     r15
0x14009c482  pop     r14
0x14009c484  pop     r13
0x14009c486  pop     r12
0x14009c488  pop     rdi
0x14009c489  pop     rsi
0x14009c48a  pop     rbx
0x14009c48b  pop     rbp
0x14009c48c  retn
```
