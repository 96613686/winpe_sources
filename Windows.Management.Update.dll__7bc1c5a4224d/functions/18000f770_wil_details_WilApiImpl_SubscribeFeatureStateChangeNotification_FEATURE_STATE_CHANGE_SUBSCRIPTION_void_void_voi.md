# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000f770`
- end: `0x18000f87d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000efe0`
- `0x18000f0dc`
- `0x18000f770`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f7fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f7fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f811`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f811`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f7c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f7c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f867`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f867`

## string_xrefs

- `0x18000f7f3`: `ntdll.dll`
- `0x18000f807`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_18003A088);
      if ( qword_18003A0F8 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18003A0F8 = 0;
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
        v9 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), void *, _QWORD, __int64 *))ProcAddress)(
               _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
               &wil::details::g_featureStateManager,
               0,
               &qword_18003A0F8);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_18003A088);
    }
  }
}

```

## disassembly

```asm
0x18000f770  mov     [rsp+arg_0], rbx
0x18000f775  mov     [rsp+arg_8], rsi
0x18000f77a  push    rdi
0x18000f77b  sub     rsp, 30h
0x18000f77f  mov     rdi, r8
0x18000f782  mov     rsi, rdx
0x18000f785  mov     rbx, rcx
0x18000f788  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000f78c  jnz     short loc_18000F7A5
0x18000f78e  mov     r8, rdx; void (*)(void *)
0x18000f791  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000f794  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000f79b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000f7a0  jmp     loc_18000F86D
0x18000f7a5  mov     qword ptr [rcx], 0
0x18000f7ac  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000f7b3  jz      loc_18000F86D
0x18000f7b9  lea     rcx, stru_18003A088; SRWLock
0x18000f7c0  call    cs:__imp_AcquireSRWLockExclusive
0x18000f7c6  cmp     cs:qword_18003A0F8, 0
0x18000f7ce  jnz     short loc_18000F84B
0x18000f7d0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000f7d7  mov     cs:qword_18003A0F8, 0
0x18000f7e2  test    rax, rax
0x18000f7e5  jnz     short loc_18000F82A
0x18000f7e7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f7ee  test    rax, rax
0x18000f7f1  jnz     short loc_18000F807
0x18000f7f3  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000f7fa  call    cs:__imp_GetModuleHandleW
0x18000f800  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f807  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000f80e  mov     rcx, rax; hModule
0x18000f811  call    cs:__imp_GetProcAddress
0x18000f817  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000f81e  test    rax, rax
0x18000f821  jnz     short loc_18000F82A
0x18000f823  mov     eax, 0C0000139h
0x18000f828  jmp     short loc_18000F847
0x18000f82a  lea     r9, qword_18003A0F8
0x18000f831  xor     r8d, r8d
0x18000f834  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000f83b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000f842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f847  test    eax, eax
0x18000f849  jnz     short loc_18000F860
0x18000f84b  mov     r9, rdi; void *
0x18000f84e  lea     rcx, CriticalSection; this
0x18000f855  mov     r8, rsi; void (*)(void *)
0x18000f858  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000f85b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000f860  lea     rcx, stru_18003A088; SRWLock
0x18000f867  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f86d  mov     rbx, [rsp+38h+arg_0]
0x18000f872  mov     rsi, [rsp+38h+arg_8]
0x18000f877  add     rsp, 30h
0x18000f87b  pop     rdi
0x18000f87c  retn
```
