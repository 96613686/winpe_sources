# InternalUninitializeService(void)

- ea: `0x1800250a8`
- end: `0x1800252b2`
- name: `?InternalUninitializeService@@YAXXZ`
- size: `522`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180038a34`

## callees

- `0x1800110e0`
- `0x180011d88`
- `0x180018c44`
- `0x180019168`
- `0x18001bb1c`
- `0x18001cd28`
- `0x1800250a8`
- `0x1800252c0`
- `0x180025344`
- `0x1800253b4`
- `0x1800254d0`
- `0x180025550`
- `0x18002559c`
- `0x180029980`
- `0x180037348`
- `0x18003b650`
- `0x18003bb2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002529a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002529a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800250be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800250be`
- `ntdll!RtlUnsubscribeWnfNotificationWithCompletionCallback` at `0x1800251ff`
- `ntdll!RtlUnsubscribeWnfNotificationWithCompletionCallback` at `0x18002523e`
- `ntdll!RtlUnsubscribeWnfNotificationWithCompletionCallback` at `0x1800251ff`
- `ntdll!RtlUnsubscribeWnfNotificationWithCompletionCallback` at `0x18002523e`
- `ntdll!RtlWnfDllUnloadCallback` at `0x1800251f8`
- `ntdll!RtlWnfDllUnloadCallback` at `0x180025237`
- `NgcIsoCtnr!NgcIsoCtnrUninitializePregenPool` at `0x1800250e6`
- `NgcIsoCtnr!NgcIsoCtnrUninitializePregenPool` at `0x1800250e6`
- `api-ms-win-oobe-notification-l1-1-0!UnregisterWaitUntilOOBECompleted` at `0x18002526f`
- `api-ms-win-oobe-notification-l1-1-0!UnregisterWaitUntilOOBECompleted` at `0x18002526f`

## string_xrefs

- `0x1800250d9`: `onecore\ds\security\ngc\ctnrsvc\service\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void InternalUninitializeService(void)
{
  struct _RTL_CRITICAL_SECTION *v0; // rbx
  int v1; // eax
  HandlerManager *v2; // rax
  ThreadpoolManager::ThreadpoolManagerImpl **v3; // rax
  ContainerManager *v4; // rax
  HandlerManager *v5; // rax
  int v6; // eax
  unsigned int v7; // edx
  wil::details::in1diag3 *v8; // rcx
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  int v11; // eax
  struct NgcUtils::ProcessPriorityManager *v12; // rax
  _QWORD *v13; // rcx
  int v14; // eax
  int v15; // eax
  const char *v16; // r9
  int v17; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char *v19; // [rsp+30h] [rbp+8h] BYREF

  v0 = (struct _RTL_CRITICAL_SECTION *)((char *)ServiceContext::Instance() + 64);
  EnterCriticalSection(v0);
  v19 = (char *)v0;
  if ( (char *)ProcessHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v1 = NgcIsoCtnrUninitializePregenPool();
    if ( v1 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x400,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
        (const char *)(unsigned int)v1,
        v17);
  }
  v2 = HandlerManager::Instance();
  HandlerManager::StopHandlers(v2);
  v3 = (ThreadpoolManager::ThreadpoolManagerImpl **)ThreadpoolManager::Instance();
  ThreadpoolManager::ThreadpoolManagerImpl::Close(*v3);
  v4 = ContainerManager::Instance(0);
  ContainerManager::Unload(v4);
  v5 = HandlerManager::Instance();
  HandlerManager::Unload(v5);
  if ( (char *)ProcessHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v6 = NgcIsoTrustlet::TrustletProcess::Stop((NgcIsoTrustlet::TrustletProcess *)&g_trustlet);
    v8 = retaddr;
    if ( v6 >= 0 )
    {
      LODWORD(v19) = 0;
      v11 = VsmUtils::TrustletProcess::WaitForTrustletStopped(retaddr, v7, (int *)&v19);
      v8 = retaddr;
      if ( v11 >= 0 )
      {
        v9 = (unsigned int)v19;
        v8 = retaddr;
        if ( (int)v19 >= 0 )
          goto LABEL_12;
        v10 = 1041;
      }
      else
      {
        v9 = (unsigned int)v11;
        v10 = 1039;
      }
    }
    else
    {
      v9 = (unsigned int)v6;
      v10 = 1036;
    }
    wil::details::in1diag3::_Log_Hr(
      v8,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
      (const char *)v9,
      v17);
  }
LABEL_12:
  v12 = NgcUtils::ProcessPriorityManager::Instance();
  wil::details::unique_storage<wil::details::resource_policy<void *,unsigned long (void *),&unsigned long PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    (char *)v12 + 32,
    0);
  v13 = (_QWORD *)((char *)NgcUtils::ProcessPriorityManager::Instance() + 16);
  if ( *v13 )
    wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(
      v13,
      0);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(
    &g_pregenTriggerSubscription,
    0);
  if ( g_deviceLockPolicySubscription )
  {
    v14 = RtlUnsubscribeWnfNotificationWithCompletionCallback(
            g_deviceLockPolicySubscription,
            RtlWnfDllUnloadCallback,
            g_hInstance);
    if ( v14 < 0 )
      wil::details::in1diag3::_Log_NtStatus(
        retaddr,
        (void *)0x420,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
        (const char *)(unsigned int)v14,
        v17);
  }
  if ( g_proCspPolicySubscription )
  {
    v15 = RtlUnsubscribeWnfNotificationWithCompletionCallback(
            g_proCspPolicySubscription,
            RtlWnfDllUnloadCallback,
            g_hInstance);
    if ( v15 < 0 )
      wil::details::in1diag3::_Log_NtStatus(
        retaddr,
        (void *)0x428,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
        (const char *)(unsigned int)v15,
        v17);
  }
  if ( g_oobeDoneSubscription && !(unsigned int)UnregisterWaitUntilOOBECompleted() )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x42E,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
      v16);
  if ( v0 )
    LeaveCriticalSection(v0);
}

```

## disassembly

```asm
0x1800250a8  mov     [rsp+arg_8], rbx
0x1800250ad  push    rdi; int
0x1800250ae  sub     rsp, 20h
0x1800250b2  call    ?Instance@ServiceContext@@SAAEAU1@XZ; ServiceContext::Instance(void)
0x1800250b7  lea     rbx, [rax+40h]
0x1800250bb  mov     rcx, rbx; lpCriticalSection
0x1800250be  call    cs:__imp_EnterCriticalSection
0x1800250c5  nop     dword ptr [rax+rax+00h]
0x1800250ca  mov     [rsp+28h+arg_0], rbx
0x1800250cf  mov     rax, cs:ProcessHandle
0x1800250d6  dec     rax
0x1800250d9  lea     rdi, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x1800250e0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800250e4  ja      short loc_18002510B
0x1800250e6  call    cs:__imp_NgcIsoCtnrUninitializePregenPool
0x1800250ed  nop     dword ptr [rax+rax+00h]
0x1800250f2  mov     rcx, [rsp+28h]; this
0x1800250f7  test    eax, eax
0x1800250f9  jns     short loc_18002510B
0x1800250fb  mov     r9d, eax; char *
0x1800250fe  mov     r8, rdi; unsigned int
0x180025101  mov     edx, 400h; void *
0x180025106  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002510b  call    ?Instance@HandlerManager@@SAAEAV1@XZ; HandlerManager::Instance(void)
0x180025110  mov     rcx, rax; this
0x180025113  call    ?StopHandlers@HandlerManager@@QEAAXXZ; HandlerManager::StopHandlers(void)
0x180025118  call    ?Instance@ThreadpoolManager@@SAAEAV1@XZ; ThreadpoolManager::Instance(void)
0x18002511d  mov     rcx, [rax]; this
0x180025120  call    ?Close@ThreadpoolManagerImpl@ThreadpoolManager@@QEAAJXZ; ThreadpoolManager::ThreadpoolManagerImpl::Close(void)
0x180025125  xor     ecx, ecx; bool
0x180025127  call    ?Instance@ContainerManager@@SAAEAV1@_N@Z; ContainerManager::Instance(bool)
0x18002512c  mov     rcx, rax; this
0x18002512f  call    ?Unload@ContainerManager@@QEAAXXZ; ContainerManager::Unload(void)
0x180025134  call    ?Instance@HandlerManager@@SAAEAV1@XZ; HandlerManager::Instance(void)
0x180025139  mov     rcx, rax; this
0x18002513c  call    ?Unload@HandlerManager@@QEAAXXZ; HandlerManager::Unload(void)
0x180025141  mov     rax, cs:ProcessHandle
0x180025148  dec     rax
0x18002514b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002514f  ja      short loc_1800251B1
0x180025151  lea     rcx, ?g_trustlet@@3VTrustletProcess@NgcIsoTrustlet@@A; this
0x180025158  call    ?Stop@TrustletProcess@NgcIsoTrustlet@@UEAAJXZ; NgcIsoTrustlet::TrustletProcess::Stop(void)
0x18002515d  mov     rcx, [rsp+28h]; this
0x180025162  test    eax, eax
0x180025164  jns     short loc_180025170
0x180025166  mov     r9d, eax
0x180025169  mov     edx, 40Ch
0x18002516e  jmp     short loc_1800251A9
0x180025170  mov     dword ptr [rsp+28h+arg_0], 0
0x180025178  lea     r8, [rsp+28h+arg_0]; int *
0x18002517d  call    ?WaitForTrustletStopped@TrustletProcess@VsmUtils@@QEAAJKPEAJ@Z; VsmUtils::TrustletProcess::WaitForTrustletStopped(ulong,long *)
0x180025182  mov     rcx, [rsp+28h]
0x180025187  test    eax, eax
0x180025189  jns     short loc_180025195
0x18002518b  mov     r9d, eax
0x18002518e  mov     edx, 40Fh
0x180025193  jmp     short loc_1800251A9
0x180025195  mov     r9d, dword ptr [rsp+28h+arg_0]; char *
0x18002519a  mov     rcx, [rsp+28h]; this
0x18002519f  test    r9d, r9d
0x1800251a2  jns     short loc_1800251B1
0x1800251a4  mov     edx, 411h; void *
0x1800251a9  mov     r8, rdi; unsigned int
0x1800251ac  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800251b1  call    ?Instance@ProcessPriorityManager@NgcUtils@@SAAEAV12@XZ; NgcUtils::ProcessPriorityManager::Instance(void)
0x1800251b6  lea     rcx, [rax+20h]
0x1800251ba  xor     edx, edx
0x1800251bc  call    ?reset@?$unique_storage@U?$resource_policy@PEAX$$A6AKPEAX@Z$1?PowerSettingUnregisterNotification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,ulong (void *),&PowerSettingUnregisterNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800251c1  call    ?Instance@ProcessPriorityManager@NgcUtils@@SAAEAV12@XZ; NgcUtils::ProcessPriorityManager::Instance(void)
0x1800251c6  lea     rcx, [rax+10h]
0x1800251ca  cmp     qword ptr [rcx], 0
0x1800251ce  jz      short loc_1800251D7
0x1800251d0  xor     edx, edx
0x1800251d2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUwnf_subscription_state_base@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(wil::details::wnf_subscription_state_base *)
0x1800251d7  xor     edx, edx
0x1800251d9  lea     rcx, ?g_pregenTriggerSubscription@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> g_pregenTriggerSubscription
0x1800251e0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUwnf_subscription_state_base@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(wil::details::wnf_subscription_state_base *)
0x1800251e5  mov     rcx, cs:?g_deviceLockPolicySubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * g_deviceLockPolicySubscription
0x1800251ec  test    rcx, rcx
0x1800251ef  jz      short loc_180025224
0x1800251f1  mov     r8, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800251f8  mov     rdx, cs:__imp_RtlWnfDllUnloadCallback
0x1800251ff  call    cs:__imp_RtlUnsubscribeWnfNotificationWithCompletionCallback
0x180025206  nop     dword ptr [rax+rax+00h]
0x18002520b  mov     rcx, [rsp+28h]; this
0x180025210  test    eax, eax
0x180025212  jns     short loc_180025224
0x180025214  mov     r9d, eax; char *
0x180025217  mov     r8, rdi; unsigned int
0x18002521a  mov     edx, 420h; void *
0x18002521f  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180025224  mov     rcx, cs:?g_proCspPolicySubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * g_proCspPolicySubscription
0x18002522b  test    rcx, rcx
0x18002522e  jz      short loc_180025263
0x180025230  mov     r8, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x180025237  mov     rdx, cs:__imp_RtlWnfDllUnloadCallback
0x18002523e  call    cs:__imp_RtlUnsubscribeWnfNotificationWithCompletionCallback
0x180025245  nop     dword ptr [rax+rax+00h]
0x18002524a  mov     rcx, [rsp+28h]; this
0x18002524f  test    eax, eax
0x180025251  jns     short loc_180025263
0x180025253  mov     r9d, eax; char *
0x180025256  mov     r8, rdi; unsigned int
0x180025259  mov     edx, 428h; void *
0x18002525e  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180025263  mov     rcx, cs:?g_oobeDoneSubscription@@3PEAXEA; void * g_oobeDoneSubscription
0x18002526a  test    rcx, rcx
0x18002526d  jz      short loc_180025292
0x18002526f  call    cs:__imp_UnregisterWaitUntilOOBECompleted
0x180025276  nop     dword ptr [rax+rax+00h]
0x18002527b  mov     rcx, [rsp+28h]; this
0x180025280  test    eax, eax
0x180025282  jnz     short loc_180025292
0x180025284  mov     r8, rdi; unsigned int
0x180025287  mov     edx, 42Eh; void *
0x18002528c  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180025291  nop
0x180025292  test    rbx, rbx
0x180025295  jz      short loc_1800252A6
0x180025297  mov     rcx, rbx; lpCriticalSection
0x18002529a  call    cs:__imp_LeaveCriticalSection
0x1800252a1  nop     dword ptr [rax+rax+00h]
0x1800252a6  mov     rbx, [rsp+28h+arg_8]
0x1800252ab  add     rsp, 20h
0x1800252af  pop     rdi
0x1800252b0  retn
```
