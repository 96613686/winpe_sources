# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180008d60`
- end: `0x180008e6d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1800085f0`
- `0x1800086ec`
- `0x180008d60`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008e01`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008e01`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008dea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008dea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008e57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008e57`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008db0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008db0`

## string_xrefs

- `0x180008de3`: `ntdll.dll`
- `0x180008df7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_18001F080);
      if ( qword_18001F0F0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18001F0F0 = 0;
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
        v9 = ((__int64 (__fastcall *)(void (__fastcall *)(__int64), char *, _QWORD, __int64 *))ProcAddress)(
               `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
               &wil::details::g_featureStateManager,
               0,
               &qword_18001F0F0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_18001F080);
    }
  }
}

```

## disassembly

```asm
0x180008d60  mov     [rsp+arg_0], rbx
0x180008d65  mov     [rsp+arg_8], rsi
0x180008d6a  push    rdi
0x180008d6b  sub     rsp, 30h
0x180008d6f  mov     rdi, r8
0x180008d72  mov     rsi, rdx
0x180008d75  mov     rbx, rcx
0x180008d78  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180008d7c  jnz     short loc_180008D95
0x180008d7e  mov     r8, rdx; void (*)(void *)
0x180008d81  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180008d84  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180008d8b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180008d90  jmp     loc_180008E5D
0x180008d95  mov     qword ptr [rcx], 0
0x180008d9c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180008da3  jz      loc_180008E5D
0x180008da9  lea     rcx, stru_18001F080; SRWLock
0x180008db0  call    cs:__imp_AcquireSRWLockExclusive
0x180008db6  cmp     cs:qword_18001F0F0, 0
0x180008dbe  jnz     short loc_180008E3B
0x180008dc0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180008dc7  mov     cs:qword_18001F0F0, 0
0x180008dd2  test    rax, rax
0x180008dd5  jnz     short loc_180008E1A
0x180008dd7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008dde  test    rax, rax
0x180008de1  jnz     short loc_180008DF7
0x180008de3  lea     rcx, ModuleName; "ntdll.dll"
0x180008dea  call    cs:__imp_GetModuleHandleW
0x180008df0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008df7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180008dfe  mov     rcx, rax; hModule
0x180008e01  call    cs:__imp_GetProcAddress
0x180008e07  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180008e0e  test    rax, rax
0x180008e11  jnz     short loc_180008E1A
0x180008e13  mov     eax, 0C0000139h
0x180008e18  jmp     short loc_180008E37
0x180008e1a  lea     r9, qword_18001F0F0
0x180008e21  xor     r8d, r8d
0x180008e24  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180008e2b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToStateChangesUnderLock@FeatureStateManager@details@wil@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@5@PEAX@Z@SA@1@Z; `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,void *)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x180008e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e37  test    eax, eax
0x180008e39  jnz     short loc_180008E50
0x180008e3b  mov     r9, rdi; void *
0x180008e3e  lea     rcx, CriticalSection; this
0x180008e45  mov     r8, rsi; void (*)(void *)
0x180008e48  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180008e4b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180008e50  lea     rcx, stru_18001F080; SRWLock
0x180008e57  call    cs:__imp_ReleaseSRWLockExclusive
0x180008e5d  mov     rbx, [rsp+38h+arg_0]
0x180008e62  mov     rsi, [rsp+38h+arg_8]
0x180008e67  add     rsp, 30h
0x180008e6b  pop     rdi
0x180008e6c  retn
```
