# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1800ec150`
- end: `0x1800ec25d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1800eb88c`
- `0x1800eb988`
- `0x1800ec150`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ec1f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ec1f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ec1da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ec1da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ec1a0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ec1a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ec247`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ec247`

## string_xrefs

- `0x1800ec1d3`: `ntdll.dll`
- `0x1800ec1e7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_18013F628);
      if ( qword_18013F698 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18013F698 = 0;
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
               &qword_18013F698);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_18013F628);
    }
  }
}

```

## disassembly

```asm
0x1800ec150  mov     [rsp+arg_0], rbx
0x1800ec155  mov     [rsp+arg_8], rsi
0x1800ec15a  push    rdi
0x1800ec15b  sub     rsp, 30h
0x1800ec15f  mov     rdi, r8
0x1800ec162  mov     rsi, rdx
0x1800ec165  mov     rbx, rcx
0x1800ec168  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800ec16c  jnz     short loc_1800EC185
0x1800ec16e  mov     r8, rdx; void (*)(void *)
0x1800ec171  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800ec174  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800ec17b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x1800ec180  jmp     loc_1800EC24D
0x1800ec185  mov     qword ptr [rcx], 0
0x1800ec18c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800ec193  jz      loc_1800EC24D
0x1800ec199  lea     rcx, stru_18013F628; SRWLock
0x1800ec1a0  call    cs:__imp_AcquireSRWLockExclusive
0x1800ec1a6  cmp     cs:qword_18013F698, 0
0x1800ec1ae  jnz     short loc_1800EC22B
0x1800ec1b0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800ec1b7  mov     cs:qword_18013F698, 0
0x1800ec1c2  test    rax, rax
0x1800ec1c5  jnz     short loc_1800EC20A
0x1800ec1c7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800ec1ce  test    rax, rax
0x1800ec1d1  jnz     short loc_1800EC1E7
0x1800ec1d3  lea     rcx, ModuleName; "ntdll.dll"
0x1800ec1da  call    cs:__imp_GetModuleHandleW
0x1800ec1e0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800ec1e7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800ec1ee  mov     rcx, rax; hModule
0x1800ec1f1  call    cs:__imp_GetProcAddress
0x1800ec1f7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800ec1fe  test    rax, rax
0x1800ec201  jnz     short loc_1800EC20A
0x1800ec203  mov     eax, 0C0000139h
0x1800ec208  jmp     short loc_1800EC227
0x1800ec20a  lea     r9, qword_18013F698
0x1800ec211  xor     r8d, r8d
0x1800ec214  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800ec21b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800ec222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec227  test    eax, eax
0x1800ec229  jnz     short loc_1800EC240
0x1800ec22b  mov     r9, rdi; void *
0x1800ec22e  lea     rcx, CriticalSection; this
0x1800ec235  mov     r8, rsi; void (*)(void *)
0x1800ec238  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800ec23b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800ec240  lea     rcx, stru_18013F628; SRWLock
0x1800ec247  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ec24d  mov     rbx, [rsp+38h+arg_0]
0x1800ec252  mov     rsi, [rsp+38h+arg_8]
0x1800ec257  add     rsp, 30h
0x1800ec25b  pop     rdi
0x1800ec25c  retn
```
