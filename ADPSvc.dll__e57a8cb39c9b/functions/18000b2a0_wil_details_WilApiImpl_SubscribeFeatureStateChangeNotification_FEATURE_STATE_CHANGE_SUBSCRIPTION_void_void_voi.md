# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000b2a0`
- end: `0x18000b3ad`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000adcc`
- `0x18000aec8`
- `0x18000b2a0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b32a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b32a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b341`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b341`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b397`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b397`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b2f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b2f0`

## string_xrefs

- `0x18000b323`: `ntdll.dll`
- `0x18000b337`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_18010E600);
      if ( qword_18010E670 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18010E670 = 0;
      if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification )
        goto LABEL_10;
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "RtlRegisterFeatureConfigurationChangeNotification");
      g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_10:
        v9 = ((__int64 (__fastcall *)(void (__fastcall *)(__int64), void *, _QWORD, __int64 *))ProcAddress)(
               `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
               &wil::details::g_featureStateManager,
               0,
               &qword_18010E670);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_18010E600);
    }
  }
}

```

## disassembly

```asm
0x18000b2a0  mov     [rsp+arg_0], rbx
0x18000b2a5  mov     [rsp+arg_8], rsi
0x18000b2aa  push    rdi
0x18000b2ab  sub     rsp, 30h
0x18000b2af  mov     rdi, r8
0x18000b2b2  mov     rsi, rdx
0x18000b2b5  mov     rbx, rcx
0x18000b2b8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000b2bc  jnz     short loc_18000B2D5
0x18000b2be  mov     r8, rdx; void (*)(void *)
0x18000b2c1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000b2c4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000b2cb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000b2d0  jmp     loc_18000B39D
0x18000b2d5  mov     qword ptr [rcx], 0
0x18000b2dc  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000b2e3  jz      loc_18000B39D
0x18000b2e9  lea     rcx, stru_18010E600; SRWLock
0x18000b2f0  call    cs:__imp_AcquireSRWLockExclusive
0x18000b2f6  cmp     cs:qword_18010E670, 0
0x18000b2fe  jnz     short loc_18000B37B
0x18000b300  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000b307  mov     cs:qword_18010E670, 0
0x18000b312  test    rax, rax
0x18000b315  jnz     short loc_18000B35A
0x18000b317  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b31e  test    rax, rax
0x18000b321  jnz     short loc_18000B337
0x18000b323  lea     rcx, ModuleName; "ntdll.dll"
0x18000b32a  call    cs:__imp_GetModuleHandleW
0x18000b330  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b337  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000b33e  mov     rcx, rax; hModule
0x18000b341  call    cs:__imp_GetProcAddress
0x18000b347  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000b34e  test    rax, rax
0x18000b351  jnz     short loc_18000B35A
0x18000b353  mov     eax, 0C0000139h
0x18000b358  jmp     short loc_18000B377
0x18000b35a  lea     r9, qword_18010E670
0x18000b361  xor     r8d, r8d
0x18000b364  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000b36b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToStateChangesUnderLock@FeatureStateManager@details@wil@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@5@PEAX@Z@SA@1@Z; `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,void *)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x18000b372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b377  test    eax, eax
0x18000b379  jnz     short loc_18000B390
0x18000b37b  mov     r9, rdi; void *
0x18000b37e  lea     rcx, CriticalSection; this
0x18000b385  mov     r8, rsi; void (*)(void *)
0x18000b388  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000b38b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000b390  lea     rcx, stru_18010E600; SRWLock
0x18000b397  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b39d  mov     rbx, [rsp+38h+arg_0]
0x18000b3a2  mov     rsi, [rsp+38h+arg_8]
0x18000b3a7  add     rsp, 30h
0x18000b3ab  pop     rdi
0x18000b3ac  retn
```
