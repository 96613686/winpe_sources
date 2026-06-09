# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180017bd0`
- end: `0x180017cdd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18001734c`
- `0x180017448`
- `0x180017bd0`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017c20`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017c20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017cc7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017cc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017c71`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017c71`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017c5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017c5a`

## string_xrefs

- `0x180017c67`: `RtlRegisterFeatureConfigurationChangeNotification`
- `0x180017c53`: `ntdll.dll`

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
      AcquireSRWLockExclusive(&stru_1800292A8);
      if ( qword_180029318 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180029318 = 0;
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
        v9 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(), void *, _QWORD, __int64 *))ProcAddress)(
               `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
               &wil::details::g_featureStateManager,
               0,
               &qword_180029318);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_1800292A8);
    }
  }
}

```

## disassembly

```asm
0x180017bd0  mov     [rsp+arg_0], rbx
0x180017bd5  mov     [rsp+arg_8], rsi
0x180017bda  push    rdi
0x180017bdb  sub     rsp, 30h
0x180017bdf  mov     rdi, r8
0x180017be2  mov     rsi, rdx
0x180017be5  mov     rbx, rcx
0x180017be8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180017bec  jnz     short loc_180017C05
0x180017bee  mov     r8, rdx; void (*)(void *)
0x180017bf1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180017bf4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180017bfb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180017c00  jmp     loc_180017CCD
0x180017c05  mov     qword ptr [rcx], 0
0x180017c0c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180017c13  jz      loc_180017CCD
0x180017c19  lea     rcx, stru_1800292A8; SRWLock
0x180017c20  call    cs:__imp_AcquireSRWLockExclusive
0x180017c26  cmp     cs:qword_180029318, 0
0x180017c2e  jnz     short loc_180017CAB
0x180017c30  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180017c37  mov     cs:qword_180029318, 0
0x180017c42  test    rax, rax
0x180017c45  jnz     short loc_180017C8A
0x180017c47  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180017c4e  test    rax, rax
0x180017c51  jnz     short loc_180017C67
0x180017c53  lea     rcx, ModuleName; "ntdll.dll"
0x180017c5a  call    cs:__imp_GetModuleHandleW
0x180017c60  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180017c67  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180017c6e  mov     rcx, rax; hModule
0x180017c71  call    cs:__imp_GetProcAddress
0x180017c77  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180017c7e  test    rax, rax
0x180017c81  jnz     short loc_180017C8A
0x180017c83  mov     eax, 0C0000139h
0x180017c88  jmp     short loc_180017CA7
0x180017c8a  lea     r9, qword_180029318
0x180017c91  xor     r8d, r8d
0x180017c94  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180017c9b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToStateChangesUnderLock@FeatureStateManager@details@wil@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@5@PEAX@Z@SA@1@Z; `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,void *)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x180017ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ca7  test    eax, eax
0x180017ca9  jnz     short loc_180017CC0
0x180017cab  mov     r9, rdi; void *
0x180017cae  lea     rcx, CriticalSection; this
0x180017cb5  mov     r8, rsi; void (*)(void *)
0x180017cb8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180017cbb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180017cc0  lea     rcx, stru_1800292A8; SRWLock
0x180017cc7  call    cs:__imp_ReleaseSRWLockExclusive
0x180017ccd  mov     rbx, [rsp+38h+arg_0]
0x180017cd2  mov     rsi, [rsp+38h+arg_8]
0x180017cd7  add     rsp, 30h
0x180017cdb  pop     rdi
0x180017cdc  retn
```
