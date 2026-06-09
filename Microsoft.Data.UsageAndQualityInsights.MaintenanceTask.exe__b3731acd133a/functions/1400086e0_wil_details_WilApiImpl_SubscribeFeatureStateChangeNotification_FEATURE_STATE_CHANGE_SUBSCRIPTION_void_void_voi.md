# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1400086e0`
- end: `0x1400087ed`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x140007f70`
- `0x14000806c`
- `0x1400086e0`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000876a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000876a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008781`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008781`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008730`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008730`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400087d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400087d7`

## string_xrefs

- `0x140008763`: `ntdll.dll`
- `0x140008777`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_140011020);
      if ( qword_140011090 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_140011090 = 0;
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
               &qword_140011090);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_140011020);
    }
  }
}

```

## disassembly

```asm
0x1400086e0  mov     [rsp+arg_0], rbx
0x1400086e5  mov     [rsp+arg_8], rsi
0x1400086ea  push    rdi
0x1400086eb  sub     rsp, 30h
0x1400086ef  mov     rdi, r8
0x1400086f2  mov     rsi, rdx
0x1400086f5  mov     rbx, rcx
0x1400086f8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1400086fc  jnz     short loc_140008715
0x1400086fe  mov     r8, rdx; void (*)(void *)
0x140008701  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140008704  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000870b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x140008710  jmp     loc_1400087DD
0x140008715  mov     qword ptr [rcx], 0
0x14000871c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140008723  jz      loc_1400087DD
0x140008729  lea     rcx, stru_140011020; SRWLock
0x140008730  call    cs:__imp_AcquireSRWLockExclusive
0x140008736  cmp     cs:qword_140011090, 0
0x14000873e  jnz     short loc_1400087BB
0x140008740  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140008747  mov     cs:qword_140011090, 0
0x140008752  test    rax, rax
0x140008755  jnz     short loc_14000879A
0x140008757  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000875e  test    rax, rax
0x140008761  jnz     short loc_140008777
0x140008763  lea     rcx, ModuleName; "ntdll.dll"
0x14000876a  call    cs:__imp_GetModuleHandleW
0x140008770  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008777  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000877e  mov     rcx, rax; hModule
0x140008781  call    cs:__imp_GetProcAddress
0x140008787  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000878e  test    rax, rax
0x140008791  jnz     short loc_14000879A
0x140008793  mov     eax, 0C0000139h
0x140008798  jmp     short loc_1400087B7
0x14000879a  lea     r9, qword_140011090
0x1400087a1  xor     r8d, r8d
0x1400087a4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1400087ab  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToStateChangesUnderLock@FeatureStateManager@details@wil@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@5@PEAX@Z@SA@1@Z; `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,void *)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x1400087b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400087b7  test    eax, eax
0x1400087b9  jnz     short loc_1400087D0
0x1400087bb  mov     r9, rdi; void *
0x1400087be  lea     rcx, CriticalSection; this
0x1400087c5  mov     r8, rsi; void (*)(void *)
0x1400087c8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1400087cb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1400087d0  lea     rcx, stru_140011020; SRWLock
0x1400087d7  call    cs:__imp_ReleaseSRWLockExclusive
0x1400087dd  mov     rbx, [rsp+38h+arg_0]
0x1400087e2  mov     rsi, [rsp+38h+arg_8]
0x1400087e7  add     rsp, 30h
0x1400087eb  pop     rdi
0x1400087ec  retn
```
