# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18001ce60`
- end: `0x18001cf6d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18001c86c`
- `0x18001c970`
- `0x18001ce60`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cf01`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cf01`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ceea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ceea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cf57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cf57`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ceb0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ceb0`

## string_xrefs

- `0x18001cee3`: `ntdll.dll`
- `0x18001cef7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_1800370A0);
      if ( qword_180037110 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180037110 = 0;
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
        v9 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), void *, _QWORD, __int64 *))ProcAddress)(
               _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
               &wil::details::g_featureStateManager,
               0,
               &qword_180037110);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_1800370A0);
    }
  }
}

```

## disassembly

```asm
0x18001ce60  mov     [rsp+arg_8], rbx
0x18001ce65  mov     [rsp+arg_10], rsi
0x18001ce6a  push    rdi
0x18001ce6b  sub     rsp, 30h
0x18001ce6f  mov     rsi, r8
0x18001ce72  mov     rdi, rdx
0x18001ce75  mov     rbx, rcx
0x18001ce78  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001ce7c  jnz     short loc_18001CE95
0x18001ce7e  mov     r8, rdx; void (*)(void *)
0x18001ce81  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18001ce84  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001ce8b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18001ce90  jmp     loc_18001CF5D
0x18001ce95  mov     qword ptr [rcx], 0
0x18001ce9c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001cea3  jz      loc_18001CF5D
0x18001cea9  lea     rcx, stru_1800370A0; SRWLock
0x18001ceb0  call    cs:__imp_AcquireSRWLockExclusive
0x18001ceb6  cmp     cs:qword_180037110, 0
0x18001cebe  jnz     short loc_18001CF3B
0x18001cec0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001cec7  mov     cs:qword_180037110, 0
0x18001ced2  test    rax, rax
0x18001ced5  jnz     short loc_18001CF1A
0x18001ced7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001cede  test    rax, rax
0x18001cee1  jnz     short loc_18001CEF7
0x18001cee3  lea     rcx, ModuleName; "ntdll.dll"
0x18001ceea  call    cs:__imp_GetModuleHandleW
0x18001cef0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001cef7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001cefe  mov     rcx, rax; hModule
0x18001cf01  call    cs:__imp_GetProcAddress
0x18001cf07  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001cf0e  test    rax, rax
0x18001cf11  jnz     short loc_18001CF1A
0x18001cf13  mov     eax, 0C0000139h
0x18001cf18  jmp     short loc_18001CF37
0x18001cf1a  lea     r9, qword_180037110
0x18001cf21  xor     r8d, r8d
0x18001cf24  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001cf2b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18001cf32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf37  test    eax, eax
0x18001cf39  jnz     short loc_18001CF50
0x18001cf3b  mov     r9, rsi; void *
0x18001cf3e  lea     rcx, CriticalSection; this
0x18001cf45  mov     r8, rdi; void (*)(void *)
0x18001cf48  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18001cf4b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18001cf50  lea     rcx, stru_1800370A0; SRWLock
0x18001cf57  call    cs:__imp_ReleaseSRWLockExclusive
0x18001cf5d  mov     rbx, [rsp+38h+arg_8]
0x18001cf62  mov     rsi, [rsp+38h+arg_10]
0x18001cf67  add     rsp, 30h
0x18001cf6b  pop     rdi
0x18001cf6c  retn
```
