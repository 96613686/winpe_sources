# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180008360`
- end: `0x18000846d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180007c44`
- `0x180007d40`
- `0x180008360`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008401`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008401`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800083ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800083ea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800083b0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800083b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008457`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008457`

## string_xrefs

- `0x1800083e3`: `ntdll.dll`
- `0x1800083f7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180014090 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180014090 = 0;
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
               &qword_180014090);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&SRWLock);
    }
  }
}

```

## disassembly

```asm
0x180008360  mov     [rsp+arg_0], rbx
0x180008365  mov     [rsp+arg_8], rsi
0x18000836a  push    rdi
0x18000836b  sub     rsp, 30h
0x18000836f  mov     rdi, r8
0x180008372  mov     rsi, rdx
0x180008375  mov     rbx, rcx
0x180008378  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000837c  jnz     short loc_180008395
0x18000837e  mov     r8, rdx; void (*)(void *)
0x180008381  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180008384  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000838b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180008390  jmp     loc_18000845D
0x180008395  mov     qword ptr [rcx], 0
0x18000839c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800083a3  jz      loc_18000845D
0x1800083a9  lea     rcx, SRWLock; SRWLock
0x1800083b0  call    cs:__imp_AcquireSRWLockExclusive
0x1800083b6  cmp     cs:qword_180014090, 0
0x1800083be  jnz     short loc_18000843B
0x1800083c0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800083c7  mov     cs:qword_180014090, 0
0x1800083d2  test    rax, rax
0x1800083d5  jnz     short loc_18000841A
0x1800083d7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800083de  test    rax, rax
0x1800083e1  jnz     short loc_1800083F7
0x1800083e3  lea     rcx, ModuleName; "ntdll.dll"
0x1800083ea  call    cs:__imp_GetModuleHandleW
0x1800083f0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800083f7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800083fe  mov     rcx, rax; hModule
0x180008401  call    cs:__imp_GetProcAddress
0x180008407  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000840e  test    rax, rax
0x180008411  jnz     short loc_18000841A
0x180008413  mov     eax, 0C0000139h
0x180008418  jmp     short loc_180008437
0x18000841a  lea     r9, qword_180014090
0x180008421  xor     r8d, r8d
0x180008424  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000842b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180008432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008437  test    eax, eax
0x180008439  jnz     short loc_180008450
0x18000843b  mov     r9, rdi; void *
0x18000843e  lea     rcx, CriticalSection; this
0x180008445  mov     r8, rsi; void (*)(void *)
0x180008448  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000844b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180008450  lea     rcx, SRWLock; SRWLock
0x180008457  call    cs:__imp_ReleaseSRWLockExclusive
0x18000845d  mov     rbx, [rsp+38h+arg_0]
0x180008462  mov     rsi, [rsp+38h+arg_8]
0x180008467  add     rsp, 30h
0x18000846b  pop     rdi
0x18000846c  retn
```
