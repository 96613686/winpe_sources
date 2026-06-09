# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14000e550`
- end: `0x14000e65d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x14000dde0`
- `0x14000dedc`
- `0x14000e550`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000e5da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000e5da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e5f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e5f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000e5a0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000e5a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000e647`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000e647`

## string_xrefs

- `0x14000e5d3`: `ntdll.dll`
- `0x14000e5e7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_14001B180);
      if ( qword_14001B1F0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_14001B1F0 = 0;
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
               &qword_14001B1F0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_14001B180);
    }
  }
}

```

## disassembly

```asm
0x14000e550  mov     [rsp+arg_0], rbx
0x14000e555  mov     [rsp+arg_8], rsi
0x14000e55a  push    rdi
0x14000e55b  sub     rsp, 30h
0x14000e55f  mov     rdi, r8
0x14000e562  mov     rsi, rdx
0x14000e565  mov     rbx, rcx
0x14000e568  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14000e56c  jnz     short loc_14000E585
0x14000e56e  mov     r8, rdx; void (*)(void *)
0x14000e571  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000e574  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000e57b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x14000e580  jmp     loc_14000E64D
0x14000e585  mov     qword ptr [rcx], 0
0x14000e58c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000e593  jz      loc_14000E64D
0x14000e599  lea     rcx, stru_14001B180; SRWLock
0x14000e5a0  call    cs:__imp_AcquireSRWLockExclusive
0x14000e5a6  cmp     cs:qword_14001B1F0, 0
0x14000e5ae  jnz     short loc_14000E62B
0x14000e5b0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000e5b7  mov     cs:qword_14001B1F0, 0
0x14000e5c2  test    rax, rax
0x14000e5c5  jnz     short loc_14000E60A
0x14000e5c7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000e5ce  test    rax, rax
0x14000e5d1  jnz     short loc_14000E5E7
0x14000e5d3  lea     rcx, aNtdllDll; "ntdll.dll"
0x14000e5da  call    cs:__imp_GetModuleHandleW
0x14000e5e0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000e5e7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000e5ee  mov     rcx, rax; hModule
0x14000e5f1  call    cs:__imp_GetProcAddress
0x14000e5f7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000e5fe  test    rax, rax
0x14000e601  jnz     short loc_14000E60A
0x14000e603  mov     eax, 0C0000139h
0x14000e608  jmp     short loc_14000E627
0x14000e60a  lea     r9, qword_14001B1F0
0x14000e611  xor     r8d, r8d
0x14000e614  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000e61b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x14000e622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e627  test    eax, eax
0x14000e629  jnz     short loc_14000E640
0x14000e62b  mov     r9, rdi; void *
0x14000e62e  lea     rcx, CriticalSection; this
0x14000e635  mov     r8, rsi; void (*)(void *)
0x14000e638  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000e63b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x14000e640  lea     rcx, stru_14001B180; SRWLock
0x14000e647  call    cs:__imp_ReleaseSRWLockExclusive
0x14000e64d  mov     rbx, [rsp+38h+arg_0]
0x14000e652  mov     rsi, [rsp+38h+arg_8]
0x14000e657  add     rsp, 30h
0x14000e65b  pop     rdi
0x14000e65c  retn
```
