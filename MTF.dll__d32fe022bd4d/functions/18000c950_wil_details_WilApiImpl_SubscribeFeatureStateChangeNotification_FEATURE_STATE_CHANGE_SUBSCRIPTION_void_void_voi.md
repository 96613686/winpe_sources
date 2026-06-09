# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000c950`
- end: `0x18000ca5d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000c518`
- `0x18000c614`
- `0x18000c950`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c9f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c9f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c9da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c9da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c9a0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c9a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ca47`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ca47`

## string_xrefs

- `0x18000c9d3`: `ntdll.dll`
- `0x18000c9e7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_18003E148);
      if ( qword_18003E1B8 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18003E1B8 = 0;
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
               &qword_18003E1B8);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_18003E148);
    }
  }
}

```

## disassembly

```asm
0x18000c950  mov     [rsp+arg_0], rbx
0x18000c955  mov     [rsp+arg_8], rsi
0x18000c95a  push    rdi
0x18000c95b  sub     rsp, 30h
0x18000c95f  mov     rdi, r8
0x18000c962  mov     rsi, rdx
0x18000c965  mov     rbx, rcx
0x18000c968  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000c96c  jnz     short loc_18000C985
0x18000c96e  mov     r8, rdx; void (*)(void *)
0x18000c971  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000c974  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000c97b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000c980  jmp     loc_18000CA4D
0x18000c985  mov     qword ptr [rcx], 0
0x18000c98c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000c993  jz      loc_18000CA4D
0x18000c999  lea     rcx, stru_18003E148; SRWLock
0x18000c9a0  call    cs:__imp_AcquireSRWLockExclusive
0x18000c9a6  cmp     cs:qword_18003E1B8, 0
0x18000c9ae  jnz     short loc_18000CA2B
0x18000c9b0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000c9b7  mov     cs:qword_18003E1B8, 0
0x18000c9c2  test    rax, rax
0x18000c9c5  jnz     short loc_18000CA0A
0x18000c9c7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c9ce  test    rax, rax
0x18000c9d1  jnz     short loc_18000C9E7
0x18000c9d3  lea     rcx, ModuleName; "ntdll.dll"
0x18000c9da  call    cs:__imp_GetModuleHandleW
0x18000c9e0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c9e7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000c9ee  mov     rcx, rax; hModule
0x18000c9f1  call    cs:__imp_GetProcAddress
0x18000c9f7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000c9fe  test    rax, rax
0x18000ca01  jnz     short loc_18000CA0A
0x18000ca03  mov     eax, 0C0000139h
0x18000ca08  jmp     short loc_18000CA27
0x18000ca0a  lea     r9, qword_18003E1B8
0x18000ca11  xor     r8d, r8d
0x18000ca14  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000ca1b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000ca22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca27  test    eax, eax
0x18000ca29  jnz     short loc_18000CA40
0x18000ca2b  mov     r9, rdi; void *
0x18000ca2e  lea     rcx, CriticalSection; this
0x18000ca35  mov     r8, rsi; void (*)(void *)
0x18000ca38  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000ca3b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000ca40  lea     rcx, stru_18003E148; SRWLock
0x18000ca47  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ca4d  mov     rbx, [rsp+38h+arg_0]
0x18000ca52  mov     rsi, [rsp+38h+arg_8]
0x18000ca57  add     rsp, 30h
0x18000ca5b  pop     rdi
0x18000ca5c  retn
```
