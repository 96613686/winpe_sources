# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18001d7c0`
- end: `0x18001d8be`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `254`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18001c754`
- `0x18001c858`
- `0x18001d7c0`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d843`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d843`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d85a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d85a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d809`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d809`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d8b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d8b0`

## string_xrefs

- `0x18001d83c`: `ntdll.dll`
- `0x18001d850`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_18007D0A8);
      if ( qword_18007D118 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18007D118 = 0;
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
               &qword_18007D118);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_18007D0A8);
    }
  }
}

```

## disassembly

```asm
0x18001d7c0  push    rbx
0x18001d7c2  push    rsi
0x18001d7c3  push    rdi
0x18001d7c4  sub     rsp, 30h
0x18001d7c8  mov     rsi, r8
0x18001d7cb  mov     rdi, rdx
0x18001d7ce  mov     rbx, rcx
0x18001d7d1  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001d7d5  jnz     short loc_18001D7EE
0x18001d7d7  mov     r8, rdx; void (*)(void *)
0x18001d7da  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18001d7dd  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001d7e4  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18001d7e9  jmp     loc_18001D8B6
0x18001d7ee  mov     qword ptr [rcx], 0
0x18001d7f5  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001d7fc  jz      loc_18001D8B6
0x18001d802  lea     rcx, stru_18007D0A8; SRWLock
0x18001d809  call    cs:__imp_AcquireSRWLockExclusive
0x18001d80f  cmp     cs:qword_18007D118, 0
0x18001d817  jnz     short loc_18001D894
0x18001d819  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001d820  mov     cs:qword_18007D118, 0
0x18001d82b  test    rax, rax
0x18001d82e  jnz     short loc_18001D873
0x18001d830  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001d837  test    rax, rax
0x18001d83a  jnz     short loc_18001D850
0x18001d83c  lea     rcx, aNtdllDll_2; "ntdll.dll"
0x18001d843  call    cs:__imp_GetModuleHandleW
0x18001d849  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001d850  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001d857  mov     rcx, rax; hModule
0x18001d85a  call    cs:__imp_GetProcAddress
0x18001d860  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001d867  test    rax, rax
0x18001d86a  jnz     short loc_18001D873
0x18001d86c  mov     eax, 0C0000139h
0x18001d871  jmp     short loc_18001D890
0x18001d873  lea     r9, qword_18007D118
0x18001d87a  xor     r8d, r8d
0x18001d87d  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001d884  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18001d88b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d890  test    eax, eax
0x18001d892  jnz     short loc_18001D8A9
0x18001d894  mov     r9, rsi; void *
0x18001d897  lea     rcx, CriticalSection; this
0x18001d89e  mov     r8, rdi; void (*)(void *)
0x18001d8a1  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18001d8a4  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18001d8a9  lea     rcx, stru_18007D0A8; SRWLock
0x18001d8b0  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d8b6  add     rsp, 30h
0x18001d8ba  pop     rdi
0x18001d8bb  pop     rsi
0x18001d8bc  pop     rbx
0x18001d8bd  retn
```
