# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14000b780`
- end: `0x14000b88d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x14000b07c`
- `0x14000b178`
- `0x14000b780`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000b80a`
- `KERNEL32!GetModuleHandleW` at `0x14000b80a`
- `KERNEL32!GetProcAddress` at `0x14000b821`
- `KERNEL32!GetProcAddress` at `0x14000b821`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b877`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b877`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b7d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b7d0`

## string_xrefs

- `0x14000b803`: `ntdll.dll`
- `0x14000b817`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v9; // eax

  if ( a3 == (void (*)(void *))-1LL )
  {
    wil::details::FeatureStateManager::SubscribeToUsageFlush(
      (wil::details::FeatureStateManager *)&wil::details::g_featureStateManager,
      this,
      (void (*)(void *))a2);
  }
  else
  {
    *this = 0;
    if ( wil::details::g_featureStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1400180A0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1400180A0 = 0;
      if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification )
        goto LABEL_10;
      ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "RtlRegisterFeatureConfigurationChangeNotification");
      g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_10:
        v9 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), char *, _QWORD, __int64 *))ProcAddress)(
               _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
               &wil::details::g_featureStateManager,
               0,
               &qword_1400180A0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&SRWLock);
    }
  }
}

```

## disassembly

```asm
0x14000b780  mov     [rsp+arg_0], rbx
0x14000b785  mov     [rsp+arg_8], rsi
0x14000b78a  push    rdi
0x14000b78b  sub     rsp, 30h
0x14000b78f  mov     rdi, r8
0x14000b792  mov     rsi, rdx
0x14000b795  mov     rbx, rcx
0x14000b798  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14000b79c  jnz     short loc_14000B7B5
0x14000b79e  mov     r8, rdx; void (*)(void *)
0x14000b7a1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000b7a4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000b7ab  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x14000b7b0  jmp     loc_14000B87D
0x14000b7b5  mov     qword ptr [rcx], 0
0x14000b7bc  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000b7c3  jz      loc_14000B87D
0x14000b7c9  lea     rcx, SRWLock; SRWLock
0x14000b7d0  call    cs:__imp_AcquireSRWLockExclusive
0x14000b7d6  cmp     cs:qword_1400180A0, 0
0x14000b7de  jnz     short loc_14000B85B
0x14000b7e0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000b7e7  mov     cs:qword_1400180A0, 0
0x14000b7f2  test    rax, rax
0x14000b7f5  jnz     short loc_14000B83A
0x14000b7f7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b7fe  test    rax, rax
0x14000b801  jnz     short loc_14000B817
0x14000b803  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000b80a  call    cs:__imp_GetModuleHandleW
0x14000b810  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b817  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000b81e  mov     rcx, rax; hModule
0x14000b821  call    cs:__imp_GetProcAddress
0x14000b827  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000b82e  test    rax, rax
0x14000b831  jnz     short loc_14000B83A
0x14000b833  mov     eax, 0C0000139h
0x14000b838  jmp     short loc_14000B857
0x14000b83a  lea     r9, qword_1400180A0
0x14000b841  xor     r8d, r8d
0x14000b844  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000b84b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x14000b852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b857  test    eax, eax
0x14000b859  jnz     short loc_14000B870
0x14000b85b  mov     r9, rdi; void *
0x14000b85e  lea     rcx, CriticalSection; this
0x14000b865  mov     r8, rsi; void (*)(void *)
0x14000b868  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000b86b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x14000b870  lea     rcx, SRWLock; SRWLock
0x14000b877  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b87d  mov     rbx, [rsp+38h+arg_0]
0x14000b882  mov     rsi, [rsp+38h+arg_8]
0x14000b887  add     rsp, 30h
0x14000b88b  pop     rdi
0x14000b88c  retn
```
