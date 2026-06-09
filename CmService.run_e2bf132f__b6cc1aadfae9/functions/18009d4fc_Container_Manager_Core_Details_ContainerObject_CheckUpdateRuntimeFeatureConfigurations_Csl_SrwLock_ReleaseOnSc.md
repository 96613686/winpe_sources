# Container::Manager::Core::Details::ContainerObject::CheckUpdateRuntimeFeatureConfigurations(Csl::SrwLock::ReleaseOnScopeExit<0> &)

- ea: `0x18009d4fc`
- end: `0x18009d88b`
- name: `?CheckUpdateRuntimeFeatureConfigurations@ContainerObject@Details@Core@Manager@Container@@AEAAJAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z`
- size: `911`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `15`
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
- `0x1800471dc`
- `0x18009d4fc`
- `0x1800a3340`
- `0x1800a3388`
- `0x1800af11c`
- `0x1800fb3a4`
- `0x180110cc8`
- `0x1801921c0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18009d558`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18009d558`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x18009d7e3`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x18009d7e3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009d77a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009d77a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d5b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d7ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d7c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d5b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d7ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d7c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009d564`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009d786`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009d564`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009d786`

## string_xrefs

- `0x18009d602`: `AgentUpdateRuntimeFeatureConfigurations`
- `0x18009d692`: `onecore\base\gendrv\silos\clem\agent\client\lib\cmagentclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Container::Manager::Core::Details::ContainerObject::CheckUpdateRuntimeFeatureConfigurations(
        struct _GUID *a1,
        PSRWLOCK *a2)
{
  unsigned __int64 v4; // r15
  char Data1; // bl
  PSRWLOCK v6; // rcx
  int v7; // esi
  unsigned __int64 v8; // r12
  __int64 v9; // rcx
  utl::_RefCountBase *v10; // rdx
  utl::_RefCountBase *v11; // rbx
  utl::_RefCountBase *v12; // r15
  int v13; // eax
  RTL_SRWLOCK *v14; // rbx
  int v15; // eax
  PSRWLOCK v16; // rcx
  int v18; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  utl::_RefCountBase *v20[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v21; // [rsp+48h] [rbp-B8h] BYREF
  char v22; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v24; // [rsp+70h] [rbp-90h]
  __int64 v25; // [rsp+80h] [rbp-80h]
  _QWORD v26[42]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  for ( ; a1[50].Data4[0]; LODWORD((*a2)[1].Ptr) = GetCurrentThreadId() )
  {
    LODWORD((*a2)[1].Ptr) = 0;
    SleepConditionVariableSRW((PCONDITION_VARIABLE)&a1[51], *a2, 0xFFFFFFFF, 0);
  }
  if ( !Container::Manager::Core::Details::ContainerObject::IsRuntimeFeatureConfigurationsUpdateRequired((Container::Manager::Core::Details::ContainerObject *)a1) )
    return 0;
  a1[50].Data4[0] = 1;
  v4 = *(_QWORD *)a1[49].Data4;
  Data1 = a1[50].Data1;
  v6 = *a2;
  if ( *a2 )
  {
    LODWORD(v6[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v6);
    *a2 = 0;
  }
  v19 = 0;
  *(_OWORD *)v20 = 0;
  v7 = Container::Manager::Core::Details::SystemConfigurationManager::QueryRuntimeFeatureConfigurationsBuffer(
         *(PSRWLOCK *)a1[87].Data4,
         &v19,
         v20);
  v8 = v19;
  if ( v7 < 0 )
  {
    v12 = v20[1];
  }
  else
  {
    if ( !Data1 )
      __int2c();
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      v26,
      "AgentUpdateRuntimeFeatureConfigurations");
    v26[0] = &CmTraceProvider::AgentUpdateRuntimeFeatureConfigurations::`vftable';
    CmTraceProvider::AgentUpdateRuntimeFeatureConfigurations::StartActivity(
      (CmTraceProvider::AgentUpdateRuntimeFeatureConfigurations *)v26,
      a1,
      v4,
      v8);
    v9 = *(_QWORD *)a1[79].Data4;
    v10 = v20[0];
    v11 = v20[1];
    v12 = 0;
    v21 = 0;
    *(_QWORD *)&v21 = *(_QWORD *)v20[0];
    DWORD2(v21) = *((_DWORD *)v20[0] + 2) - *(_DWORD *)v20[0];
    v19 = (unsigned __int64)&v21;
    v20[0] = *(utl::_RefCountBase **)(v9 + 16);
    v13 = Container::Manager::Rpc::InvokeAsyncStubFunctionWithTimeout<void (*)(_RPC_ASYNC_STATE *,void *,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *),void *,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *>(
            *(_DWORD *)(v9 + 24),
            (__int64)v10,
            v20,
            &v19);
    v7 = v13;
    if ( v13 >= 0 )
    {
      if ( v11 )
        utl::_RefCountBase::_DecStrong(v11);
      v7 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2AB,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\client\\lib\\cmagentclient.cpp",
        (const char *)(unsigned int)v13,
        v18);
      if ( v11 )
        utl::_RefCountBase::_DecStrong(v11);
    }
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v26,
      (unsigned int)v7);
    if ( v7 < 0 || (*(_DWORD *)(*(_QWORD *)a1[81].Data4 + 96LL) & 0x80000) != 0 )
    {
      v14 = *(RTL_SRWLOCK **)a1[90].Data4;
      *(_OWORD *)v23 = 0;
      v24 = 0;
      v25 = 0;
      Container::Manager::Core::Details::PolicyManager::IsSystemLoggerConfigured(*(Container::Manager::Core::Details::PolicyManager **)a1[81].Data4);
      v15 = Container::Manager::Core::Details::LogManager::CopyLogsFromComputeSystem(
              v14,
              *(Container::Manager::Hcs::ComputeSystem **)a1[78].Data4,
              (__int64)v23);
      if ( v15 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2EED,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
          (const char *)(unsigned int)v15,
          v18);
    }
    v26[0] = &CmTraceProvider::AgentUpdateRuntimeFeatureConfigurations::`vftable';
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v26);
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v26);
  }
  AcquireSRWLockExclusive((PSRWLOCK)a1[28].Data4);
  a1[29].Data1 = GetCurrentThreadId();
  if ( a2 == (PSRWLOCK *)&v22 )
  {
    a1[29].Data1 = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)a1[28].Data4);
  }
  else
  {
    v16 = *a2;
    if ( *a2 )
    {
      LODWORD(v16[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v16);
    }
    *a2 = (PSRWLOCK)a1[28].Data4;
  }
  a1[50].Data4[0] = 0;
  WakeConditionVariable((PCONDITION_VARIABLE)&a1[51]);
  if ( v7 >= 0 )
  {
    *(_QWORD *)a1[49].Data4 = v8;
    LOBYTE(a1[50].Data1) = 1;
    *(unsigned int *)((char *)&a1[50].Data1 + 1) = *(_DWORD *)((char *)&v21 + 9);
    *(unsigned __int16 *)((char *)&a1[50].Data2 + 1) = *(_WORD *)((char *)&v21 + 13);
    HIBYTE(a1[50].Data3) = HIBYTE(v21);
    if ( v12 )
      utl::_RefCountBase::_DecStrong(v12);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2EF9,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
    (const char *)(unsigned int)v7,
    v18);
  if ( v12 )
    utl::_RefCountBase::_DecStrong(v12);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18009d4fc  mov     [rsp-8+arg_10], rbx
0x18009d501  mov     [rsp-8+arg_18], rsi
0x18009d506  push    rbp
0x18009d507  push    rdi
0x18009d508  push    r12
0x18009d50a  push    r14
0x18009d50c  push    r15
0x18009d50e  lea     rbp, [rsp-0F0h]
0x18009d516  sub     rsp, 1F0h
0x18009d51d  mov     rax, cs:__security_cookie
0x18009d524  xor     rax, rsp
0x18009d527  mov     [rbp+110h+var_30], rax
0x18009d52e  mov     r14, rdx
0x18009d531  mov     rdi, rcx
0x18009d534  cmp     byte ptr [rcx+328h], 0
0x18009d53b  jz      short loc_18009D57F
0x18009d53d  mov     rax, [r14]
0x18009d540  mov     dword ptr [rax+8], 0
0x18009d547  xor     r9d, r9d; Flags
0x18009d54a  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18009d54e  mov     rdx, [r14]; SRWLock
0x18009d551  lea     rcx, [rdi+330h]; ConditionVariable
0x18009d558  call    cs:__imp_SleepConditionVariableSRW
0x18009d55f  nop     dword ptr [rax+rax+00h]
0x18009d564  call    cs:__imp_GetCurrentThreadId
0x18009d56b  nop     dword ptr [rax+rax+00h]
0x18009d570  mov     rcx, [r14]
0x18009d573  mov     [rcx+8], eax
0x18009d576  cmp     byte ptr [rdi+328h], 0
0x18009d57d  jnz     short loc_18009D53D
0x18009d57f  mov     rcx, rdi; this
0x18009d582  call    ?IsRuntimeFeatureConfigurationsUpdateRequired@ContainerObject@Details@Core@Manager@Container@@AEAA_NXZ; Container::Manager::Core::Details::ContainerObject::IsRuntimeFeatureConfigurationsUpdateRequired(void)
0x18009d587  test    al, al
0x18009d589  jz      loc_18009D85D
0x18009d58f  mov     byte ptr [rdi+328h], 1
0x18009d596  mov     r15, [rdi+318h]
0x18009d59d  mov     bl, [rdi+320h]
0x18009d5a3  mov     rcx, [r14]; SRWLock
0x18009d5a6  test    rcx, rcx
0x18009d5a9  jz      short loc_18009D5C5
0x18009d5ab  mov     dword ptr [rcx+8], 0
0x18009d5b2  call    cs:__imp_ReleaseSRWLockExclusive
0x18009d5b9  nop     dword ptr [rax+rax+00h]
0x18009d5be  mov     qword ptr [r14], 0
0x18009d5c5  mov     [rsp+210h+var_1E0], 0
0x18009d5ce  xorps   xmm0, xmm0
0x18009d5d1  movdqu  xmmword ptr [rsp+210h+var_1D8], xmm0
0x18009d5d7  lea     r8, [rsp+210h+var_1D8]
0x18009d5dc  lea     rdx, [rsp+210h+var_1E0]
0x18009d5e1  mov     rcx, [rdi+578h]; SRWLock
0x18009d5e8  call    ?QueryRuntimeFeatureConfigurationsBuffer@SystemConfigurationManager@Details@Core@Manager@Container@@QEAAJAEA_KAEAV?$shared_ptr@V?$vector@EV?$allocator@E@utl@@@utl@@@utl@@@Z; Container::Manager::Core::Details::SystemConfigurationManager::QueryRuntimeFeatureConfigurationsBuffer(unsigned __int64 &,utl::shared_ptr<utl::vector<uchar,utl::allocator<uchar>>> &)
0x18009d5ed  mov     esi, eax
0x18009d5ef  mov     r12, [rsp+210h+var_1E0]
0x18009d5f4  test    eax, eax
0x18009d5f6  js      loc_18009D76B
0x18009d5fc  test    bl, bl
0x18009d5fe  jnz     short loc_18009D602
0x18009d600  int     2Ch; Windows NT - assertion failure
0x18009d602  lea     rdx, aAgentupdaterun; "AgentUpdateRuntimeFeatureConfigurations"
0x18009d609  lea     rcx, [rbp+110h+var_180]
0x18009d60d  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18009d612  lea     rax, ??_7AgentUpdateRuntimeFeatureConfigurations@CmTraceProvider@@6B@; const CmTraceProvider::AgentUpdateRuntimeFeatureConfigurations::`vftable'
0x18009d619  mov     [rbp+110h+var_180], rax
0x18009d61d  mov     r9, r12; unsigned __int64
0x18009d620  mov     r8, r15; unsigned __int64
0x18009d623  mov     rdx, rdi; struct _GUID *
0x18009d626  lea     rcx, [rbp+110h+var_180]; this
0x18009d62a  call    ?StartActivity@AgentUpdateRuntimeFeatureConfigurations@CmTraceProvider@@QEAAXAEBU_GUID@@_K1@Z; CmTraceProvider::AgentUpdateRuntimeFeatureConfigurations::StartActivity(_GUID const &,unsigned __int64,unsigned __int64)
0x18009d62f  nop
0x18009d630  mov     rcx, [rdi+4F8h]
0x18009d637  mov     rdx, [rsp+210h+var_1D8]
0x18009d63c  mov     rbx, [rsp+210h+var_1D8+8]
0x18009d641  xor     r15d, r15d
0x18009d644  xorps   xmm0, xmm0
0x18009d647  movups  [rsp+210h+var_1C8], xmm0
0x18009d64c  mov     rax, [rdx]
0x18009d64f  mov     qword ptr [rsp+210h+var_1C8], rax
0x18009d654  mov     eax, [rdx+8]
0x18009d657  sub     eax, [rdx]
0x18009d659  mov     dword ptr [rsp+210h+var_1C8+8], eax
0x18009d65d  lea     rax, [rsp+210h+var_1C8]
0x18009d662  mov     [rsp+210h+var_1E0], rax
0x18009d667  mov     rax, [rcx+10h]
0x18009d66b  mov     [rsp+210h+var_1D8], rax
0x18009d670  lea     r9, [rsp+210h+var_1E0]
0x18009d675  lea     r8, [rsp+210h+var_1D8]
0x18009d67a  mov     ecx, [rcx+18h]; dwMilliseconds
0x18009d67d  call    ??$InvokeAsyncStubFunctionWithTimeout@P6AXPEAU_RPC_ASYNC_STATE@@PEAXPEAU_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION@@@ZPEAXPEAU2@@Rpc@Manager@Container@@YAJKP6AXPEAU_RPC_ASYNC_STATE@@PEAXPEAU_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION@@@Z$$QEAPEAX$$QEAPEAU4@@Z; Container::Manager::Rpc::InvokeAsyncStubFunctionWithTimeout<void (*)(_RPC_ASYNC_STATE *,void *,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *),void *,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *>(ulong,void (*)(_RPC_ASYNC_STATE *,void *,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *),void * &&,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION * &&)
0x18009d682  mov     esi, eax
0x18009d684  test    eax, eax
0x18009d686  jns     short loc_18009D6B4
0x18009d688  mov     rcx, [rbp+118h]; this
0x18009d68f  mov     r9d, eax; char *
0x18009d692  lea     r8, aOnecoreBaseGen_24; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18009d699  mov     edx, 2ABh; void *
0x18009d69e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d6a3  nop
0x18009d6a4  test    rbx, rbx
0x18009d6a7  jz      short loc_18009D6B2
0x18009d6a9  mov     rcx, rbx; this
0x18009d6ac  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18009d6b1  nop
0x18009d6b2  jmp     short loc_18009D6C4
0x18009d6b4  test    rbx, rbx
0x18009d6b7  jz      short loc_18009D6C2
0x18009d6b9  mov     rcx, rbx; this
0x18009d6bc  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18009d6c1  nop
0x18009d6c2  xor     esi, esi
0x18009d6c4  mov     edx, esi
0x18009d6c6  lea     rcx, [rbp+110h+var_180]
0x18009d6ca  call    ?Stop@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18009d6cf  test    esi, esi
0x18009d6d1  js      short loc_18009D6E4
0x18009d6d3  mov     rax, [rdi+518h]
0x18009d6da  mov     eax, [rax+60h]
0x18009d6dd  shr     eax, 13h
0x18009d6e0  test    al, 1
0x18009d6e2  jz      short loc_18009D74C
0x18009d6e4  mov     rbx, [rdi+5A8h]
0x18009d6eb  xorps   xmm0, xmm0
0x18009d6ee  xor     eax, eax
0x18009d6f0  movups  xmmword ptr [rsp+210h+var_1B0], xmm0
0x18009d6f5  movups  [rsp+210h+var_1A0], xmm0
0x18009d6fa  mov     [rbp+110h+var_190], rax
0x18009d6fe  mov     rcx, [rdi+518h]; this
0x18009d705  call    ?IsSystemLoggerConfigured@PolicyManager@Details@Core@Manager@Container@@QEAA_NXZ; Container::Manager::Core::Details::PolicyManager::IsSystemLoggerConfigured(void)
0x18009d70a  lea     rcx, [rsp+210h+var_1B0]
0x18009d70f  mov     qword ptr [rsp+210h+var_1F0], rcx; int
0x18009d714  mov     r9b, al
0x18009d717  mov     r8, [rdi+4F8h]
0x18009d71e  mov     rdx, [rdi+4E8h]; this
0x18009d725  mov     rcx, rbx; SRWLock
0x18009d728  call    ?CopyLogsFromComputeSystem@LogManager@Details@Core@Manager@Container@@QEAAJAEAVComputeSystem@Hcs@45@AEAVCmAgentConnection@Client@Agent@45@_NV?$optional@VPath@Csl@@@utl@@@Z; Container::Manager::Core::Details::LogManager::CopyLogsFromComputeSystem(Container::Manager::Hcs::ComputeSystem &,Container::Manager::Agent::Client::CmAgentConnection &,bool,utl::optional<Csl::Path>)
0x18009d72d  mov     rcx, [rbp+118h]; this
0x18009d734  test    eax, eax
0x18009d736  jns     short loc_18009D74C
0x18009d738  mov     r9d, eax; char *
0x18009d73b  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18009d742  mov     edx, 2EEDh; void *
0x18009d747  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009d74c  lea     rax, ??_7AgentUpdateRuntimeFeatureConfigurations@CmTraceProvider@@6B@; const CmTraceProvider::AgentUpdateRuntimeFeatureConfigurations::`vftable'
0x18009d753  mov     [rbp+110h+var_180], rax
0x18009d757  lea     rcx, [rbp+110h+var_180]
0x18009d75b  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18009d760  lea     rcx, [rbp+110h+var_180]
0x18009d764  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18009d769  jmp     short loc_18009D770
0x18009d76b  mov     r15, [rsp+210h+var_1D8+8]
0x18009d770  lea     rbx, [rdi+1C8h]
0x18009d777  mov     rcx, rbx; SRWLock
0x18009d77a  call    cs:__imp_AcquireSRWLockExclusive
0x18009d781  nop     dword ptr [rax+rax+00h]
0x18009d786  call    cs:__imp_GetCurrentThreadId
0x18009d78d  nop     dword ptr [rax+rax+00h]
0x18009d792  mov     [rbx+8], eax
0x18009d795  lea     rax, [rsp+210h+var_1B8]
0x18009d79a  cmp     r14, rax
0x18009d79d  jz      short loc_18009D7BF
0x18009d79f  mov     rcx, [r14]; SRWLock
0x18009d7a2  test    rcx, rcx
0x18009d7a5  jz      short loc_18009D7BA
0x18009d7a7  mov     dword ptr [rcx+8], 0
0x18009d7ae  call    cs:__imp_ReleaseSRWLockExclusive
0x18009d7b5  nop     dword ptr [rax+rax+00h]
0x18009d7ba  mov     [r14], rbx
0x18009d7bd  jmp     short loc_18009D7D5
0x18009d7bf  mov     dword ptr [rbx+8], 0
0x18009d7c6  mov     rcx, rbx; SRWLock
0x18009d7c9  call    cs:__imp_ReleaseSRWLockExclusive
0x18009d7d0  nop     dword ptr [rax+rax+00h]
0x18009d7d5  mov     byte ptr [rdi+328h], 0
0x18009d7dc  lea     rcx, [rdi+330h]; ConditionVariable
0x18009d7e3  call    cs:__imp_WakeConditionVariable
0x18009d7ea  nop     dword ptr [rax+rax+00h]
0x18009d7ef  test    esi, esi
0x18009d7f1  jns     short loc_18009D821
0x18009d7f3  mov     rcx, [rbp+118h]; this
0x18009d7fa  mov     r9d, esi; char *
0x18009d7fd  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18009d804  mov     edx, 2EF9h; void *
0x18009d809  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d80e  nop
0x18009d80f  test    r15, r15
0x18009d812  jz      short loc_18009D81D
0x18009d814  mov     rcx, r15; this
0x18009d817  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18009d81c  nop
0x18009d81d  mov     eax, esi
0x18009d81f  jmp     short loc_18009D85F
0x18009d821  mov     [rdi+318h], r12
0x18009d828  mov     byte ptr [rdi+320h], 1
0x18009d82f  mov     eax, dword ptr [rsp+210h+var_1C8+9]
0x18009d833  mov     [rdi+321h], eax
0x18009d839  movzx   eax, word ptr [rsp+210h+var_1C8+0Dh]
0x18009d83e  mov     [rdi+325h], ax
0x18009d845  mov     al, byte ptr [rsp+210h+var_1C8+0Fh]
0x18009d849  mov     [rdi+327h], al
0x18009d84f  test    r15, r15
0x18009d852  jz      short loc_18009D85D
0x18009d854  mov     rcx, r15; this
0x18009d857  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18009d85c  nop
0x18009d85d  xor     eax, eax
0x18009d85f  mov     rcx, [rbp+110h+var_30]
0x18009d866  xor     rcx, rsp; StackCookie
0x18009d869  call    __security_check_cookie
0x18009d86e  lea     r11, [rsp+210h+var_20]
0x18009d876  mov     rbx, [r11+40h]
0x18009d87a  mov     rsi, [r11+48h]
0x18009d87e  mov     rsp, r11
0x18009d881  pop     r15
0x18009d883  pop     r14
0x18009d885  pop     r12
0x18009d887  pop     rdi
0x18009d888  pop     rbp
0x18009d889  retn
```
