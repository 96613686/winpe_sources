# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18002f6c0`
- end: `0x18002f7cd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18002ef50`
- `0x18002f04c`
- `0x18002f6c0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f761`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f761`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f74a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f74a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f7b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002f7b7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002f710`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002f710`

## string_xrefs

- `0x18002f743`: `ntdll.dll`
- `0x18002f757`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_1800460A0);
      if ( qword_180046110 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180046110 = 0;
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
               &qword_180046110);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_1800460A0);
    }
  }
}

```

## disassembly

```asm
0x18002f6c0  mov     [rsp+arg_0], rbx
0x18002f6c5  mov     [rsp+arg_8], rsi
0x18002f6ca  push    rdi
0x18002f6cb  sub     rsp, 30h
0x18002f6cf  mov     rdi, r8
0x18002f6d2  mov     rsi, rdx
0x18002f6d5  mov     rbx, rcx
0x18002f6d8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18002f6dc  jnz     short loc_18002F6F5
0x18002f6de  mov     r8, rdx; void (*)(void *)
0x18002f6e1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18002f6e4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18002f6eb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18002f6f0  jmp     loc_18002F7BD
0x18002f6f5  mov     qword ptr [rcx], 0
0x18002f6fc  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18002f703  jz      loc_18002F7BD
0x18002f709  lea     rcx, stru_1800460A0; SRWLock
0x18002f710  call    cs:__imp_AcquireSRWLockExclusive
0x18002f716  cmp     cs:qword_180046110, 0
0x18002f71e  jnz     short loc_18002F79B
0x18002f720  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18002f727  mov     cs:qword_180046110, 0
0x18002f732  test    rax, rax
0x18002f735  jnz     short loc_18002F77A
0x18002f737  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002f73e  test    rax, rax
0x18002f741  jnz     short loc_18002F757
0x18002f743  lea     rcx, ModuleName; "ntdll.dll"
0x18002f74a  call    cs:__imp_GetModuleHandleW
0x18002f750  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002f757  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18002f75e  mov     rcx, rax; hModule
0x18002f761  call    cs:__imp_GetProcAddress
0x18002f767  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18002f76e  test    rax, rax
0x18002f771  jnz     short loc_18002F77A
0x18002f773  mov     eax, 0C0000139h
0x18002f778  jmp     short loc_18002F797
0x18002f77a  lea     r9, qword_180046110
0x18002f781  xor     r8d, r8d
0x18002f784  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18002f78b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18002f792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f797  test    eax, eax
0x18002f799  jnz     short loc_18002F7B0
0x18002f79b  mov     r9, rdi; void *
0x18002f79e  lea     rcx, CriticalSection; this
0x18002f7a5  mov     r8, rsi; void (*)(void *)
0x18002f7a8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18002f7ab  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18002f7b0  lea     rcx, stru_1800460A0; SRWLock
0x18002f7b7  call    cs:__imp_ReleaseSRWLockExclusive
0x18002f7bd  mov     rbx, [rsp+38h+arg_0]
0x18002f7c2  mov     rsi, [rsp+38h+arg_8]
0x18002f7c7  add     rsp, 30h
0x18002f7cb  pop     rdi
0x18002f7cc  retn
```
