# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14000e730`
- end: `0x14000e83d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x14000e2d4`
- `0x14000e3d0`
- `0x14000e730`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e7d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e7d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000e7ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000e7ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000e827`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000e827`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000e780`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000e780`

## string_xrefs

- `0x14000e7b3`: `ntdll.dll`
- `0x14000e7c7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_140020148 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_140020148 = 0;
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
               &qword_140020148);
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
0x14000e730  mov     [rsp+arg_0], rbx
0x14000e735  mov     [rsp+arg_8], rsi
0x14000e73a  push    rdi
0x14000e73b  sub     rsp, 30h
0x14000e73f  mov     rdi, r8
0x14000e742  mov     rsi, rdx
0x14000e745  mov     rbx, rcx
0x14000e748  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14000e74c  jnz     short loc_14000E765
0x14000e74e  mov     r8, rdx; void (*)(void *)
0x14000e751  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000e754  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000e75b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x14000e760  jmp     loc_14000E82D
0x14000e765  mov     qword ptr [rcx], 0
0x14000e76c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000e773  jz      loc_14000E82D
0x14000e779  lea     rcx, SRWLock; SRWLock
0x14000e780  call    cs:__imp_AcquireSRWLockExclusive
0x14000e786  cmp     cs:qword_140020148, 0
0x14000e78e  jnz     short loc_14000E80B
0x14000e790  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000e797  mov     cs:qword_140020148, 0
0x14000e7a2  test    rax, rax
0x14000e7a5  jnz     short loc_14000E7EA
0x14000e7a7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000e7ae  test    rax, rax
0x14000e7b1  jnz     short loc_14000E7C7
0x14000e7b3  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000e7ba  call    cs:__imp_GetModuleHandleW
0x14000e7c0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000e7c7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000e7ce  mov     rcx, rax; hModule
0x14000e7d1  call    cs:__imp_GetProcAddress
0x14000e7d7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000e7de  test    rax, rax
0x14000e7e1  jnz     short loc_14000E7EA
0x14000e7e3  mov     eax, 0C0000139h
0x14000e7e8  jmp     short loc_14000E807
0x14000e7ea  lea     r9, qword_140020148
0x14000e7f1  xor     r8d, r8d
0x14000e7f4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000e7fb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x14000e802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e807  test    eax, eax
0x14000e809  jnz     short loc_14000E820
0x14000e80b  mov     r9, rdi; void *
0x14000e80e  lea     rcx, CriticalSection; this
0x14000e815  mov     r8, rsi; void (*)(void *)
0x14000e818  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000e81b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x14000e820  lea     rcx, SRWLock; SRWLock
0x14000e827  call    cs:__imp_ReleaseSRWLockExclusive
0x14000e82d  mov     rbx, [rsp+38h+arg_0]
0x14000e832  mov     rsi, [rsp+38h+arg_8]
0x14000e837  add     rsp, 30h
0x14000e83b  pop     rdi
0x14000e83c  retn
```
