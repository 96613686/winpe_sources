# VirtualMachine::Teardown(void)

- ea: `0x14004fa0c`
- end: `0x140050027`
- name: `?Teardown@VirtualMachine@@QEAAXXZ`
- size: `1563`
- prototype: `void __fastcall(VirtualMachine *__hidden this)`
- caller_count: `1`
- callee_count: `37`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14004f5a8`

## callees

- `0x140021fb8`
- `0x140031ad8`
- `0x14004fa0c`
- `0x140050030`
- `0x140055af0`
- `0x140055de0`
- `0x14008705c`
- `0x140094acc`
- `0x140094b7c`
- `0x1400997f4`
- `0x1400c6e5c`
- `0x1400c6f00`
- `0x1400c6f58`
- `0x1400d436c`
- `0x1400d6d84`
- `0x1400e793c`
- `0x1400e9020`
- `0x140132940`
- `0x1401335fc`
- `0x140156d80`
- `0x140156ddc`
- `0x140156e38`
- `0x140156e94`
- `0x140156ef0`
- `0x140156f4c`
- `0x140156fa8`
- `0x140157004`
- `0x140157060`
- `0x1401570bc`
- `0x140157118`
- `0x140157174`
- `0x1401571d0`
- `0x14016b858`
- `0x140172a7c`
- `0x14017c17c`
- `0x14017ca34`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14004fbf6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14004fbf6`
- `WS2_32!__imp_WSACleanup` at `0x14004fc0b`
- `WS2_32!__imp_WSACleanup` at `0x14004fc0b`
- `vid!VidSchedulerAssistReset` at `0x14004fb59`
- `vid!VidSchedulerAssistReset` at `0x14004fb59`
- `vid!VidEpfReset` at `0x14004fb23`
- `vid!VidEpfReset` at `0x14004fb23`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall VirtualMachine::Teardown(VirtualMachine *this)
{
  __int128 v2; // xmm0
  _QWORD *v3; // r14
  __int64 v4; // rcx
  __int64 v5; // rdi
  const char *v6; // r9
  const char *v7; // r9
  __int64 v8; // rcx
  __int64 v9; // rdi
  struct _TP_WAIT *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  WorkerCpuidHandler *v14; // rcx
  WorkerExceptionHandler *v15; // rcx
  MemoryManager *v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  Vml::VmSharableObject *v28; // rcx
  Vml::VmSharableObject *v29; // rcx
  __int128 v30; // [rsp+28h] [rbp-D8h] BYREF
  void **v31; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v32[264]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+150h] [rbp+50h]
  _BYTE v34[8]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v35[48]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  v30 = *((_OWORD *)this + 71);
  memset_0(&v31, 0, 0x150u);
  wil::ActivityBase<VmWorkerTrace,0,16,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v31);
  v31 = &VmWorkerTrace::VmTeardown::`vftable';
  VmWorkerTrace::VmTeardown::StartActivity((VmWorkerTrace::VmTeardown *)&v31);
  if ( v33 == -8 )
    v2 = 0;
  else
    v2 = *(_OWORD *)(v33 + 8);
  *((_OWORD *)this + 164) = v2;
  AsyncTimer::DisableAndWait((VirtualMachine *)((char *)this + 1712));
  VmWorkerTrace::VmTeardown::TeardownTimerWait<_GUID &>(&v31, &v30);
  VirtualMachine::TeardownPartition(this, 0);
  VmWorkerTrace::VmTeardown::TeardownPartition<_GUID &>(&v31, &v30);
  v3 = (_QWORD *)((char *)this + 1024);
  v4 = *((_QWORD *)this + 128);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v4 + 8) + 88LL))(v4 + 8);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 320LL))(*v3);
    if ( (v5 & 0x20000) != 0 && !(unsigned int)VidEpfReset(*((_QWORD *)this + 122)) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x972,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\virtualmachine.cpp",
        v6);
    if ( (v5 & 0x100000) != 0 && !(unsigned int)VidSchedulerAssistReset(*((_QWORD *)this + 122)) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x977,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\virtualmachine.cpp",
        v7);
    v8 = *((_QWORD *)this + 130);
    if ( v8 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v8 + 184LL))(v8) && *((_DWORD *)this + 317) != 3 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)(*v3 + 24LL) + 24LL))(*v3 + 24LL, 524544, 0);
  }
  VirtualMachine::TeardownMotherboard(this);
  VmWorkerTrace::VmTeardown::TeardownMotherboard<_GUID &>(&v31, &v30);
  v9 = *((_QWORD *)this + 131);
  if ( v9 )
  {
    v10 = *(struct _TP_WAIT **)(v9 + 224);
    if ( v10 )
      CloseThreadpoolWait(v10);
    if ( *(_DWORD *)(v9 + 208) )
      WSACleanup();
    Vml::VmReferencePtr<WorkerConfiguration,Vml::VmUserReferenceTraits>::Reset((char *)this + 1048, 0);
  }
  VmWorkerTrace::VmTeardown::TeardownMigrationManager<_GUID &>(&v31, &v30);
  v11 = *((_QWORD *)this + 323);
  *((_QWORD *)this + 323) = 0;
  if ( v11 )
    Vml::VmSharableObject::DecrementUserCount((Vml::VmSharableObject *)(v11 + 8 + *(int *)(*(_QWORD *)(v11 + 8) + 4LL)));
  *((_QWORD *)this + 179) = 0;
  v12 = *((_QWORD *)this + 178);
  *((_QWORD *)this + 178) = 0;
  if ( v12 )
    Vml::VmSharableObject::DecrementUserCount((Vml::VmSharableObject *)(v12 + 8));
  v13 = *((_QWORD *)this + 125);
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(_QWORD *)(v13 + 152) + 8LL) + 64LL))(
      *(_QWORD *)(v13 + 152) + 8LL,
      *(_QWORD *)(v13 + 192));
    Vml::VmSharableObject::DecrementUserCount((Vml::VmSharableObject *)(*((_QWORD *)this + 125)
                                                                      + 8LL
                                                                      + *(int *)(*(_QWORD *)(*((_QWORD *)this + 125)
                                                                                           + 8LL)
                                                                               + 4LL)));
    *((_QWORD *)this + 125) = 0;
  }
  v14 = (WorkerCpuidHandler *)*((_QWORD *)this + 126);
  if ( v14 )
  {
    WorkerCpuidHandler::TeardownRegisteredResults(v14);
    Vml::VmSharableObject::DecrementUserCount((Vml::VmSharableObject *)(*((_QWORD *)this + 126)
                                                                      + 8LL
                                                                      + *(int *)(*(_QWORD *)(*((_QWORD *)this + 126)
                                                                                           + 8LL)
                                                                               + 4LL)));
    *((_QWORD *)this + 126) = 0;
  }
  v15 = (WorkerExceptionHandler *)*((_QWORD *)this + 127);
  if ( v15 )
  {
    WorkerExceptionHandler::Teardown(v15);
    Vml::VmSharableObject::DecrementUserCount((Vml::VmSharableObject *)(*((_QWORD *)this + 127)
                                                                      + 8LL
                                                                      + *(int *)(*(_QWORD *)(*((_QWORD *)this + 127)
                                                                                           + 8LL)
                                                                               + 4LL)));
    *((_QWORD *)this + 127) = 0;
  }
  VmWorkerTrace::VmTeardown::TeardownInternalInterceptHandler<_GUID &>(&v31, &v30);
  v16 = (MemoryManager *)*((_QWORD *)this + 124);
  if ( v16 )
  {
    MemoryManager::Teardown(v16);
    *((_QWORD *)this + 124) = 0;
  }
  v17 = *((_QWORD *)this + 130);
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 264LL))(v17);
    Vml::VmReferencePtr<VndCompletionThread,Vml::VmUserReferenceTraits>::Reset((char *)this + 1040, 0);
  }
  VmWorkerTrace::VmTeardown::TeardownProcessorManager<_GUID &>(&v31, &v30);
  if ( *v3 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 88LL))(*v3);
    Vml::VmReferencePtr<IVidPartitionManager,Vml::VmUserReferenceTraits>::Reset((char *)this + 1024, 0);
  }
  v18 = *((_QWORD *)this + 132);
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 32LL))(v18);
    v19 = *((_QWORD *)this + 132);
    *((_QWORD *)this + 132) = 0;
    if ( v19 )
      Vml::VmSharableObject::DecrementUserCount((Vml::VmSharableObject *)(v19 + 8 + *(int *)(*(_QWORD *)(v19 + 8) + 4LL)));
  }
  VmWorkerTrace::VmTeardown::TeardownSavedStateFileManager<_GUID &>(&v31, &v30);
  Vml::VmReferencePtr<IMetricManager,Vml::VmUserReferenceTraits>::Reset((char *)this + 1064);
  VmWorkerTrace::VmTeardown::TeardownMetricManager<_GUID &>(&v31, &v30);
  v20 = *((_QWORD *)this + 129);
  *((_QWORD *)this + 129) = 0;
  if ( v20 )
    Vml::VmSharableObject::DecrementUserCount((Vml::VmSharableObject *)(v20 + 8 + *(int *)(*(_QWORD *)(v20 + 8) + 4LL)));
  VmWorkerTrace::VmTeardown::TeardownNumaManager<_GUID &>(&v31, &v30);
  v21 = *((_QWORD *)this + 134);
  *((_QWORD *)this + 134) = 0;
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  VmWorkerTrace::VmTeardown::TeardownSecurityManager<_GUID &>(&v31, &v30);
  v22 = *((_QWORD *)this + 181);
  *((_QWORD *)this + 181) = 0;
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  v23 = *((_QWORD *)this + 290);
  *((_QWORD *)this + 290) = 0;
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  v24 = *((_QWORD *)this + 291);
  *((_QWORD *)this + 291) = 0;
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  v25 = *((_QWORD *)this + 183);
  *((_QWORD *)this + 183) = 0;
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  v26 = *((_QWORD *)this + 184);
  *((_QWORD *)this + 184) = 0;
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  v27 = *((_QWORD *)this + 185);
  *((_QWORD *)this + 185) = 0;
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  VmWorkerTrace::VmTeardown::TeardownRdpAndMonitorDevice<_GUID &>(&v31, &v30);
  v28 = (Vml::VmSharableObject *)*((_QWORD *)this + 180);
  if ( v28 )
  {
    Vml::VmSharableObject::DecrementUserCount(v28);
    *((_QWORD *)this + 180) = 0;
  }
  VmWorkerTrace::VmTeardown::TeardownAsyncTimerlist<_GUID &>(&v31, &v30);
  v29 = (Vml::VmSharableObject *)*((_QWORD *)this + 177);
  *((_QWORD *)this + 177) = 0;
  if ( v29 )
    Vml::VmSharableObject::DecrementUserCount(v29);
  VmWorkerTrace::VmTeardown::TeardownWorkerConfig<_GUID &>(&v31, &v30);
  wil::ActivityBase<VmWorkerTrace,0,16,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v31, 0);
  if ( this != (VirtualMachine *)-2624LL )
    VirtualMachine::ResetActivityId((struct _GUID *)this + 164);
  v31 = &VmWorkerTrace::VmTeardown::`vftable';
  wil::ActivityBase<VmWorkerTrace,0,16,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v31);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v35);
  wil::details::shared_object<wil::ActivityBase<VmWorkerTrace,0,16,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<VmWorkerTrace,_TlgReflectorTag_Param0IsProviderType>>::reset(v34);
  wil::ActivityBase<VmWorkerTrace,0,16,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<VmWorkerTrace,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<VmWorkerTrace,_TlgReflectorTag_Param0IsProviderType>(v32);
}

```

## disassembly

```asm
0x14004fa0c  push    rbp
0x14004fa0e  push    rbx
0x14004fa0f  push    rsi
0x14004fa10  push    rdi
0x14004fa11  push    r12
0x14004fa13  push    r13
0x14004fa15  push    r14
0x14004fa17  push    r15
0x14004fa19  lea     rbp, [rsp-0A8h]
0x14004fa21  sub     rsp, 1A8h
0x14004fa28  mov     rax, cs:__security_cookie
0x14004fa2f  xor     rax, rsp
0x14004fa32  mov     [rbp+0E0h+var_50], rax
0x14004fa39  mov     rbx, rcx
0x14004fa3c  movups  xmm0, xmmword ptr [rcx+470h]
0x14004fa43  movdqu  [rsp+1E0h+var_1B8], xmm0
0x14004fa49  xor     edx, edx; Val
0x14004fa4b  mov     r8d, 150h; Size
0x14004fa51  lea     rcx, [rsp+1E0h+var_1A0]; void *
0x14004fa56  call    memset_0
0x14004fa5b  lea     rdx, aVmteardown; "VmTeardown"
0x14004fa62  lea     rcx, [rsp+1E0h+var_1A0]; struct wil::details::IFailureCallback *
0x14004fa67  call    ??0?$ActivityBase@VVmWorkerTrace@@$0A@$0BA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<VmWorkerTrace,0,16,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14004fa6c  lea     r13, ??_7VmTeardown@VmWorkerTrace@@6B@; const VmWorkerTrace::VmTeardown::`vftable'
0x14004fa73  mov     [rsp+1E0h+var_1A0], r13
0x14004fa78  lea     rcx, [rsp+1E0h+var_1A0]; this
0x14004fa7d  call    ?StartActivity@VmTeardown@VmWorkerTrace@@QEAAXXZ; VmWorkerTrace::VmTeardown::StartActivity(void)
0x14004fa82  nop
0x14004fa83  mov     rax, [rbp+0E0h+var_90]
0x14004fa87  lea     r15, [rbx+0A40h]
0x14004fa8e  xor     r12d, r12d
0x14004fa91  add     rax, 8
0x14004fa95  jz      short loc_14004FA9C
0x14004fa97  movups  xmm0, xmmword ptr [rax]
0x14004fa9a  jmp     short loc_14004FA9F
0x14004fa9c  xorps   xmm0, xmm0
0x14004fa9f  movdqu  xmmword ptr [r15], xmm0
0x14004faa4  mov     [rsp+1E0h+var_1C0], r15
0x14004faa9  lea     rcx, [rbx+6B0h]; this
0x14004fab0  call    ?DisableAndWait@AsyncTimer@@QEAAHXZ; AsyncTimer::DisableAndWait(void)
0x14004fab5  lea     rdx, [rsp+1E0h+var_1B8]
0x14004faba  lea     rcx, [rsp+1E0h+var_1A0]
0x14004fabf  call    ??$TeardownTimerWait@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownTimerWait<_GUID &>(_GUID &)
0x14004fac4  xor     edx, edx; int
0x14004fac6  mov     rcx, rbx; this
0x14004fac9  call    ?TeardownPartition@VirtualMachine@@AEAAXH@Z; VirtualMachine::TeardownPartition(int)
0x14004face  lea     rdx, [rsp+1E0h+var_1B8]
0x14004fad3  lea     rcx, [rsp+1E0h+var_1A0]
0x14004fad8  call    ??$TeardownPartition@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownPartition<_GUID &>(_GUID &)
0x14004fadd  lea     r14, [rbx+400h]
0x14004fae4  mov     rcx, [r14]
0x14004fae7  test    rcx, rcx
0x14004faea  jz      loc_14004FBC4
0x14004faf0  add     rcx, 8
0x14004faf4  mov     rax, [rcx]
0x14004faf7  mov     rax, [rax+58h]
0x14004fafb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fb00  mov     rcx, [r14]
0x14004fb03  mov     rax, [rcx]
0x14004fb06  mov     rax, [rax+140h]
0x14004fb0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fb12  mov     rdi, rax
0x14004fb15  bt      rax, 11h
0x14004fb1a  jnb     short loc_14004FB4B
0x14004fb1c  mov     rcx, [rbx+3D0h]
0x14004fb23  call    cs:__imp_VidEpfReset
0x14004fb2a  nop     dword ptr [rax+rax+00h]
0x14004fb2f  mov     rcx, [rbp+0E8h]; this
0x14004fb36  test    eax, eax
0x14004fb38  jnz     short loc_14004FB4B
0x14004fb3a  lea     r8, aOnecoreVmWorke_77; "onecore\\vm\\worker\\wpcore\\virtualmac"...
0x14004fb41  mov     edx, 972h; void *
0x14004fb46  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x14004fb4b  bt      rdi, 14h
0x14004fb50  jnb     short loc_14004FB81
0x14004fb52  mov     rcx, [rbx+3D0h]
0x14004fb59  call    cs:__imp_VidSchedulerAssistReset
0x14004fb60  nop     dword ptr [rax+rax+00h]
0x14004fb65  mov     rcx, [rbp+0E8h]; this
0x14004fb6c  test    eax, eax
0x14004fb6e  jnz     short loc_14004FB81
0x14004fb70  lea     r8, aOnecoreVmWorke_77; "onecore\\vm\\worker\\wpcore\\virtualmac"...
0x14004fb77  mov     edx, 977h; void *
0x14004fb7c  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x14004fb81  mov     rcx, [rbx+410h]
0x14004fb88  test    rcx, rcx
0x14004fb8b  jz      short loc_14004FBC4
0x14004fb8d  mov     rax, [rcx]
0x14004fb90  mov     rax, [rax+0B8h]
0x14004fb97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fb9c  test    eax, eax
0x14004fb9e  jz      short loc_14004FBC4
0x14004fba0  cmp     dword ptr [rbx+4F4h], 3
0x14004fba7  jz      short loc_14004FBC4
0x14004fba9  mov     rcx, [r14]
0x14004fbac  add     rcx, 18h
0x14004fbb0  mov     rax, [rcx]
0x14004fbb3  xor     r8d, r8d
0x14004fbb6  mov     edx, 80100h
0x14004fbbb  mov     rax, [rax+18h]
0x14004fbbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fbc4  mov     rcx, rbx; this
0x14004fbc7  call    ?TeardownMotherboard@VirtualMachine@@QEAAXXZ; VirtualMachine::TeardownMotherboard(void)
0x14004fbcc  lea     rdx, [rsp+1E0h+var_1B8]
0x14004fbd1  lea     rcx, [rsp+1E0h+var_1A0]
0x14004fbd6  call    ??$TeardownMotherboard@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownMotherboard<_GUID &>(_GUID &)
0x14004fbdb  lea     rsi, [rbx+418h]
0x14004fbe2  mov     rdi, [rsi]
0x14004fbe5  test    rdi, rdi
0x14004fbe8  jz      short loc_14004FC21
0x14004fbea  mov     rcx, [rdi+0E0h]; pwa
0x14004fbf1  test    rcx, rcx
0x14004fbf4  jz      short loc_14004FC02
0x14004fbf6  call    cs:__imp_CloseThreadpoolWait
0x14004fbfd  nop     dword ptr [rax+rax+00h]
0x14004fc02  cmp     [rdi+0D0h], r12d
0x14004fc09  jz      short loc_14004FC17
0x14004fc0b  call    cs:__imp_WSACleanup
0x14004fc12  nop     dword ptr [rax+rax+00h]
0x14004fc17  xor     edx, edx
0x14004fc19  mov     rcx, rsi
0x14004fc1c  call    ?Reset@?$VmReferencePtr@VWorkerConfiguration@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVWorkerConfiguration@@@Z; Vml::VmReferencePtr<WorkerConfiguration,Vml::VmUserReferenceTraits>::Reset(WorkerConfiguration *)
0x14004fc21  lea     rdx, [rsp+1E0h+var_1B8]
0x14004fc26  lea     rcx, [rsp+1E0h+var_1A0]
0x14004fc2b  call    ??$TeardownMigrationManager@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownMigrationManager<_GUID &>(_GUID &)
0x14004fc30  mov     rdx, [rbx+0A18h]
0x14004fc37  mov     [rbx+0A18h], r12
0x14004fc3e  test    rdx, rdx
0x14004fc41  jz      short loc_14004FC57
0x14004fc43  mov     rax, [rdx+8]
0x14004fc47  movsxd  rcx, dword ptr [rax+4]
0x14004fc4b  add     rdx, 8
0x14004fc4f  add     rcx, rdx; this
0x14004fc52  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14004fc57  mov     [rbx+598h], r12
0x14004fc5e  mov     rcx, [rbx+590h]
0x14004fc65  mov     [rbx+590h], r12
0x14004fc6c  test    rcx, rcx
0x14004fc6f  jz      short loc_14004FC7A
0x14004fc71  add     rcx, 8; this
0x14004fc75  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14004fc7a  mov     rdx, [rbx+3E8h]
0x14004fc81  test    rdx, rdx
0x14004fc84  jz      short loc_14004FCC6
0x14004fc86  mov     rcx, [rdx+98h]
0x14004fc8d  add     rcx, 8
0x14004fc91  mov     rax, [rcx]
0x14004fc94  mov     rdx, [rdx+0C0h]
0x14004fc9b  mov     rax, [rax+40h]
0x14004fc9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fca4  mov     rdx, [rbx+3E8h]
0x14004fcab  mov     rax, [rdx+8]
0x14004fcaf  movsxd  rcx, dword ptr [rax+4]
0x14004fcb3  add     rdx, 8
0x14004fcb7  add     rcx, rdx; this
0x14004fcba  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14004fcbf  mov     [rbx+3E8h], r12
0x14004fcc6  mov     rcx, [rbx+3F0h]; this
0x14004fccd  test    rcx, rcx
0x14004fcd0  jz      short loc_14004FCF9
0x14004fcd2  call    ?TeardownRegisteredResults@WorkerCpuidHandler@@AEAAXXZ; WorkerCpuidHandler::TeardownRegisteredResults(void)
0x14004fcd7  mov     rdx, [rbx+3F0h]
0x14004fcde  mov     rax, [rdx+8]
0x14004fce2  movsxd  rcx, dword ptr [rax+4]
0x14004fce6  add     rdx, 8
0x14004fcea  add     rcx, rdx; this
0x14004fced  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14004fcf2  mov     [rbx+3F0h], r12
0x14004fcf9  mov     rcx, [rbx+3F8h]; this
0x14004fd00  test    rcx, rcx
0x14004fd03  jz      short loc_14004FD2C
0x14004fd05  call    ?Teardown@WorkerExceptionHandler@@QEAAXXZ; WorkerExceptionHandler::Teardown(void)
0x14004fd0a  mov     rdx, [rbx+3F8h]
0x14004fd11  mov     rax, [rdx+8]
0x14004fd15  movsxd  rcx, dword ptr [rax+4]
0x14004fd19  add     rdx, 8
0x14004fd1d  add     rcx, rdx; this
0x14004fd20  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14004fd25  mov     [rbx+3F8h], r12
0x14004fd2c  lea     rdx, [rsp+1E0h+var_1B8]
0x14004fd31  lea     rcx, [rsp+1E0h+var_1A0]
0x14004fd36  call    ??$TeardownInternalInterceptHandler@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownInternalInterceptHandler<_GUID &>(_GUID &)
0x14004fd3b  mov     rcx, [rbx+3E0h]; this
0x14004fd42  test    rcx, rcx
0x14004fd45  jz      short loc_14004FD53
0x14004fd47  call    ?Teardown@MemoryManager@@QEAAXXZ; MemoryManager::Teardown(void)
0x14004fd4c  mov     [rbx+3E0h], r12
0x14004fd53  lea     rdi, [rbx+410h]
0x14004fd5a  mov     rcx, [rdi]
0x14004fd5d  test    rcx, rcx
0x14004fd60  jz      short loc_14004FD7B
0x14004fd62  mov     rax, [rcx]
0x14004fd65  mov     rax, [rax+108h]
0x14004fd6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fd71  xor     edx, edx
0x14004fd73  mov     rcx, rdi
0x14004fd76  call    ?Reset@?$VmReferencePtr@VVndCompletionThread@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVVndCompletionThread@@@Z; Vml::VmReferencePtr<VndCompletionThread,Vml::VmUserReferenceTraits>::Reset(VndCompletionThread *)
0x14004fd7b  lea     rdx, [rsp+1E0h+var_1B8]
0x14004fd80  lea     rcx, [rsp+1E0h+var_1A0]
0x14004fd85  call    ??$TeardownProcessorManager@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownProcessorManager<_GUID &>(_GUID &)
0x14004fd8a  mov     rcx, [r14]
0x14004fd8d  test    rcx, rcx
0x14004fd90  jz      short loc_14004FDA8
0x14004fd92  mov     rax, [rcx]
0x14004fd95  mov     rax, [rax+58h]
0x14004fd99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fd9e  xor     edx, edx
0x14004fda0  mov     rcx, r14
0x14004fda3  call    ?Reset@?$VmReferencePtr@UIVidPartitionManager@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAUIVidPartitionManager@@@Z; Vml::VmReferencePtr<IVidPartitionManager,Vml::VmUserReferenceTraits>::Reset(IVidPartitionManager *)
0x14004fda8  mov     rcx, [rbx+420h]
0x14004fdaf  test    rcx, rcx
0x14004fdb2  jz      short loc_14004FE18
0x14004fdb4  mov     rax, [rbx+588h]
0x14004fdbb  cmp     [rax+17Ch], r12d
0x14004fdc2  jnz     short loc_14004FDE2
0x14004fdc4  mov     edx, 1
0x14004fdc9  cmp     [rbx+4F4h], edx
0x14004fdcf  jnz     short loc_14004FDE2
0x14004fdd1  cmp     [rbx+4F0h], edx
0x14004fdd7  jz      short loc_14004FDE5
0x14004fdd9  cmp     [rbx+4F8h], r12d
0x14004fde0  jz      short loc_14004FDE5
0x14004fde2  mov     edx, r12d
0x14004fde5  mov     rax, [rcx]
0x14004fde8  mov     rax, [rax+20h]
0x14004fdec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fdf1  mov     rdx, [rbx+420h]
0x14004fdf8  mov     [rbx+420h], r12
0x14004fdff  test    rdx, rdx
0x14004fe02  jz      short loc_14004FE18
0x14004fe04  mov     rax, [rdx+8]
0x14004fe08  movsxd  rcx, dword ptr [rax+4]
0x14004fe0c  add     rdx, 8
0x14004fe10  add     rcx, rdx; this
0x14004fe13  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14004fe18  lea     rdx, [rsp+1E0h+var_1B8]
0x14004fe1d  lea     rcx, [rsp+1E0h+var_1A0]
0x14004fe22  call    ??$TeardownSavedStateFileManager@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownSavedStateFileManager<_GUID &>(_GUID &)
0x14004fe27  lea     rcx, [rbx+428h]
0x14004fe2e  call    ?Reset@?$VmReferencePtr@UIMetricManager@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAUIMetricManager@@@Z; Vml::VmReferencePtr<IMetricManager,Vml::VmUserReferenceTraits>::Reset(IMetricManager *)
0x14004fe33  lea     rdx, [rsp+1E0h+var_1B8]
0x14004fe38  lea     rcx, [rsp+1E0h+var_1A0]
0x14004fe3d  call    ??$TeardownMetricManager@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownMetricManager<_GUID &>(_GUID &)
0x14004fe42  mov     rdx, [rbx+408h]
0x14004fe49  mov     [rbx+408h], r12
0x14004fe50  test    rdx, rdx
0x14004fe53  jz      short loc_14004FE69
0x14004fe55  mov     rax, [rdx+8]
0x14004fe59  movsxd  rcx, dword ptr [rax+4]
0x14004fe5d  add     rdx, 8
0x14004fe61  add     rcx, rdx; this
0x14004fe64  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14004fe69  lea     rdx, [rsp+1E0h+var_1B8]
0x14004fe6e  lea     rcx, [rsp+1E0h+var_1A0]
0x14004fe73  call    ??$TeardownNumaManager@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownNumaManager<_GUID &>(_GUID &)
0x14004fe78  mov     rcx, [rbx+430h]
0x14004fe7f  mov     [rbx+430h], r12
0x14004fe86  test    rcx, rcx
0x14004fe89  jz      short loc_14004FE97
0x14004fe8b  mov     rax, [rcx]
0x14004fe8e  mov     rax, [rax+10h]
0x14004fe92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fe97  lea     rdx, [rsp+1E0h+var_1B8]
0x14004fe9c  lea     rcx, [rsp+1E0h+var_1A0]
0x14004fea1  call    ??$TeardownSecurityManager@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownSecurityManager<_GUID &>(_GUID &)
0x14004fea6  mov     rcx, [rbx+5A8h]
0x14004fead  mov     [rbx+5A8h], r12
0x14004feb4  test    rcx, rcx
0x14004feb7  jz      short loc_14004FEC5
0x14004feb9  mov     rax, [rcx]
0x14004febc  mov     rax, [rax+10h]
0x14004fec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fec5  mov     rcx, [rbx+910h]
0x14004fecc  mov     [rbx+910h], r12
0x14004fed3  test    rcx, rcx
0x14004fed6  jz      short loc_14004FEE4
0x14004fed8  mov     rax, [rcx]
0x14004fedb  mov     rax, [rax+10h]
0x14004fedf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fee4  mov     rcx, [rbx+918h]
0x14004feeb  mov     [rbx+918h], r12
0x14004fef2  test    rcx, rcx
0x14004fef5  jz      short loc_14004FF03
0x14004fef7  mov     rax, [rcx]
0x14004fefa  mov     rax, [rax+10h]
0x14004fefe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ff03  mov     rcx, [rbx+5B8h]
0x14004ff0a  mov     [rbx+5B8h], r12
0x14004ff11  test    rcx, rcx
0x14004ff14  jz      short loc_14004FF22
0x14004ff16  mov     rax, [rcx]
0x14004ff19  mov     rax, [rax+10h]
0x14004ff1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ff22  mov     rcx, [rbx+5C0h]
0x14004ff29  mov     [rbx+5C0h], r12
0x14004ff30  test    rcx, rcx
0x14004ff33  jz      short loc_14004FF41
0x14004ff35  mov     rax, [rcx]
0x14004ff38  mov     rax, [rax+10h]
0x14004ff3c  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
