# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180009af0`
- end: `0x180009bfd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000937c`
- `0x180009478`
- `0x180009af0`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180009b7a`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180009b7a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180009b91`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180009b91`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009b40`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009b40`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009be7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009be7`

## string_xrefs

- `0x180009b73`: `ntdll.dll`
- `0x180009b87`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180025410);
      if ( qword_180025480 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180025480 = 0;
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
               &qword_180025480);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180025410);
    }
  }
}

```

## disassembly

```asm
0x180009af0  mov     [rsp+arg_0], rbx
0x180009af5  mov     [rsp+arg_8], rsi
0x180009afa  push    rdi
0x180009afb  sub     rsp, 30h
0x180009aff  mov     rdi, r8
0x180009b02  mov     rsi, rdx
0x180009b05  mov     rbx, rcx
0x180009b08  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180009b0c  jnz     short loc_180009B25
0x180009b0e  mov     r8, rdx; void (*)(void *)
0x180009b11  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180009b14  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180009b1b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180009b20  jmp     loc_180009BED
0x180009b25  mov     qword ptr [rcx], 0
0x180009b2c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009b33  jz      loc_180009BED
0x180009b39  lea     rcx, stru_180025410; SRWLock
0x180009b40  call    cs:__imp_AcquireSRWLockExclusive
0x180009b46  cmp     cs:qword_180025480, 0
0x180009b4e  jnz     short loc_180009BCB
0x180009b50  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180009b57  mov     cs:qword_180025480, 0
0x180009b62  test    rax, rax
0x180009b65  jnz     short loc_180009BAA
0x180009b67  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009b6e  test    rax, rax
0x180009b71  jnz     short loc_180009B87
0x180009b73  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180009b7a  call    cs:__imp_GetModuleHandleW
0x180009b80  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009b87  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180009b8e  mov     rcx, rax; hModule
0x180009b91  call    cs:__imp_GetProcAddress
0x180009b97  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180009b9e  test    rax, rax
0x180009ba1  jnz     short loc_180009BAA
0x180009ba3  mov     eax, 0C0000139h
0x180009ba8  jmp     short loc_180009BC7
0x180009baa  lea     r9, qword_180025480
0x180009bb1  xor     r8d, r8d
0x180009bb4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009bbb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180009bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bc7  test    eax, eax
0x180009bc9  jnz     short loc_180009BE0
0x180009bcb  mov     r9, rdi; void *
0x180009bce  lea     rcx, CriticalSection; this
0x180009bd5  mov     r8, rsi; void (*)(void *)
0x180009bd8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180009bdb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180009be0  lea     rcx, stru_180025410; SRWLock
0x180009be7  call    cs:__imp_ReleaseSRWLockExclusive
0x180009bed  mov     rbx, [rsp+38h+arg_0]
0x180009bf2  mov     rsi, [rsp+38h+arg_8]
0x180009bf7  add     rsp, 30h
0x180009bfb  pop     rdi
0x180009bfc  retn
```
