# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180025d40`
- end: `0x180025e4d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1800258f0`
- `0x1800259ec`
- `0x180025d40`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025dca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025dca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025de1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025de1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025d90`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025d90`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025e37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025e37`

## string_xrefs

- `0x180025dc3`: `ntdll.dll`
- `0x180025dd7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_18003B120 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18003B120 = 0;
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
               &qword_18003B120);
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
0x180025d40  mov     [rsp+arg_0], rbx
0x180025d45  mov     [rsp+arg_8], rsi
0x180025d4a  push    rdi
0x180025d4b  sub     rsp, 30h
0x180025d4f  mov     rdi, r8
0x180025d52  mov     rsi, rdx
0x180025d55  mov     rbx, rcx
0x180025d58  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180025d5c  jnz     short loc_180025D75
0x180025d5e  mov     r8, rdx; void (*)(void *)
0x180025d61  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180025d64  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180025d6b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180025d70  jmp     loc_180025E3D
0x180025d75  mov     qword ptr [rcx], 0
0x180025d7c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180025d83  jz      loc_180025E3D
0x180025d89  lea     rcx, SRWLock; SRWLock
0x180025d90  call    cs:__imp_AcquireSRWLockExclusive
0x180025d96  cmp     cs:qword_18003B120, 0
0x180025d9e  jnz     short loc_180025E1B
0x180025da0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180025da7  mov     cs:qword_18003B120, 0
0x180025db2  test    rax, rax
0x180025db5  jnz     short loc_180025DFA
0x180025db7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180025dbe  test    rax, rax
0x180025dc1  jnz     short loc_180025DD7
0x180025dc3  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180025dca  call    cs:__imp_GetModuleHandleW
0x180025dd0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180025dd7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180025dde  mov     rcx, rax; hModule
0x180025de1  call    cs:__imp_GetProcAddress
0x180025de7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180025dee  test    rax, rax
0x180025df1  jnz     short loc_180025DFA
0x180025df3  mov     eax, 0C0000139h
0x180025df8  jmp     short loc_180025E17
0x180025dfa  lea     r9, qword_18003B120
0x180025e01  xor     r8d, r8d
0x180025e04  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180025e0b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToStateChangesUnderLock@FeatureStateManager@details@wil@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@5@PEAX@Z@SA@1@Z; `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,void *)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x180025e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e17  test    eax, eax
0x180025e19  jnz     short loc_180025E30
0x180025e1b  mov     r9, rdi; void *
0x180025e1e  lea     rcx, CriticalSection; this
0x180025e25  mov     r8, rsi; void (*)(void *)
0x180025e28  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180025e2b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180025e30  lea     rcx, SRWLock; SRWLock
0x180025e37  call    cs:__imp_ReleaseSRWLockExclusive
0x180025e3d  mov     rbx, [rsp+38h+arg_0]
0x180025e42  mov     rsi, [rsp+38h+arg_8]
0x180025e47  add     rsp, 30h
0x180025e4b  pop     rdi
0x180025e4c  retn
```
