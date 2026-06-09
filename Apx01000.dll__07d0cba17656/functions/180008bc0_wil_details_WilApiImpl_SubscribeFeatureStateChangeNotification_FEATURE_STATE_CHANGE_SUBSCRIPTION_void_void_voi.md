# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180008bc0`
- end: `0x180008ccd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180008450`
- `0x18000854c`
- `0x180008bc0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008c4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008c4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008c61`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008c61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008cb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008cb7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008c10`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008c10`

## string_xrefs

- `0x180008c43`: `ntdll.dll`
- `0x180008c57`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180033060);
      if ( qword_1800330D0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800330D0 = 0;
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
               &qword_1800330D0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180033060);
    }
  }
}

```

## disassembly

```asm
0x180008bc0  mov     [rsp+arg_0], rbx
0x180008bc5  mov     [rsp+arg_8], rsi
0x180008bca  push    rdi
0x180008bcb  sub     rsp, 30h
0x180008bcf  mov     rdi, r8
0x180008bd2  mov     rsi, rdx
0x180008bd5  mov     rbx, rcx
0x180008bd8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180008bdc  jnz     short loc_180008BF5
0x180008bde  mov     r8, rdx; void (*)(void *)
0x180008be1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180008be4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180008beb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180008bf0  jmp     loc_180008CBD
0x180008bf5  mov     qword ptr [rcx], 0
0x180008bfc  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180008c03  jz      loc_180008CBD
0x180008c09  lea     rcx, stru_180033060; SRWLock
0x180008c10  call    cs:__imp_AcquireSRWLockExclusive
0x180008c16  cmp     cs:qword_1800330D0, 0
0x180008c1e  jnz     short loc_180008C9B
0x180008c20  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180008c27  mov     cs:qword_1800330D0, 0
0x180008c32  test    rax, rax
0x180008c35  jnz     short loc_180008C7A
0x180008c37  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008c3e  test    rax, rax
0x180008c41  jnz     short loc_180008C57
0x180008c43  lea     rcx, ModuleName; "ntdll.dll"
0x180008c4a  call    cs:__imp_GetModuleHandleW
0x180008c50  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008c57  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180008c5e  mov     rcx, rax; hModule
0x180008c61  call    cs:__imp_GetProcAddress
0x180008c67  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180008c6e  test    rax, rax
0x180008c71  jnz     short loc_180008C7A
0x180008c73  mov     eax, 0C0000139h
0x180008c78  jmp     short loc_180008C97
0x180008c7a  lea     r9, qword_1800330D0
0x180008c81  xor     r8d, r8d
0x180008c84  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180008c8b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180008c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c97  test    eax, eax
0x180008c99  jnz     short loc_180008CB0
0x180008c9b  mov     r9, rdi; void *
0x180008c9e  lea     rcx, CriticalSection; this
0x180008ca5  mov     r8, rsi; void (*)(void *)
0x180008ca8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180008cab  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180008cb0  lea     rcx, stru_180033060; SRWLock
0x180008cb7  call    cs:__imp_ReleaseSRWLockExclusive
0x180008cbd  mov     rbx, [rsp+38h+arg_0]
0x180008cc2  mov     rsi, [rsp+38h+arg_8]
0x180008cc7  add     rsp, 30h
0x180008ccb  pop     rdi
0x180008ccc  retn
```
