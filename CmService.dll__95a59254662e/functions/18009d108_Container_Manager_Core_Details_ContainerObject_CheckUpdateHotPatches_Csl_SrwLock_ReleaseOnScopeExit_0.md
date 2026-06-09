# Container::Manager::Core::Details::ContainerObject::CheckUpdateHotPatches(Csl::SrwLock::ReleaseOnScopeExit<0> &)

- ea: `0x18009d108`
- end: `0x18009d4f5`
- name: `?CheckUpdateHotPatches@ContainerObject@Details@Core@Manager@Container@@AEAAJAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z`
- size: `1005`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800b9b40`

## callees

- `0x180004bd0`
- `0x180007b48`
- `0x180007dd4`
- `0x180009ba0`
- `0x18000da88`
- `0x1800103a4`
- `0x180016718`
- `0x18004eff8`
- `0x18009b018`
- `0x18009d108`
- `0x1800a321c`
- `0x1800a32d0`
- `0x1800a3388`
- `0x1800aab8c`
- `0x1800ac950`
- `0x1800aefec`
- `0x1800fb1dc`
- `0x180110cc8`
- `0x180193f30`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18009d162`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18009d162`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x18009d47e`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x18009d47e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009d3fe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009d3fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d26c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d42e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d446`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d26c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d42e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d446`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009d16e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009d40a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009d16e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009d40a`

## string_xrefs

- `0x18009d299`: `AgentUpdateHotPatches`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Container::Manager::Core::Details::ContainerObject::CheckUpdateHotPatches(
        struct _GUID *a1,
        PSRWLOCK *a2)
{
  int HotPatches; // eax
  int v6; // r14d
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  int v9; // eax
  unsigned int v10; // r14d
  PSRWLOCK v11; // rcx
  int updated; // eax
  RTL_SRWLOCK *v13; // rbx
  int v14; // eax
  PSRWLOCK v15; // rcx
  int v16; // [rsp+20h] [rbp-E0h]
  _OWORD v17[3]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+68h] [rbp-98h]
  __int64 v19[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v20; // [rsp+80h] [rbp-80h]
  __int128 v21; // [rsp+90h] [rbp-70h]
  char v22; // [rsp+A0h] [rbp-60h]
  char v23; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v24[42]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  for ( ; BYTE1(a1[52].Data1); LODWORD((*a2)[1].Ptr) = GetCurrentThreadId() )
  {
    LODWORD((*a2)[1].Ptr) = 0;
    SleepConditionVariableSRW((PCONDITION_VARIABLE)a1[52].Data4, *a2, 0xFFFFFFFF, 0);
  }
  if ( !Container::Manager::Core::Details::ContainerObject::IsHotPatchUpdateRequired((Container::Manager::Core::Details::ContainerObject *)a1) )
    return 0;
  memset(v17, 0, sizeof(v17));
  v18 = 0;
  HotPatches = Container::Manager::Core::Details::SystemConfigurationManager::QueryHotPatches(*(PSRWLOCK *)a1[87].Data4);
  v6 = HotPatches;
  if ( HotPatches >= 0 )
  {
    if ( *(_QWORD *)&v17[0] != *((_QWORD *)&v17[0] + 1) )
    {
      BYTE1(a1[52].Data1) = 1;
      Container::Manager::Core::Details::ContainerObject::AcquireAndWaitForContainerInfrastructureWakeReference(a1, a2);
      if ( !(_BYTE)v18 )
        __int2c();
      v9 = Container::Manager::Core::Details::ContainerObject::PrepareForHotPatching((Container::Manager::Core::Details::ContainerObject *)a1);
      v6 = v9;
      if ( v9 >= 0 )
      {
        if ( a1[51].Data4[4] )
          v10 = *(_DWORD *)a1[51].Data4;
        else
          v10 = 0;
        v11 = *a2;
        if ( *a2 )
        {
          LODWORD(v11[1].Ptr) = 0;
          ReleaseSRWLockExclusive(v11);
          *a2 = 0;
        }
        Container::Manager::Core::Details::PolicyManager::IsManualHotPatchMode(*(Container::Manager::Core::Details::PolicyManager **)a1[81].Data4);
        __int2c();
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
          v24,
          "AgentUpdateHotPatches");
        v24[0] = &CmTraceProvider::AgentUpdateHotPatches::`vftable';
        CmTraceProvider::AgentUpdateHotPatches::StartActivity((CmTraceProvider::AgentUpdateHotPatches *)v24, a1, v10, 0);
        LOBYTE(v19[0]) = 0;
        v22 = 0;
        if ( (_BYTE)v18 )
        {
          *(_OWORD *)v19 = v17[0];
          v20 = v17[1];
          *(_QWORD *)&v17[0] = -1;
          *(__m128i *)((char *)v17 + 8) = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
          v21 = v17[2];
          *(_OWORD *)((char *)&v17[1] + 8) = *(_OWORD *)((char *)v17 + 8);
          *((_QWORD *)&v17[2] + 1) = -1;
          v22 = 1;
        }
        updated = Container::Manager::Agent::Client::CmAgentConnection::UpdateHotPatches(*(Container::Manager::Agent::Client **)a1[79].Data4);
        v6 = updated;
        if ( updated < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2FE5,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
            (const char *)(unsigned int)updated,
            v16);
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
          v24,
          (unsigned int)v6);
        if ( v6 < 0 || (*(_DWORD *)(*(_QWORD *)a1[81].Data4 + 96LL) & 0x80000) != 0 )
        {
          v13 = *(RTL_SRWLOCK **)a1[90].Data4;
          *(_OWORD *)v19 = 0;
          v20 = 0;
          *(_QWORD *)&v21 = 0;
          Container::Manager::Core::Details::PolicyManager::IsSystemLoggerConfigured(*(Container::Manager::Core::Details::PolicyManager **)a1[81].Data4);
          v14 = Container::Manager::Core::Details::LogManager::CopyLogsFromComputeSystem(
                  v13,
                  *(Container::Manager::Hcs::ComputeSystem **)a1[78].Data4,
                  (__int64)v19);
          if ( v14 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x2FF1,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
              (const char *)(unsigned int)v14,
              v16);
        }
        AcquireSRWLockExclusive((PSRWLOCK)a1[28].Data4);
        a1[29].Data1 = GetCurrentThreadId();
        if ( a2 == (PSRWLOCK *)&v23 )
        {
          a1[29].Data1 = 0;
          ReleaseSRWLockExclusive((PSRWLOCK)a1[28].Data4);
        }
        else
        {
          v15 = *a2;
          if ( *a2 )
          {
            LODWORD(v15[1].Ptr) = 0;
            ReleaseSRWLockExclusive(v15);
          }
          *a2 = (PSRWLOCK)a1[28].Data4;
        }
        v24[0] = &CmTraceProvider::AgentUpdateHotPatches::`vftable';
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v24);
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v24);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2FCC,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
          (const char *)(unsigned int)v9,
          v16);
      }
      Container::Manager::Core::Details::ContainerObject::ReleaseContainerInfrastructureWakeReference((Container::Manager::Core::Details::ContainerObject *)a1);
      BYTE1(a1[52].Data1) = 0;
      WakeConditionVariable((PCONDITION_VARIABLE)a1[52].Data4);
      if ( v6 < 0 )
      {
        v7 = (unsigned int)v6;
        v8 = 12287;
        goto LABEL_33;
      }
      LOBYTE(a1[52].Data1) = 1;
    }
    *(_QWORD *)a1[51].Data4 = 0;
    v6 = 0;
    goto LABEL_36;
  }
  v7 = (unsigned int)HotPatches;
  v8 = 12222;
LABEL_33:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
    (const char *)v7,
    v16);
LABEL_36:
  utl::_OptionalData1<Container::Manager::Common::HotPatches,0>::~_OptionalData1<Container::Manager::Common::HotPatches,0>(v17);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18009d108  mov     [rsp-8+arg_10], rbx
0x18009d10d  push    rbp
0x18009d10e  push    rsi
0x18009d10f  push    rdi
0x18009d110  push    r12
0x18009d112  push    r13
0x18009d114  push    r14
0x18009d116  push    r15
0x18009d118  lea     rbp, [rsp-110h]
0x18009d120  sub     rsp, 210h
0x18009d127  mov     rax, cs:__security_cookie
0x18009d12e  xor     rax, rsp
0x18009d131  mov     [rbp+140h+var_40], rax
0x18009d138  mov     r15, rdx
0x18009d13b  mov     rsi, rcx
0x18009d13e  xor     r12d, r12d
0x18009d141  cmp     [rcx+341h], r12b
0x18009d148  jz      short loc_18009D189
0x18009d14a  mov     rax, [r15]
0x18009d14d  mov     [rax+8], r12d
0x18009d151  xor     r9d, r9d; Flags
0x18009d154  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18009d158  mov     rdx, [r15]; SRWLock
0x18009d15b  lea     rcx, [rsi+348h]; ConditionVariable
0x18009d162  call    cs:__imp_SleepConditionVariableSRW
0x18009d169  nop     dword ptr [rax+rax+00h]
0x18009d16e  call    cs:__imp_GetCurrentThreadId
0x18009d175  nop     dword ptr [rax+rax+00h]
0x18009d17a  mov     rcx, [r15]
0x18009d17d  mov     [rcx+8], eax
0x18009d180  cmp     [rsi+341h], r12b
0x18009d187  jnz     short loc_18009D14A
0x18009d189  mov     rcx, rsi; this
0x18009d18c  call    ?IsHotPatchUpdateRequired@ContainerObject@Details@Core@Manager@Container@@AEAA_NXZ; Container::Manager::Core::Details::ContainerObject::IsHotPatchUpdateRequired(void)
0x18009d191  test    al, al
0x18009d193  jnz     short loc_18009D19C
0x18009d195  xor     eax, eax
0x18009d197  jmp     loc_18009D4CA
0x18009d19c  mov     qword ptr [rsp+240h+var_210], r12
0x18009d1a1  xorps   xmm0, xmm0
0x18009d1a4  xor     eax, eax
0x18009d1a6  movups  [rsp+240h+var_208], xmm0
0x18009d1ab  movups  [rsp+240h+var_1F8], xmm0
0x18009d1b0  movups  [rsp+240h+var_1E8], xmm0
0x18009d1b5  mov     [rsp+240h+var_1D8], rax
0x18009d1ba  lea     r8, [rsp+240h+var_208]
0x18009d1bf  lea     rdx, [rsp+240h+var_210]
0x18009d1c4  mov     rcx, [rsi+578h]; SRWLock
0x18009d1cb  call    ?QueryHotPatches@SystemConfigurationManager@Details@Core@Manager@Container@@QEBAJAEAV?$optional@K@utl@@AEAV?$optional@UHotPatches@Common@Manager@Container@@@7@@Z; Container::Manager::Core::Details::SystemConfigurationManager::QueryHotPatches(utl::optional<ulong> &,utl::optional<Container::Manager::Common::HotPatches> &)
0x18009d1d0  mov     r14d, eax
0x18009d1d3  test    eax, eax
0x18009d1d5  jns     short loc_18009D1E4
0x18009d1d7  mov     r9d, eax
0x18009d1da  mov     edx, 2FBEh
0x18009d1df  jmp     loc_18009D497
0x18009d1e4  mov     rdi, qword ptr [rsp+240h+var_210]
0x18009d1e9  mov     rax, qword ptr [rsp+240h+var_208+8]
0x18009d1ee  cmp     qword ptr [rsp+240h+var_208], rax
0x18009d1f3  jz      loc_18009D4B3
0x18009d1f9  mov     byte ptr [rsi+341h], 1
0x18009d200  mov     rdx, r15
0x18009d203  mov     rcx, rsi
0x18009d206  call    ?AcquireAndWaitForContainerInfrastructureWakeReference@ContainerObject@Details@Core@Manager@Container@@AEAAXAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::AcquireAndWaitForContainerInfrastructureWakeReference(Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x18009d20b  cmp     byte ptr [rsp+240h+var_1D8], r12b
0x18009d210  jnz     short loc_18009D214
0x18009d212  int     2Ch; Windows NT - assertion failure
0x18009d214  mov     r8, r15
0x18009d217  lea     rdx, [rsp+240h+var_208]
0x18009d21c  mov     rcx, rsi; this
0x18009d21f  call    ?PrepareForHotPatching@ContainerObject@Details@Core@Manager@Container@@AEAAJAEAUHotPatches@Common@45@AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::PrepareForHotPatching(Container::Manager::Common::HotPatches &,Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x18009d224  mov     r14d, eax
0x18009d227  mov     rcx, [rbp+148h]; this
0x18009d22e  test    eax, eax
0x18009d230  jns     short loc_18009D24B
0x18009d232  mov     r9d, eax; char *
0x18009d235  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18009d23c  mov     edx, 2FCCh; void *
0x18009d241  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009d246  jmp     loc_18009D468
0x18009d24b  cmp     [rsi+33Ch], r12b
0x18009d252  jz      short loc_18009D25D
0x18009d254  mov     r14d, [rsi+338h]
0x18009d25b  jmp     short loc_18009D260
0x18009d25d  mov     r14d, r12d
0x18009d260  mov     rcx, [r15]; SRWLock
0x18009d263  test    rcx, rcx
0x18009d266  jz      short loc_18009D27B
0x18009d268  mov     [rcx+8], r12d
0x18009d26c  call    cs:__imp_ReleaseSRWLockExclusive
0x18009d273  nop     dword ptr [rax+rax+00h]
0x18009d278  mov     [r15], r12
0x18009d27b  mov     rbx, r12
0x18009d27e  mov     rcx, [rsi+518h]; this
0x18009d285  call    ?IsManualHotPatchMode@PolicyManager@Details@Core@Manager@Container@@QEBA_NXZ; Container::Manager::Core::Details::PolicyManager::IsManualHotPatchMode(void)
0x18009d28a  test    al, al
0x18009d28c  cmovz   rbx, rdi
0x18009d290  cmp     byte ptr [rsp+240h+var_210+4], r12b
0x18009d295  jnz     short loc_18009D299
0x18009d297  int     2Ch; Windows NT - assertion failure
0x18009d299  lea     rdx, aAgentupdatehot; "AgentUpdateHotPatches"
0x18009d2a0  lea     rcx, [rbp+140h+var_190]
0x18009d2a4  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18009d2a9  lea     r13, ??_7AgentUpdateHotPatches@CmTraceProvider@@6B@; const CmTraceProvider::AgentUpdateHotPatches::`vftable'
0x18009d2b0  mov     [rbp+140h+var_190], r13
0x18009d2b4  mov     r9d, edi; unsigned int
0x18009d2b7  mov     r8d, r14d; unsigned int
0x18009d2ba  mov     rdx, rsi; struct _GUID *
0x18009d2bd  lea     rcx, [rbp+140h+var_190]; this
0x18009d2c1  call    ?StartActivity@AgentUpdateHotPatches@CmTraceProvider@@QEAAXAEBU_GUID@@KK@Z; CmTraceProvider::AgentUpdateHotPatches::StartActivity(_GUID const &,ulong,ulong)
0x18009d2c6  nop
0x18009d2c7  mov     byte ptr [rsp+240h+var_1D0], r12b
0x18009d2cc  mov     [rbp+140h+var_1A0], r12b
0x18009d2d0  cmp     byte ptr [rsp+240h+var_1D8], r12b
0x18009d2d5  jz      short loc_18009D335
0x18009d2d7  mov     rax, qword ptr [rsp+240h+var_208]
0x18009d2dc  mov     [rsp+240h+var_1D0], rax
0x18009d2e1  mov     rax, qword ptr [rsp+240h+var_208+8]
0x18009d2e6  mov     [rsp+240h+var_1D0+8], rax
0x18009d2eb  mov     rax, qword ptr [rsp+240h+var_1F8]
0x18009d2f0  mov     qword ptr [rbp+140h+var_1C0], rax
0x18009d2f4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18009d2f8  mov     qword ptr [rsp+240h+var_208], rcx
0x18009d2fd  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18009d305  movdqu  [rsp+240h+var_208+8], xmm0
0x18009d30b  mov     rax, qword ptr [rsp+240h+var_1F8+8]
0x18009d310  mov     qword ptr [rbp+140h+var_1C0+8], rax
0x18009d314  mov     rax, qword ptr [rsp+240h+var_1E8]
0x18009d319  mov     qword ptr [rbp+140h+var_1B0], rax
0x18009d31d  mov     rax, qword ptr [rsp+240h+var_1E8+8]
0x18009d322  mov     qword ptr [rbp+140h+var_1B0+8], rax
0x18009d326  movdqu  [rsp+240h+var_1F8+8], xmm0
0x18009d32c  mov     qword ptr [rsp+240h+var_1E8+8], rcx
0x18009d331  mov     [rbp+140h+var_1A0], 1
0x18009d335  mov     r8, rbx
0x18009d338  lea     rdx, [rsp+240h+var_1D0]
0x18009d33d  mov     rcx, [rsi+4F8h]; this
0x18009d344  call    ?UpdateHotPatches@CmAgentConnection@Client@Agent@Manager@Container@@QEAAJV?$optional@UHotPatches@Common@Manager@Container@@@utl@@V?$optional@K@7@@Z; Container::Manager::Agent::Client::CmAgentConnection::UpdateHotPatches(utl::optional<Container::Manager::Common::HotPatches>,utl::optional<ulong>)
0x18009d349  mov     r14d, eax
0x18009d34c  test    eax, eax
0x18009d34e  jns     short loc_18009D36B
0x18009d350  mov     rcx, [rbp+148h]; this
0x18009d357  mov     r9d, eax; char *
0x18009d35a  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18009d361  mov     edx, 2FE5h; void *
0x18009d366  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009d36b  mov     edx, r14d
0x18009d36e  lea     rcx, [rbp+140h+var_190]
0x18009d372  call    ?Stop@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18009d377  test    r14d, r14d
0x18009d37a  js      short loc_18009D38D
0x18009d37c  mov     rax, [rsi+518h]
0x18009d383  mov     eax, [rax+60h]
0x18009d386  shr     eax, 13h
0x18009d389  test    al, 1
0x18009d38b  jz      short loc_18009D3F4
0x18009d38d  mov     rbx, [rsi+5A8h]
0x18009d394  xorps   xmm0, xmm0
0x18009d397  xor     eax, eax
0x18009d399  movups  xmmword ptr [rsp+240h+var_1D0], xmm0
0x18009d39e  movups  [rbp+140h+var_1C0], xmm0
0x18009d3a2  mov     qword ptr [rbp+140h+var_1B0], rax
0x18009d3a6  mov     rcx, [rsi+518h]; this
0x18009d3ad  call    ?IsSystemLoggerConfigured@PolicyManager@Details@Core@Manager@Container@@QEAA_NXZ; Container::Manager::Core::Details::PolicyManager::IsSystemLoggerConfigured(void)
0x18009d3b2  lea     rcx, [rsp+240h+var_1D0]
0x18009d3b7  mov     qword ptr [rsp+240h+var_220], rcx; int
0x18009d3bc  mov     r9b, al
0x18009d3bf  mov     r8, [rsi+4F8h]
0x18009d3c6  mov     rdx, [rsi+4E8h]; this
0x18009d3cd  mov     rcx, rbx; SRWLock
0x18009d3d0  call    ?CopyLogsFromComputeSystem@LogManager@Details@Core@Manager@Container@@QEAAJAEAVComputeSystem@Hcs@45@AEAVCmAgentConnection@Client@Agent@45@_NV?$optional@VPath@Csl@@@utl@@@Z; Container::Manager::Core::Details::LogManager::CopyLogsFromComputeSystem(Container::Manager::Hcs::ComputeSystem &,Container::Manager::Agent::Client::CmAgentConnection &,bool,utl::optional<Csl::Path>)
0x18009d3d5  test    eax, eax
0x18009d3d7  jns     short loc_18009D3F4
0x18009d3d9  mov     rcx, [rbp+148h]; this
0x18009d3e0  mov     r9d, eax; char *
0x18009d3e3  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18009d3ea  mov     edx, 2FF1h; void *
0x18009d3ef  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009d3f4  lea     rbx, [rsi+1C8h]
0x18009d3fb  mov     rcx, rbx; SRWLock
0x18009d3fe  call    cs:__imp_AcquireSRWLockExclusive
0x18009d405  nop     dword ptr [rax+rax+00h]
0x18009d40a  call    cs:__imp_GetCurrentThreadId
0x18009d411  nop     dword ptr [rax+rax+00h]
0x18009d416  mov     [rbx+8], eax
0x18009d419  lea     rax, [rbp+140h+var_198]
0x18009d41d  cmp     r15, rax
0x18009d420  jz      short loc_18009D43F
0x18009d422  mov     rcx, [r15]; SRWLock
0x18009d425  test    rcx, rcx
0x18009d428  jz      short loc_18009D43A
0x18009d42a  mov     [rcx+8], r12d
0x18009d42e  call    cs:__imp_ReleaseSRWLockExclusive
0x18009d435  nop     dword ptr [rax+rax+00h]
0x18009d43a  mov     [r15], rbx
0x18009d43d  jmp     short loc_18009D452
0x18009d43f  mov     [rbx+8], r12d
0x18009d443  mov     rcx, rbx; SRWLock
0x18009d446  call    cs:__imp_ReleaseSRWLockExclusive
0x18009d44d  nop     dword ptr [rax+rax+00h]
0x18009d452  mov     [rbp+140h+var_190], r13
0x18009d456  lea     rcx, [rbp+140h+var_190]
0x18009d45a  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18009d45f  lea     rcx, [rbp+140h+var_190]
0x18009d463  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18009d468  mov     rcx, rsi; this
0x18009d46b  call    ?ReleaseContainerInfrastructureWakeReference@ContainerObject@Details@Core@Manager@Container@@AEAAXXZ; Container::Manager::Core::Details::ContainerObject::ReleaseContainerInfrastructureWakeReference(void)
0x18009d470  mov     [rsi+341h], r12b
0x18009d477  lea     rcx, [rsi+348h]; ConditionVariable
0x18009d47e  call    cs:__imp_WakeConditionVariable
0x18009d485  nop     dword ptr [rax+rax+00h]
0x18009d48a  test    r14d, r14d
0x18009d48d  jns     short loc_18009D4AC
0x18009d48f  mov     r9d, r14d; char *
0x18009d492  mov     edx, 2FFFh; void *
0x18009d497  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18009d49e  mov     rcx, [rbp+148h]; this
0x18009d4a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d4aa  jmp     short loc_18009D4BD
0x18009d4ac  mov     byte ptr [rsi+340h], 1
0x18009d4b3  mov     [rsi+338h], rdi
0x18009d4ba  mov     r14d, r12d
0x18009d4bd  lea     rcx, [rsp+240h+var_208]
0x18009d4c2  call    ??1?$_OptionalData1@UHotPatches@Common@Manager@Container@@$0A@@utl@@QEAA@XZ; utl::_OptionalData1<Container::Manager::Common::HotPatches,0>::~_OptionalData1<Container::Manager::Common::HotPatches,0>(void)
0x18009d4c7  mov     eax, r14d
0x18009d4ca  mov     rcx, [rbp+140h+var_40]
0x18009d4d1  xor     rcx, rsp; StackCookie
0x18009d4d4  call    __security_check_cookie
0x18009d4d9  mov     rbx, [rsp+240h+arg_10]
0x18009d4e1  add     rsp, 210h
0x18009d4e8  pop     r15
0x18009d4ea  pop     r14
0x18009d4ec  pop     r13
0x18009d4ee  pop     r12
0x18009d4f0  pop     rdi
0x18009d4f1  pop     rsi
0x18009d4f2  pop     rbp
0x18009d4f3  retn
```
