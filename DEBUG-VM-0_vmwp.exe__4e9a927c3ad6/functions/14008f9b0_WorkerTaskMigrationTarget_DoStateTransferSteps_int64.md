# WorkerTaskMigrationTarget::DoStateTransferSteps(__int64 &)

- ea: `0x14008f9b0`
- end: `0x14008ff62`
- name: `?DoStateTransferSteps@WorkerTaskMigrationTarget@@AEAAJAEA_J@Z`
- size: `1458`
- prototype: `__int64 __fastcall(WorkerTaskMigrationTarget *__hidden this, __int64 *)`
- caller_count: `1`
- callee_count: `29`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400914e0`

## callees

- `0x140031c88`
- `0x140042240`
- `0x140054508`
- `0x140054630`
- `0x1400549dc`
- `0x14006af38`
- `0x14007a72c`
- `0x140088408`
- `0x140089084`
- `0x14008f9b0`
- `0x14008ff68`
- `0x140090390`
- `0x140090440`
- `0x140092e38`
- `0x140093098`
- `0x1400a0854`
- `0x1400a09e0`
- `0x1400a0eb0`
- `0x1400a2294`
- `0x1400ccc40`
- `0x1400edc00`
- `0x14010abe0`
- `0x140111070`
- `0x140117ca8`
- `0x14012f9f4`
- `0x140132940`
- `0x1401eb9e0`
- `0x140223ac4`
- `0x1402c2010`

## string_xrefs

- `0x14008fac0`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008faf1`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fb19`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fb41`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fb7b`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fbb6`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fc0b`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fc78`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fcc1`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fd19`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fd7d`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fdaa`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fe2a`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fe67`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008fea1`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WorkerTaskMigrationTarget::DoStateTransferSteps(WorkerTaskMigrationTarget *this, __int64 *a2)
{
  __int64 *v2; // r12
  const struct _GUID *v4; // r15
  unsigned int v5; // r13d
  int v6; // esi
  int v7; // eax
  int v8; // eax
  int started; // eax
  SavedStateRepository **v10; // r14
  int Instance; // eax
  bool v12; // r8
  int v13; // esi
  unsigned int Integer; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  bool v18; // r8
  int v19; // eax
  int v20; // eax
  int v21; // eax
  const struct Vml::ExceptionTraceParameters *v22; // r8
  int v24; // [rsp+20h] [rbp-158h]
  SavedStateMigrationNetwork *v25; // [rsp+30h] [rbp-148h] BYREF
  struct _GUID v26; // [rsp+38h] [rbp-140h] BYREF
  __int64 *v27; // [rsp+48h] [rbp-130h]
  char *v28[2]; // [rsp+50h] [rbp-128h] BYREF
  _BYTE v29[12]; // [rsp+60h] [rbp-118h] BYREF
  int v30; // [rsp+6Ch] [rbp-10Ch]
  __int64 v31; // [rsp+78h] [rbp-100h]
  __int64 v32; // [rsp+80h] [rbp-F8h]
  _BYTE v33[72]; // [rsp+88h] [rbp-F0h] BYREF
  _BYTE v34[24]; // [rsp+D0h] [rbp-A8h] BYREF
  __int64 v35; // [rsp+E8h] [rbp-90h]
  __int64 v36; // [rsp+F0h] [rbp-88h]
  _BYTE v37[72]; // [rsp+F8h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v2 = a2;
  v27 = a2;
  v26 = 0;
  v4 = (const struct _GUID *)((char *)this + 412);
  Vml::VmPerfTraceOperation::VmPerfTraceOperation(
    (Vml::VmPerfTraceOperation *)v34,
    (struct Vml::VmPerfTraceComponent *)&g_MigrationPerfTrace,
    (const struct _GUID *)((char *)this + 412),
    &v26);
  v26 = 0;
  Vml::VmPerfTraceOperation::VmPerfTraceOperation(
    (Vml::VmPerfTraceOperation *)v29,
    (struct Vml::VmPerfTraceComponent *)&g_MigrationPerfTrace,
    v4,
    &v26);
  v35 = *v2;
  Vml::VmPerfTraceOperation::BeginOperation<>((Vml::VmPerfTraceOperation *)v34, &VMWP_PERF_MIGRATION_TARGET_MOVE_START);
  v31 = *v2;
  Vml::VmPerfTraceOperation::BeginOperation<>(
    (Vml::VmPerfTraceOperation *)v29,
    &VMWP_PERF_MIGRATION_TARGET_MOVE_RECEIVE_STATE_START);
  v5 = 0;
  try
  {
    v25 = 0;
    v6 = SavedStateMigrationNetwork::CreateInstance(
           *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 1416LL) + 376LL),
           &v25);
    if ( v6 < 0 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
        VmlDebugTraceWithError(16866, &off_1402DB3E0, (unsigned int)v6);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x47B,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v6,
        v24);
    }
    if ( *((_BYTE *)this + 409) )
    {
      v7 = WorkerTaskMigrationTarget::DoTdxMutableStateImport(this);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x481,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v7,
          v24);
      v8 = WorkerTaskMigrationTarget::DoTdxVpStateImport(this);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x482,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v8,
          v24);
      started = WorkerTaskMigrationTarget::DoTdxStartTokenImport(this);
      if ( started < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x483,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)started,
          v24);
    }
    v10 = (SavedStateRepository **)((char *)this + 568);
    Instance = SavedStateRepository::CreateInstance(v4, v25, (struct SavedStateRepository **)this + 71);
    if ( Instance < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x487,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)Instance,
        v24);
    *(_OWORD *)v28 = 0;
    VmSavedStateStorageAutoLock::VmSavedStateStorageAutoLock((VmSavedStateStorageAutoLock *)v28, v25, v12);
    if ( SLODWORD(v28[1]) < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x48B,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)LODWORD(v28[1]),
        v24);
    v13 = SavedStateMigrationNetwork::Import(v25, *((struct VmMigrationConnection **)this + 55));
    if ( v13 < 0 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
        VmlDebugTraceWithError(16866, &off_1402DB208, (unsigned int)v13);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x493,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v13,
        v24);
    }
    VmSavedStateStorageAutoLock::~VmSavedStateStorageAutoLock((VmSavedStateStorageAutoLock *)v28);
    if ( (*((_BYTE *)this + 480) & 0x20) != 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 57) + 72LL))(*((_QWORD *)this + 57));
    v28[0] = 0;
    v26 = 0;
    VmRepositoryAutoLock::VmRepositoryAutoLock(&v26, *v10, 1);
    if ( *(int *)v26.Data4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4A7,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)*(unsigned int *)v26.Data4,
        v24);
    v28[0] = 0;
    Integer = SavedStateRepository::ReadInteger(*v10, L"/savedVM/migration_run_state", (__int64 *)v28);
    if ( (int)(Integer + 0x80000000) >= 0 && Integer != -2147188715 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4B0,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)Integer,
        v24);
    *(_DWORD *)(*((_QWORD *)this + 54) + 88LL) = v28[0] == (char *)1;
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)&v26);
    Vml::VmPerfTraceOperation::EndOperation<>(
      (Vml::VmPerfTraceOperation *)v29,
      &VMWP_PERF_MIGRATION_TARGET_MOVE_RECEIVE_STATE_STOP);
    v15 = WorkerTaskMigrationTarget::CheckCancel(this);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4BD,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v15,
        v24);
    if ( (*((_BYTE *)this + 480) & 1) != 0 && !*((_DWORD *)this + 122) )
    {
      v31 = 0;
      v32 = 0;
      v30 = 1;
      Vml::VmPerfTraceOperation::BeginOperation<>(
        (Vml::VmPerfTraceOperation *)v29,
        &VMWP_PERF_MIGRATION_TARGET_MOVE_CHECKSUMS_START);
      v16 = WorkerTaskMigrationTarget::VerifyRamChecksums(this);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4D3,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v16,
          v24);
      v17 = WorkerTaskMigrationTarget::VerifyRuntimeStateChecksum(this, v25);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4D6,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v17,
          v24);
      Vml::VmPerfTraceOperation::EndOperation<>(
        (Vml::VmPerfTraceOperation *)v29,
        &VMWP_PERF_MIGRATION_TARGET_MOVE_CHECKSUMS_STOP);
    }
    if ( (*((_BYTE *)this + 480) & 0x20) == 0 )
    {
      LODWORD(v28[0]) = 0;
      v31 = 0;
      v32 = 0;
      v30 = 1;
      Vml::VmPerfTraceOperation::BeginOperation<>(
        (Vml::VmPerfTraceOperation *)v29,
        &VMWP_PERF_MIGRATION_TARGET_MOVE_WAIT_OWNER_START);
      v19 = MigrationManager::WaitForFinalStateTransition(
              *((MigrationManager **)this + 54),
              0x12Cu,
              v18,
              (enum MigrationManager::FINAL_STATE_TRANSITION *)v28,
              0);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4ED,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v19,
          v24);
      Vml::VmPerfTraceOperation::EndOperation<>(
        (Vml::VmPerfTraceOperation *)v29,
        &VMWP_PERF_MIGRATION_TARGET_MOVE_WAIT_OWNER_STOP);
      v20 = WorkerTaskMigrationTarget::TransitionWorkerProcess(this, LODWORD(v28[0]));
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4F4,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
          (const char *)(unsigned int)v20,
          v24);
    }
    v21 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 1072LL) + 240LL))(*(_QWORD *)(*((_QWORD *)this + 2) + 1072LL));
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4FA,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v21,
        v24);
    if ( (int)WorkerTaskMigrationTarget::IndicateStatusToSource(this, 8) < 0
      && (unsigned int)VmlIsDebugTraceEnabled(33250) )
    {
      VmlDebugTraceEx(33250, &off_1402DB2D0);
    }
    Vml::VmReferencePtr<IVmMigrationTransport,Vml::VmUserReferenceTraits>::~VmReferencePtr<IVmMigrationTransport,Vml::VmUserReferenceTraits>(&v25);
  }
  catch ( ... )
  {
    LODWORD(v28[0]) = Vml::GetHResultFromThrownExceptionAndTrace((Vml *)0x41E2, (unsigned __int16)&off_1402DB238, v22);
    v5 = (unsigned int)v28[0];
    v2 = v27;
  }
  Vml::VmPerfTraceOperation::EndOperation<>((Vml::VmPerfTraceOperation *)v34, &VMWP_PERF_MIGRATION_TARGET_MOVE_STOP);
  *v2 = v36;
  std::wstring::_Tidy_deallocate(v33);
  std::wstring::_Tidy_deallocate(v37);
  return v5;
}

```

## disassembly

```asm
0x14008f9b0  mov     [rsp+arg_10], rsi
0x14008f9b5  push    rdi
0x14008f9b6  push    r12
0x14008f9b8  push    r13
0x14008f9ba  push    r14
0x14008f9bc  push    r15
0x14008f9be  sub     rsp, 150h
0x14008f9c5  mov     rax, cs:__security_cookie
0x14008f9cc  xor     rax, rsp
0x14008f9cf  mov     [rsp+178h+var_38], rax
0x14008f9d7  mov     r12, rdx
0x14008f9da  mov     rdi, rcx
0x14008f9dd  mov     [rsp+178h+var_130], rdx
0x14008f9e2  xorps   xmm0, xmm0
0x14008f9e5  movups  xmmword ptr [rsp+178h+var_140.Data1], xmm0
0x14008f9ea  lea     r15, [rcx+19Ch]
0x14008f9f1  lea     r9, [rsp+178h+var_140]; struct _GUID *
0x14008f9f6  mov     r8, r15; struct _GUID *
0x14008f9f9  lea     rdx, ?g_MigrationPerfTrace@@3VVmPerfTraceComponent@Vml@@A; struct Vml::VmPerfTraceComponent *
0x14008fa00  lea     rcx, [rsp+178h+var_A8]; this
0x14008fa08  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x14008fa0d  nop
0x14008fa0e  xorps   xmm0, xmm0
0x14008fa11  movups  xmmword ptr [rsp+178h+var_140.Data1], xmm0
0x14008fa16  lea     r9, [rsp+178h+var_140]; struct _GUID *
0x14008fa1b  mov     r8, r15; struct _GUID *
0x14008fa1e  lea     rdx, ?g_MigrationPerfTrace@@3VVmPerfTraceComponent@Vml@@A; struct Vml::VmPerfTraceComponent *
0x14008fa25  lea     rcx, [rsp+178h+var_118]; this
0x14008fa2a  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x14008fa2f  nop
0x14008fa30  mov     rax, [r12]
0x14008fa34  mov     [rsp+178h+var_90], rax
0x14008fa3c  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_START; EventDescriptor
0x14008fa43  lea     rcx, [rsp+178h+var_A8]; this
0x14008fa4b  call    ??$BeginOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::BeginOperation<>(_EVENT_DESCRIPTOR const &)
0x14008fa50  mov     rax, [r12]
0x14008fa54  mov     [rsp+178h+var_100], rax
0x14008fa59  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_RECEIVE_STATE_START; EventDescriptor
0x14008fa60  lea     rcx, [rsp+178h+var_118]; this
0x14008fa65  call    ??$BeginOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::BeginOperation<>(_EVENT_DESCRIPTOR const &)
0x14008fa6a  xor     r13d, r13d
0x14008fa6d  mov     [rsp+178h+var_148], r13
0x14008fa72  mov     rax, [rdi+10h]
0x14008fa76  mov     rcx, [rax+588h]
0x14008fa7d  lea     rdx, [rsp+178h+var_148]; struct SavedStateMigrationNetwork **
0x14008fa82  mov     ecx, [rcx+178h]; unsigned int
0x14008fa88  call    ?CreateInstance@SavedStateMigrationNetwork@@SAJIPEAPEAV1@@Z; SavedStateMigrationNetwork::CreateInstance(uint,SavedStateMigrationNetwork * *)
0x14008fa8d  mov     esi, eax
0x14008fa8f  test    eax, eax
0x14008fa91  jns     short loc_14008FAD1
0x14008fa93  mov     ecx, 41E2h
0x14008fa98  call    VmlIsDebugTraceEnabled
0x14008fa9d  test    eax, eax
0x14008fa9f  jz      short loc_14008FAB5
0x14008faa1  mov     r8d, esi
0x14008faa4  lea     rdx, off_1402DB3E0; "Failed to create runtime state storage."
0x14008faab  mov     ecx, 41E2h
0x14008fab0  call    VmlDebugTraceWithError
0x14008fab5  mov     rcx, [rsp+178h]; this
0x14008fabd  mov     r9d, esi; char *
0x14008fac0  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fac7  mov     edx, 47Bh; void *
0x14008facc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fad1  cmp     byte ptr [rdi+199h], 0
0x14008fad8  jz      short loc_14008FB52
0x14008fada  mov     rcx, rdi; this
0x14008fadd  call    ?DoTdxMutableStateImport@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::DoTdxMutableStateImport(void)
0x14008fae2  mov     rcx, [rsp+178h]; this
0x14008faea  test    eax, eax
0x14008faec  jns     short loc_14008FB02
0x14008faee  mov     r9d, eax; char *
0x14008faf1  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008faf8  mov     edx, 481h; void *
0x14008fafd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fb02  mov     rcx, rdi; this
0x14008fb05  call    ?DoTdxVpStateImport@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::DoTdxVpStateImport(void)
0x14008fb0a  mov     rcx, [rsp+178h]; this
0x14008fb12  test    eax, eax
0x14008fb14  jns     short loc_14008FB2A
0x14008fb16  mov     r9d, eax; char *
0x14008fb19  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fb20  mov     edx, 482h; void *
0x14008fb25  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fb2a  mov     rcx, rdi; this
0x14008fb2d  call    ?DoTdxStartTokenImport@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::DoTdxStartTokenImport(void)
0x14008fb32  mov     rcx, [rsp+178h]; this
0x14008fb3a  test    eax, eax
0x14008fb3c  jns     short loc_14008FB52
0x14008fb3e  mov     r9d, eax; char *
0x14008fb41  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fb48  mov     edx, 483h; void *
0x14008fb4d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fb52  lea     r14, [rdi+238h]
0x14008fb59  mov     r8, r14; struct SavedStateRepository **
0x14008fb5c  mov     rdx, [rsp+178h+var_148]; struct ISavedStateStorage *
0x14008fb61  mov     rcx, r15; struct _GUID *
0x14008fb64  call    ?CreateInstance@SavedStateRepository@@SAJAEBU_GUID@@PEAVISavedStateStorage@@PEAPEAV1@@Z; SavedStateRepository::CreateInstance(_GUID const &,ISavedStateStorage *,SavedStateRepository * *)
0x14008fb69  mov     rcx, [rsp+178h]; this
0x14008fb71  xor     r15d, r15d
0x14008fb74  test    eax, eax
0x14008fb76  jns     short loc_14008FB8C
0x14008fb78  mov     r9d, eax; char *
0x14008fb7b  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fb82  mov     edx, 487h; void *
0x14008fb87  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fb8c  xorps   xmm0, xmm0
0x14008fb8f  movups  xmmword ptr [rsp+178h+var_128], xmm0
0x14008fb94  mov     rdx, [rsp+178h+var_148]; struct SavedStateStorage *
0x14008fb99  lea     rcx, [rsp+178h+var_128]; this
0x14008fb9e  call    ??0VmSavedStateStorageAutoLock@@QEAA@PEAVSavedStateStorage@@_N@Z; VmSavedStateStorageAutoLock::VmSavedStateStorageAutoLock(SavedStateStorage *,bool)
0x14008fba3  nop
0x14008fba4  mov     r9d, dword ptr [rsp+178h+var_128+8]; char *
0x14008fba9  mov     rcx, [rsp+178h]; this
0x14008fbb1  test    r9d, r9d
0x14008fbb4  jns     short loc_14008FBC7
0x14008fbb6  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fbbd  mov     edx, 48Bh; void *
0x14008fbc2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fbc7  mov     rdx, [rdi+1B8h]; struct VmMigrationConnection *
0x14008fbce  mov     rcx, [rsp+178h+var_148]; this
0x14008fbd3  call    ?Import@SavedStateMigrationNetwork@@QEAAJPEAVVmMigrationConnection@@@Z; SavedStateMigrationNetwork::Import(VmMigrationConnection *)
0x14008fbd8  mov     esi, eax
0x14008fbda  test    eax, eax
0x14008fbdc  jns     short loc_14008FC1D
0x14008fbde  mov     ecx, 41E2h
0x14008fbe3  call    VmlIsDebugTraceEnabled
0x14008fbe8  test    eax, eax
0x14008fbea  jz      short loc_14008FC00
0x14008fbec  mov     r8d, esi
0x14008fbef  lea     rdx, off_1402DB208; "Failed to receive the VM runtime-state "...
0x14008fbf6  mov     ecx, 41E2h
0x14008fbfb  call    VmlDebugTraceWithError
0x14008fc00  mov     rcx, [rsp+178h]; this
0x14008fc08  mov     r9d, esi; char *
0x14008fc0b  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fc12  mov     edx, 493h; void *
0x14008fc17  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fc1d  lea     rcx, [rsp+178h+var_128]; this
0x14008fc22  call    ??1VmSavedStateStorageAutoLock@@QEAA@XZ; VmSavedStateStorageAutoLock::~VmSavedStateStorageAutoLock(void)
0x14008fc27  test    byte ptr [rdi+1E0h], 20h
0x14008fc2e  jz      short loc_14008FC43
0x14008fc30  mov     rcx, [rdi+1C8h]
0x14008fc37  mov     rax, [rcx]
0x14008fc3a  mov     rax, [rax+48h]
0x14008fc3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008fc43  mov     [rsp+178h+var_128], r15
0x14008fc48  xorps   xmm0, xmm0
0x14008fc4b  movups  xmmword ptr [rsp+178h+var_140.Data1], xmm0
0x14008fc50  mov     esi, 1
0x14008fc55  mov     r8d, esi
0x14008fc58  mov     rdx, [r14]
0x14008fc5b  lea     rcx, [rsp+178h+var_140]
0x14008fc60  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x14008fc65  nop
0x14008fc66  mov     r9d, dword ptr [rsp+178h+var_140.Data4]; char *
0x14008fc6b  mov     rcx, [rsp+178h]; this
0x14008fc73  test    r9d, r9d
0x14008fc76  jns     short loc_14008FC89
0x14008fc78  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fc7f  mov     edx, 4A7h; void *
0x14008fc84  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fc89  mov     [rsp+178h+var_128], r15
0x14008fc8e  lea     r8, [rsp+178h+var_128]; __int64 *
0x14008fc93  lea     rdx, ?VM_MIGRATION_RUN_STATE_XPATH@@3QBGB; "/savedVM/migration_run_state"
0x14008fc9a  mov     rcx, [r14]; this
0x14008fc9d  call    ?ReadInteger@SavedStateRepository@@UEBAJPEBGAEA_J@Z; SavedStateRepository::ReadInteger(ushort const *,__int64 &)
0x14008fca2  mov     r9d, eax; char *
0x14008fca5  mov     ecx, 80000000h
0x14008fcaa  add     eax, ecx
0x14008fcac  test    ecx, eax
0x14008fcae  jnz     short loc_14008FCD2
0x14008fcb0  cmp     r9d, 80048015h
0x14008fcb7  jz      short loc_14008FCD2
0x14008fcb9  mov     rcx, [rsp+178h]; this
0x14008fcc1  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fcc8  mov     edx, 4B0h; void *
0x14008fccd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fcd2  mov     rcx, [rdi+1B0h]
0x14008fcd9  mov     eax, r15d
0x14008fcdc  cmp     [rsp+178h+var_128], rsi
0x14008fce1  setz    al
0x14008fce4  mov     [rcx+58h], eax
0x14008fce7  lea     rcx, [rsp+178h+var_140]; this
0x14008fcec  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x14008fcf1  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_RECEIVE_STATE_STOP; EventDescriptor
0x14008fcf8  lea     rcx, [rsp+178h+var_118]; this
0x14008fcfd  call    ??$EndOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::EndOperation<>(_EVENT_DESCRIPTOR const &)
0x14008fd02  mov     rcx, rdi; this
0x14008fd05  call    ?CheckCancel@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::CheckCancel(void)
0x14008fd0a  mov     rcx, [rsp+178h]; this
0x14008fd12  test    eax, eax
0x14008fd14  jns     short loc_14008FD2A
0x14008fd16  mov     r9d, eax; char *
0x14008fd19  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fd20  mov     edx, 4BDh; void *
0x14008fd25  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fd2a  test    [rdi+1E0h], sil
0x14008fd31  jz      loc_14008FDCC
0x14008fd37  cmp     [rdi+1E8h], r15d
0x14008fd3e  jnz     loc_14008FDCC
0x14008fd44  mov     [rsp+178h+var_100], r15
0x14008fd49  mov     [rsp+178h+var_F8], r15
0x14008fd51  mov     [rsp+178h+var_10C], esi
0x14008fd55  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_CHECKSUMS_START; EventDescriptor
0x14008fd5c  lea     rcx, [rsp+178h+var_118]; this
0x14008fd61  call    ??$BeginOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::BeginOperation<>(_EVENT_DESCRIPTOR const &)
0x14008fd66  mov     rcx, rdi; this
0x14008fd69  call    ?VerifyRamChecksums@WorkerTaskMigrationTarget@@AEAAJXZ; WorkerTaskMigrationTarget::VerifyRamChecksums(void)
0x14008fd6e  mov     rcx, [rsp+178h]; this
0x14008fd76  test    eax, eax
0x14008fd78  jns     short loc_14008FD8E
0x14008fd7a  mov     r9d, eax; char *
0x14008fd7d  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fd84  mov     edx, 4D3h; void *
0x14008fd89  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fd8e  mov     rdx, [rsp+178h+var_148]; struct SavedStateMigrationNetwork *
0x14008fd93  mov     rcx, rdi; this
0x14008fd96  call    ?VerifyRuntimeStateChecksum@WorkerTaskMigrationTarget@@AEAAJPEAVSavedStateMigrationNetwork@@@Z; WorkerTaskMigrationTarget::VerifyRuntimeStateChecksum(SavedStateMigrationNetwork *)
0x14008fd9b  mov     rcx, [rsp+178h]; this
0x14008fda3  test    eax, eax
0x14008fda5  jns     short loc_14008FDBB
0x14008fda7  mov     r9d, eax; char *
0x14008fdaa  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fdb1  mov     edx, 4D6h; void *
0x14008fdb6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fdbb  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_CHECKSUMS_STOP; EventDescriptor
0x14008fdc2  lea     rcx, [rsp+178h+var_118]; this
0x14008fdc7  call    ??$EndOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::EndOperation<>(_EVENT_DESCRIPTOR const &)
0x14008fdcc  test    byte ptr [rdi+1E0h], 20h
0x14008fdd3  jnz     loc_14008FE78
0x14008fdd9  mov     dword ptr [rsp+178h+var_128], r15d
0x14008fdde  mov     [rsp+178h+var_100], r15
0x14008fde3  mov     [rsp+178h+var_F8], r15
0x14008fdeb  mov     [rsp+178h+var_10C], esi
0x14008fdef  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_WAIT_OWNER_START; EventDescriptor
0x14008fdf6  lea     rcx, [rsp+178h+var_118]; this
0x14008fdfb  call    ??$BeginOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::BeginOperation<>(_EVENT_DESCRIPTOR const &)
0x14008fe00  mov     qword ptr [rsp+178h+var_158], r15; int
0x14008fe05  lea     r9, [rsp+178h+var_128]; enum MigrationManager::FINAL_STATE_TRANSITION *
0x14008fe0a  mov     edx, 12Ch; unsigned int
0x14008fe0f  mov     rcx, [rdi+1B0h]; this
0x14008fe16  call    ?WaitForFinalStateTransition@MigrationManager@@QEAAJI_NAEAW4FINAL_STATE_TRANSITION@1@PEAPEAUIVmSimpleTask@@@Z; MigrationManager::WaitForFinalStateTransition(uint,bool,MigrationManager::FINAL_STATE_TRANSITION &,IVmSimpleTask * *)
0x14008fe1b  mov     rcx, [rsp+178h]; this
0x14008fe23  test    eax, eax
0x14008fe25  jns     short loc_14008FE3B
0x14008fe27  mov     r9d, eax; char *
0x14008fe2a  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fe31  mov     edx, 4EDh; void *
0x14008fe36  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fe3b  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_WAIT_OWNER_STOP; EventDescriptor
0x14008fe42  lea     rcx, [rsp+178h+var_118]; this
0x14008fe47  call    ??$EndOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::EndOperation<>(_EVENT_DESCRIPTOR const &)
0x14008fe4c  mov     edx, dword ptr [rsp+178h+var_128]
0x14008fe50  mov     rcx, rdi
0x14008fe53  call    ?TransitionWorkerProcess@WorkerTaskMigrationTarget@@AEAAJW4FINAL_STATE_TRANSITION@MigrationManager@@@Z; WorkerTaskMigrationTarget::TransitionWorkerProcess(MigrationManager::FINAL_STATE_TRANSITION)
0x14008fe58  mov     rcx, [rsp+178h]; this
0x14008fe60  test    eax, eax
0x14008fe62  jns     short loc_14008FE78
0x14008fe64  mov     r9d, eax; char *
0x14008fe67  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fe6e  mov     edx, 4F4h; void *
0x14008fe73  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008fe78  mov     rax, [rdi+10h]
0x14008fe7c  mov     rcx, [rax+430h]
0x14008fe83  mov     rax, [rcx]
0x14008fe86  mov     rax, [rax+0F0h]
0x14008fe8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008fe92  mov     rcx, [rsp+178h]; this
0x14008fe9a  test    eax, eax
0x14008fe9c  jns     short loc_14008FEB2
0x14008fe9e  mov     r9d, eax; char *
0x14008fea1  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008fea8  mov     edx, 4FAh; void *
0x14008fead  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008feb2  mov     edx, 8
0x14008feb7  mov     rcx, rdi
0x14008feba  call    ?IndicateStatusToSource@WorkerTaskMigrationTarget@@AEAAJW4MESSAGE_SEQUENCE_TYPE@VmMigrationConnection@@KJ@Z; WorkerTaskMigrationTarget::IndicateStatusToSource(VmMigrationConnection::MESSAGE_SEQUENCE_TYPE,ulong,long)
0x14008febf  test    eax, eax
0x14008fec1  jns     short loc_14008FEE3
0x14008fec3  mov     ecx, 81E2h
0x14008fec8  call    VmlIsDebugTraceEnabled
0x14008fecd  test    eax, eax
0x14008fecf  jz      short loc_14008FEE3
0x14008fed1  lea     rdx, off_1402DB2D0; "Failed to signal migration completion t"...
0x14008fed8  mov     ecx, 81E2h
0x14008fedd  call    VmlDebugTraceEx
0x14008fee2  nop
0x14008fee3  lea     rcx, [rsp+178h+var_148]
0x14008fee8  call    ??1?$VmReferencePtr@VIVmMigrationTransport@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<IVmMigrationTransport,Vml::VmUserReferenceTraits>::~VmReferencePtr<IVmMigrationTransport,Vml::VmUserReferenceTraits>(void)
0x14008feed  nop
0x14008feee  jmp     short loc_14008FEFA
0x14008fef0  mov     r13d, dword ptr [rsp+178h+var_128]
0x14008fef5  mov     r12, [rsp+178h+var_130]
0x14008fefa  lea     rdx, VMWP_PERF_MIGRATION_TARGET_MOVE_STOP; EventDescriptor
0x14008ff01  lea     rcx, [rsp+178h+var_A8]; this
0x14008ff09  call    ??$EndOperation@$$V@VmPerfTraceOperation@Vml@@QEAAXAEBU_EVENT_DESCRIPTOR@@@Z; Vml::VmPerfTraceOperation::EndOperation<>(_EVENT_DESCRIPTOR const &)
0x14008ff0e  mov     rcx, [rsp+178h+var_88]
0x14008ff16  mov     [r12], rcx
0x14008ff1a  lea     rcx, [rsp+178h+var_F0]
0x14008ff22  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
  ... truncated ...
```
