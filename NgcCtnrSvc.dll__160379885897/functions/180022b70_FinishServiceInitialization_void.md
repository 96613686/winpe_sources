# FinishServiceInitialization(void)

- ea: `0x180022b70`
- end: `0x180022e60`
- name: `?FinishServiceInitialization@@YAKXZ`
- size: `752`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180038a60`

## callees

- `0x1800110e0`
- `0x180011d88`
- `0x180016f14`
- `0x180017820`
- `0x180018378`
- `0x180018c44`
- `0x180019168`
- `0x18001c4fc`
- `0x18001d530`
- `0x18001de28`
- `0x18001e128`
- `0x1800205c0`
- `0x180020680`
- `0x180022b70`
- `0x180022f7c`
- `0x180023278`
- `0x180023398`
- `0x1800233ec`
- `0x1800235bc`
- `0x180023600`
- `0x180023a08`
- `0x180023a88`
- `0x180025344`
- `0x180026c94`
- `0x180029980`
- `0x18003b684`
- `0x180055e5c`
- `0x18005a124`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022bcc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022e48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022bcc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022e48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022b88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022b88`
- `NgcIsoCtnr!NgcIsoCtnrInitializePregenPool` at `0x180022cc1`
- `NgcIsoCtnr!NgcIsoCtnrInitializePregenPool` at `0x180022cc1`

## string_xrefs

- `0x180022bab`: `onecore\ds\security\ngc\ctnrsvc\service\service.cpp`
- `0x180022be4`: `onecore\ds\security\ngc\ctnrsvc\service\service.cpp`

## pseudocode

```c
__int64 FinishServiceInitialization(void)
{
  struct _RTL_CRITICAL_SECTION *v0; // rsi
  ThreadpoolManager::ThreadpoolManagerImpl **v1; // rax
  NgcUtils *v2; // rcx
  int v3; // ebx
  __int64 v4; // rdx
  NgcUtils *v6; // rcx
  int started; // eax
  HandlerManager *v8; // rax
  ContainerManager *v9; // rax
  int v10; // eax
  ContainerManager *v11; // rbx
  int RootPath; // eax
  wil::details::in1diag3 *v13; // rcx
  __int64 v14; // rdx
  int v15; // eax
  __int64 ***v16; // rax
  void (*v17)(void *, void *, unsigned int); // r8
  int v18; // eax
  int v19; // eax
  NgcUtils::ProcessPriorityManager *v20; // rax
  int v21; // eax
  NgcUtils::ProcessPriorityManager *v22; // rax
  int v23; // eax
  int v24; // eax
  NgcCtnrCommon *v25; // rcx
  int v26; // eax
  int *v27; // [rsp+20h] [rbp-18h] BYREF
  __int16 v28; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]
  char v30; // [rsp+60h] [rbp+28h] BYREF
  __int16 v31; // [rsp+61h] [rbp+29h]
  unsigned __int16 *v32; // [rsp+68h] [rbp+30h] BYREF
  int v33; // [rsp+70h] [rbp+38h] BYREF
  struct _RTL_CRITICAL_SECTION *v34; // [rsp+78h] [rbp+40h]

  v0 = (struct _RTL_CRITICAL_SECTION *)((char *)ServiceContext::Instance() + 64);
  EnterCriticalSection(v0);
  v34 = v0;
  v1 = (ThreadpoolManager::ThreadpoolManagerImpl **)ThreadpoolManager::Instance();
  v3 = ThreadpoolManager::ThreadpoolManagerImpl::Initialize(*v1);
  if ( v3 < 0 )
  {
    v4 = 850;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
      (const char *)(unsigned int)v3,
      (int)v27);
LABEL_4:
    if ( v0 )
      LeaveCriticalSection(v0);
    return (unsigned int)v3;
  }
  if ( NgcUtils::IsSecureBioEnabled(v2) || NgcUtils::IsNgcInVsmEnabled(v6) )
  {
    started = StartTrustlet();
    if ( started < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x358,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
        (const char *)(unsigned int)started,
        (int)v27);
  }
  ContainerManager::Instance(1);
  HandlerManager::Instance();
  v8 = HandlerManager::Instance();
  v3 = HandlerManager::Load(v8);
  if ( v3 < 0 )
  {
    v4 = 862;
    goto LABEL_3;
  }
  v31 = 258;
  v9 = ContainerManager::Instance(0);
  v10 = ContainerManager::Load(v9);
  v33 = v10;
  if ( v10 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x371,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
      (const char *)(unsigned int)v10,
      (int)v27);
  if ( (char *)ProcessHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v32 = 0;
    v11 = ContainerManager::Instance(0);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v32,
      0);
    RootPath = ContainerManager::GetRootPath(v11, &v32);
    v13 = retaddr;
    if ( RootPath >= 0 )
    {
      RootPath = NgcIsoCtnrInitializePregenPool(v32);
      v13 = retaddr;
      if ( RootPath >= 0 )
        goto LABEL_21;
      v14 = 889;
    }
    else
    {
      v14 = 887;
    }
    wil::details::in1diag3::_Log_Hr(
      v13,
      (void *)v14,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
      (const char *)(unsigned int)RootPath,
      (int)v27);
LABEL_21:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcIsoWatchdog>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NgcIsoWatchdog>::GetImpl'::`2'::impl) )
    {
      v15 = StartNgcIsoWatchdogLoop();
      if ( v15 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x37D,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
          (const char *)(unsigned int)v15,
          (int)v27);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v32);
  }
  v27 = &v33;
  v28 = 258;
  v16 = (__int64 ***)HandlerManager::Instance();
  v18 = HandlerManager::StartHandlers(v16, 0x12Cu, v17);
  v3 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x39B,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
      (const char *)(unsigned int)v18,
      (int)v27);
    wil::details::ScopeExitFnGuard__lambda_0a4c0a1de6b26816c4e2c843e83ec0e8___::operator()(&v27);
    wil::details::ScopeExitFnGuard__lambda_6de966007b66b61b7be861dac11c36f8___::operator()(&v30);
    goto LABEL_4;
  }
  *(_WORD *)((char *)&v32 + 1) = 258;
  v19 = RegisterForWnf();
  if ( v19 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3AA,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
      (const char *)(unsigned int)v19,
      (int)v27);
  v20 = NgcUtils::ProcessPriorityManager::Instance();
  v21 = NgcUtils::ProcessPriorityManager::RegisterForPowerNotification(v20);
  if ( v21 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3AC,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
      (const char *)(unsigned int)v21,
      (int)v27);
  v22 = NgcUtils::ProcessPriorityManager::Instance();
  v23 = NgcUtils::ProcessPriorityManager::RegisterConnectedStandByExitNotification(v22);
  if ( v23 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3AD,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
      (const char *)(unsigned int)v23,
      (int)v27);
  v24 = CheckContainerLockout();
  v25 = retaddr;
  if ( v24 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3B1,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
      (const char *)(unsigned int)v24,
      (int)v27);
  v26 = NgcCtnrCommon::ForceDeviceWipeIfNecessary(v25);
  if ( v26 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3B4,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
      (const char *)(unsigned int)v26,
      (int)v27);
  HIBYTE(v31) = 0;
  HIBYTE(v28) = 0;
  BYTE2(v32) = 0;
  wil::details::ScopeExitFnGuard__lambda_262a2a1bfb0d7f07f4d31e57e96ccf44___::operator()(&v32);
  wil::details::ScopeExitFnGuard__lambda_0a4c0a1de6b26816c4e2c843e83ec0e8___::operator()(&v27);
  wil::details::ScopeExitFnGuard__lambda_6de966007b66b61b7be861dac11c36f8___::operator()(&v30);
  if ( v0 )
    LeaveCriticalSection(v0);
  return 0;
}

```

## disassembly

```asm
0x180022b70  push    rbp
0x180022b72  push    rbx
0x180022b73  push    rsi
0x180022b74  push    rdi
0x180022b75  mov     rbp, rsp
0x180022b78  sub     rsp, 38h
0x180022b7c  call    ?Instance@ServiceContext@@SAAEAU1@XZ; ServiceContext::Instance(void)
0x180022b81  lea     rsi, [rax+40h]
0x180022b85  mov     rcx, rsi; lpCriticalSection
0x180022b88  call    cs:__imp_EnterCriticalSection
0x180022b8f  nop     dword ptr [rax+rax+00h]
0x180022b94  mov     [rbp+arg_18], rsi
0x180022b98  call    ?Instance@ThreadpoolManager@@SAAEAV1@XZ; ThreadpoolManager::Instance(void)
0x180022b9d  mov     rcx, [rax]; this
0x180022ba0  call    ?Initialize@ThreadpoolManagerImpl@ThreadpoolManager@@QEAAJXZ; ThreadpoolManager::ThreadpoolManagerImpl::Initialize(void)
0x180022ba5  mov     ebx, eax
0x180022ba7  test    eax, eax
0x180022ba9  jns     short loc_180022BDF
0x180022bab  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x180022bb2  mov     edx, 352h; void *
0x180022bb7  mov     r9d, ebx; char *
0x180022bba  mov     rcx, [rbp+20h]; this
0x180022bbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022bc3  nop
0x180022bc4  test    rsi, rsi
0x180022bc7  jz      short loc_180022BD8
0x180022bc9  mov     rcx, rsi; lpCriticalSection
0x180022bcc  call    cs:__imp_LeaveCriticalSection
0x180022bd3  nop     dword ptr [rax+rax+00h]
0x180022bd8  mov     eax, ebx
0x180022bda  jmp     loc_180022E56
0x180022bdf  call    ?IsSecureBioEnabled@NgcUtils@@YA_NXZ; NgcUtils::IsSecureBioEnabled(void)
0x180022be4  lea     rdi, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x180022beb  test    al, al
0x180022bed  jnz     short loc_180022BF8
0x180022bef  call    ?IsNgcInVsmEnabled@NgcUtils@@YA_NXZ; NgcUtils::IsNgcInVsmEnabled(void)
0x180022bf4  test    al, al
0x180022bf6  jz      short loc_180022C15
0x180022bf8  call    ?StartTrustlet@@YAJXZ; StartTrustlet(void)
0x180022bfd  mov     rcx, [rbp+20h]; this
0x180022c01  test    eax, eax
0x180022c03  jns     short loc_180022C15
0x180022c05  mov     r9d, eax; char *
0x180022c08  mov     r8, rdi; unsigned int
0x180022c0b  mov     edx, 358h; void *
0x180022c10  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022c15  mov     cl, 1; bool
0x180022c17  call    ?Instance@ContainerManager@@SAAEAV1@_N@Z; ContainerManager::Instance(bool)
0x180022c1c  call    ?Instance@HandlerManager@@SAAEAV1@XZ; HandlerManager::Instance(void)
0x180022c21  call    ?Instance@HandlerManager@@SAAEAV1@XZ; HandlerManager::Instance(void)
0x180022c26  mov     rcx, rax; this
0x180022c29  call    ?Load@HandlerManager@@QEAAJXZ; HandlerManager::Load(void)
0x180022c2e  mov     ebx, eax
0x180022c30  test    eax, eax
0x180022c32  jns     short loc_180022C41
0x180022c34  mov     r8, rdi
0x180022c37  mov     edx, 35Eh
0x180022c3c  jmp     loc_180022BB7
0x180022c41  mov     [rbp+arg_1], 102h
0x180022c47  xor     ecx, ecx; bool
0x180022c49  call    ?Instance@ContainerManager@@SAAEAV1@_N@Z; ContainerManager::Instance(bool)
0x180022c4e  mov     rcx, rax; this
0x180022c51  call    ?Load@ContainerManager@@QEAAJXZ; ContainerManager::Load(void)
0x180022c56  mov     [rbp+arg_10], eax
0x180022c59  mov     rcx, [rbp+20h]; this
0x180022c5d  test    eax, eax
0x180022c5f  jns     short loc_180022C71
0x180022c61  mov     r9d, eax; char *
0x180022c64  mov     r8, rdi; unsigned int
0x180022c67  mov     edx, 371h; void *
0x180022c6c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022c71  mov     rax, cs:ProcessHandle
0x180022c78  dec     rax
0x180022c7b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180022c7f  ja      loc_180022D1C
0x180022c85  mov     [rbp+arg_8], 0
0x180022c8d  xor     ecx, ecx; bool
0x180022c8f  call    ?Instance@ContainerManager@@SAAEAV1@_N@Z; ContainerManager::Instance(bool)
0x180022c94  mov     rbx, rax
0x180022c97  xor     edx, edx
0x180022c99  lea     rcx, [rbp+arg_8]
0x180022c9d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180022ca2  lea     rdx, [rbp+arg_8]; unsigned __int16 **
0x180022ca6  mov     rcx, rbx; this
0x180022ca9  call    ?GetRootPath@ContainerManager@@QEAAJPEAPEAG@Z; ContainerManager::GetRootPath(ushort * *)
0x180022cae  mov     rcx, [rbp+20h]
0x180022cb2  test    eax, eax
0x180022cb4  jns     short loc_180022CBD
0x180022cb6  mov     edx, 377h
0x180022cbb  jmp     short loc_180022CDA
0x180022cbd  mov     rcx, [rbp+arg_8]
0x180022cc1  call    cs:__imp_NgcIsoCtnrInitializePregenPool
0x180022cc8  nop     dword ptr [rax+rax+00h]
0x180022ccd  mov     rcx, [rbp+20h]; this
0x180022cd1  test    eax, eax
0x180022cd3  jns     short loc_180022CE5
0x180022cd5  mov     edx, 379h; void *
0x180022cda  mov     r9d, eax; char *
0x180022cdd  mov     r8, rdi; unsigned int
0x180022ce0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022ce5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NgcIsoWatchdog@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NgcIsoWatchdog@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcIsoWatchdog> `wil::Feature<__WilFeatureTraits_Feature_NgcIsoWatchdog>::GetImpl(void)'::`2'::impl
0x180022cec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NgcIsoWatchdog@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcIsoWatchdog>::__private_IsEnabled(void)
0x180022cf1  test    al, al
0x180022cf3  jz      short loc_180022D13
0x180022cf5  call    ?StartNgcIsoWatchdogLoop@@YAJXZ; StartNgcIsoWatchdogLoop(void)
0x180022cfa  mov     rcx, [rbp+20h]; this
0x180022cfe  test    eax, eax
0x180022d00  jns     short loc_180022D13
0x180022d02  mov     r9d, eax; char *
0x180022d05  mov     r8, rdi; unsigned int
0x180022d08  mov     edx, 37Dh; void *
0x180022d0d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022d12  nop
0x180022d13  lea     rcx, [rbp+arg_8]
0x180022d17  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180022d1c  lea     rax, [rbp+arg_10]
0x180022d20  mov     [rbp+var_18], rax
0x180022d24  mov     [rbp+var_10], 102h
0x180022d2a  call    ?Instance@HandlerManager@@SAAEAV1@XZ; HandlerManager::Instance(void)
0x180022d2f  mov     edx, 12Ch; unsigned int
0x180022d34  mov     rcx, rax; this
0x180022d37  call    ?StartHandlers@HandlerManager@@QEAAJKP6AXPEAX0K@Z@Z; HandlerManager::StartHandlers(ulong,void (*)(void *,void *,ulong))
0x180022d3c  mov     ebx, eax
0x180022d3e  test    eax, eax
0x180022d40  jns     short loc_180022D6F
0x180022d42  mov     rcx, [rbp+20h]; this
0x180022d46  mov     r9d, eax; char *
0x180022d49  mov     r8, rdi; unsigned int
0x180022d4c  mov     edx, 39Bh; void *
0x180022d51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022d56  nop
0x180022d57  lea     rcx, [rbp+var_18]
0x180022d5b  call    wil__details__ScopeExitFnGuard__lambda_0a4c0a1de6b26816c4e2c843e83ec0e8_____operator__
0x180022d60  nop
0x180022d61  lea     rcx, [rbp+arg_0]
0x180022d65  call    wil__details__ScopeExitFnGuard__lambda_6de966007b66b61b7be861dac11c36f8_____operator__
0x180022d6a  jmp     loc_180022BC4
0x180022d6f  mov     word ptr [rbp+arg_8+1], 102h
0x180022d75  call    ?RegisterForWnf@@YAJXZ; RegisterForWnf(void)
0x180022d7a  mov     rcx, [rbp+20h]; this
0x180022d7e  test    eax, eax
0x180022d80  jns     short loc_180022D92
0x180022d82  mov     r9d, eax; char *
0x180022d85  mov     r8, rdi; unsigned int
0x180022d88  mov     edx, 3AAh; void *
0x180022d8d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022d92  call    ?Instance@ProcessPriorityManager@NgcUtils@@SAAEAV12@XZ; NgcUtils::ProcessPriorityManager::Instance(void)
0x180022d97  mov     rcx, rax; this
0x180022d9a  call    ?RegisterForPowerNotification@ProcessPriorityManager@NgcUtils@@QEAAJXZ; NgcUtils::ProcessPriorityManager::RegisterForPowerNotification(void)
0x180022d9f  mov     rcx, [rbp+20h]; this
0x180022da3  test    eax, eax
0x180022da5  jns     short loc_180022DB7
0x180022da7  mov     r9d, eax; char *
0x180022daa  mov     r8, rdi; unsigned int
0x180022dad  mov     edx, 3ACh; void *
0x180022db2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022db7  call    ?Instance@ProcessPriorityManager@NgcUtils@@SAAEAV12@XZ; NgcUtils::ProcessPriorityManager::Instance(void)
0x180022dbc  mov     rcx, rax; this
0x180022dbf  call    ?RegisterConnectedStandByExitNotification@ProcessPriorityManager@NgcUtils@@QEAAJXZ; NgcUtils::ProcessPriorityManager::RegisterConnectedStandByExitNotification(void)
0x180022dc4  mov     rcx, [rbp+20h]; this
0x180022dc8  test    eax, eax
0x180022dca  jns     short loc_180022DDC
0x180022dcc  mov     r9d, eax; char *
0x180022dcf  mov     r8, rdi; unsigned int
0x180022dd2  mov     edx, 3ADh; void *
0x180022dd7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022ddc  call    ?CheckContainerLockout@@YAJXZ; CheckContainerLockout(void)
0x180022de1  mov     rcx, [rbp+20h]; this
0x180022de5  test    eax, eax
0x180022de7  jns     short loc_180022DF9
0x180022de9  mov     r9d, eax; char *
0x180022dec  mov     r8, rdi; unsigned int
0x180022def  mov     edx, 3B1h; void *
0x180022df4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022df9  call    ?ForceDeviceWipeIfNecessary@NgcCtnrCommon@@YAJXZ; NgcCtnrCommon::ForceDeviceWipeIfNecessary(void)
0x180022dfe  mov     rcx, [rbp+20h]; this
0x180022e02  test    eax, eax
0x180022e04  jns     short loc_180022E16
0x180022e06  mov     r9d, eax; char *
0x180022e09  mov     r8, rdi; unsigned int
0x180022e0c  mov     edx, 3B4h; void *
0x180022e11  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022e16  mov     byte ptr [rbp+arg_1+1], 0
0x180022e1a  mov     byte ptr [rbp+var_10+1], 0
0x180022e1e  mov     byte ptr [rbp+arg_8+2], 0
0x180022e22  lea     rcx, [rbp+arg_8]
0x180022e26  call    wil__details__ScopeExitFnGuard__lambda_262a2a1bfb0d7f07f4d31e57e96ccf44_____operator__
0x180022e2b  nop
0x180022e2c  lea     rcx, [rbp+var_18]
0x180022e30  call    wil__details__ScopeExitFnGuard__lambda_0a4c0a1de6b26816c4e2c843e83ec0e8_____operator__
0x180022e35  nop
0x180022e36  lea     rcx, [rbp+arg_0]
0x180022e3a  call    wil__details__ScopeExitFnGuard__lambda_6de966007b66b61b7be861dac11c36f8_____operator__
0x180022e3f  nop
0x180022e40  test    rsi, rsi
0x180022e43  jz      short loc_180022E54
0x180022e45  mov     rcx, rsi; lpCriticalSection
0x180022e48  call    cs:__imp_LeaveCriticalSection
0x180022e4f  nop     dword ptr [rax+rax+00h]
0x180022e54  xor     eax, eax
0x180022e56  add     rsp, 38h
0x180022e5a  pop     rdi
0x180022e5b  pop     rsi
0x180022e5c  pop     rbx
0x180022e5d  pop     rbp
0x180022e5e  retn
```
