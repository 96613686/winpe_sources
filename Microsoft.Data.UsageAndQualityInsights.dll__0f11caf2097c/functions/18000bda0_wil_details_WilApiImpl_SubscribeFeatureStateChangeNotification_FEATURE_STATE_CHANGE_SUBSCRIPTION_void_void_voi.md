# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000bda0`
- end: `0x18000bead`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000b52c`
- `0x18000b628`
- `0x18000bda0`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000be2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000be2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000be41`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000be41`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bdf0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bdf0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000be97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000be97`

## string_xrefs

- `0x18000be23`: `ntdll.dll`
- `0x18000be37`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180158660);
      if ( qword_1801586D0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1801586D0 = 0;
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
               &qword_1801586D0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180158660);
    }
  }
}

```

## disassembly

```asm
0x18000bda0  mov     [rsp+arg_0], rbx
0x18000bda5  mov     [rsp+arg_8], rsi
0x18000bdaa  push    rdi
0x18000bdab  sub     rsp, 30h
0x18000bdaf  mov     rdi, r8
0x18000bdb2  mov     rsi, rdx
0x18000bdb5  mov     rbx, rcx
0x18000bdb8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000bdbc  jnz     short loc_18000BDD5
0x18000bdbe  mov     r8, rdx; void (*)(void *)
0x18000bdc1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000bdc4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000bdcb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000bdd0  jmp     loc_18000BE9D
0x18000bdd5  mov     qword ptr [rcx], 0
0x18000bddc  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000bde3  jz      loc_18000BE9D
0x18000bde9  lea     rcx, stru_180158660; SRWLock
0x18000bdf0  call    cs:__imp_AcquireSRWLockExclusive
0x18000bdf6  cmp     cs:qword_1801586D0, 0
0x18000bdfe  jnz     short loc_18000BE7B
0x18000be00  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000be07  mov     cs:qword_1801586D0, 0
0x18000be12  test    rax, rax
0x18000be15  jnz     short loc_18000BE5A
0x18000be17  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000be1e  test    rax, rax
0x18000be21  jnz     short loc_18000BE37
0x18000be23  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000be2a  call    cs:__imp_GetModuleHandleW
0x18000be30  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000be37  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000be3e  mov     rcx, rax; hModule
0x18000be41  call    cs:__imp_GetProcAddress
0x18000be47  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000be4e  test    rax, rax
0x18000be51  jnz     short loc_18000BE5A
0x18000be53  mov     eax, 0C0000139h
0x18000be58  jmp     short loc_18000BE77
0x18000be5a  lea     r9, qword_1801586D0
0x18000be61  xor     r8d, r8d
0x18000be64  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000be6b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToStateChangesUnderLock@FeatureStateManager@details@wil@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@5@PEAX@Z@SA@1@Z; `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,void *)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x18000be72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be77  test    eax, eax
0x18000be79  jnz     short loc_18000BE90
0x18000be7b  mov     r9, rdi; void *
0x18000be7e  lea     rcx, CriticalSection; this
0x18000be85  mov     r8, rsi; void (*)(void *)
0x18000be88  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000be8b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000be90  lea     rcx, stru_180158660; SRWLock
0x18000be97  call    cs:__imp_ReleaseSRWLockExclusive
0x18000be9d  mov     rbx, [rsp+38h+arg_0]
0x18000bea2  mov     rsi, [rsp+38h+arg_8]
0x18000bea7  add     rsp, 30h
0x18000beab  pop     rdi
0x18000beac  retn
```
