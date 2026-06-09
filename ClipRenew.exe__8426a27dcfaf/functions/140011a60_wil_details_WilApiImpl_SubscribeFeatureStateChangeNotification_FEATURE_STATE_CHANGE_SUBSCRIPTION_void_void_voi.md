# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x140011a60`
- end: `0x140011b6d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1400115a8`
- `0x1400116a4`
- `0x140011a60`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140011b01`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140011b01`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140011aea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140011aea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140011b57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140011b57`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140011ab0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140011ab0`

## string_xrefs

- `0x140011ae3`: `ntdll.dll`
- `0x140011af7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_140019070);
      if ( qword_1400190E0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1400190E0 = 0;
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
        v9 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), char *, _QWORD, __int64 *))ProcAddress)(
               _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
               &wil::details::g_featureStateManager,
               0,
               &qword_1400190E0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_140019070);
    }
  }
}

```

## disassembly

```asm
0x140011a60  mov     [rsp+arg_0], rbx
0x140011a65  mov     [rsp+arg_8], rsi
0x140011a6a  push    rdi
0x140011a6b  sub     rsp, 30h
0x140011a6f  mov     rdi, r8
0x140011a72  mov     rsi, rdx
0x140011a75  mov     rbx, rcx
0x140011a78  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140011a7c  jnz     short loc_140011A95
0x140011a7e  mov     r8, rdx; void (*)(void *)
0x140011a81  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140011a84  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x140011a8b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x140011a90  jmp     loc_140011B5D
0x140011a95  mov     qword ptr [rcx], 0
0x140011a9c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140011aa3  jz      loc_140011B5D
0x140011aa9  lea     rcx, stru_140019070; SRWLock
0x140011ab0  call    cs:__imp_AcquireSRWLockExclusive
0x140011ab6  cmp     cs:qword_1400190E0, 0
0x140011abe  jnz     short loc_140011B3B
0x140011ac0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140011ac7  mov     cs:qword_1400190E0, 0
0x140011ad2  test    rax, rax
0x140011ad5  jnz     short loc_140011B1A
0x140011ad7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140011ade  test    rax, rax
0x140011ae1  jnz     short loc_140011AF7
0x140011ae3  lea     rcx, ModuleName; "ntdll.dll"
0x140011aea  call    cs:__imp_GetModuleHandleW
0x140011af0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140011af7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x140011afe  mov     rcx, rax; hModule
0x140011b01  call    cs:__imp_GetProcAddress
0x140011b07  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x140011b0e  test    rax, rax
0x140011b11  jnz     short loc_140011B1A
0x140011b13  mov     eax, 0C0000139h
0x140011b18  jmp     short loc_140011B37
0x140011b1a  lea     r9, qword_1400190E0
0x140011b21  xor     r8d, r8d
0x140011b24  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140011b2b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x140011b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011b37  test    eax, eax
0x140011b39  jnz     short loc_140011B50
0x140011b3b  mov     r9, rdi; void *
0x140011b3e  lea     rcx, CriticalSection; this
0x140011b45  mov     r8, rsi; void (*)(void *)
0x140011b48  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140011b4b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x140011b50  lea     rcx, stru_140019070; SRWLock
0x140011b57  call    cs:__imp_ReleaseSRWLockExclusive
0x140011b5d  mov     rbx, [rsp+38h+arg_0]
0x140011b62  mov     rsi, [rsp+38h+arg_8]
0x140011b67  add     rsp, 30h
0x140011b6b  pop     rdi
0x140011b6c  retn
```
