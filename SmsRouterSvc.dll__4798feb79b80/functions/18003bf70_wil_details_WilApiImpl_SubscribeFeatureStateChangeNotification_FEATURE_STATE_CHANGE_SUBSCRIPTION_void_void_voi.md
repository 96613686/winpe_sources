# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18003bf70`
- end: `0x18003c07d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18003b9a0`
- `0x18003ba9c`
- `0x18003bf70`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003bffa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003bffa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c011`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c011`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003bfc0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003bfc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c067`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c067`

## string_xrefs

- `0x18003bff3`: `ntdll.dll`
- `0x18003c007`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_18008C170);
      if ( qword_18008C1E0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18008C1E0 = 0;
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
               &qword_18008C1E0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&stru_18008C198,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_18008C170);
    }
  }
}

```

## disassembly

```asm
0x18003bf70  mov     [rsp+arg_0], rbx
0x18003bf75  mov     [rsp+arg_8], rsi
0x18003bf7a  push    rdi
0x18003bf7b  sub     rsp, 30h
0x18003bf7f  mov     rdi, r8
0x18003bf82  mov     rsi, rdx
0x18003bf85  mov     rbx, rcx
0x18003bf88  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18003bf8c  jnz     short loc_18003BFA5
0x18003bf8e  mov     r8, rdx; void (*)(void *)
0x18003bf91  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18003bf94  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18003bf9b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18003bfa0  jmp     loc_18003C06D
0x18003bfa5  mov     qword ptr [rcx], 0
0x18003bfac  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18003bfb3  jz      loc_18003C06D
0x18003bfb9  lea     rcx, stru_18008C170; SRWLock
0x18003bfc0  call    cs:__imp_AcquireSRWLockExclusive
0x18003bfc6  cmp     cs:qword_18008C1E0, 0
0x18003bfce  jnz     short loc_18003C04B
0x18003bfd0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18003bfd7  mov     cs:qword_18008C1E0, 0
0x18003bfe2  test    rax, rax
0x18003bfe5  jnz     short loc_18003C02A
0x18003bfe7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003bfee  test    rax, rax
0x18003bff1  jnz     short loc_18003C007
0x18003bff3  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18003bffa  call    cs:__imp_GetModuleHandleW
0x18003c000  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003c007  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18003c00e  mov     rcx, rax; hModule
0x18003c011  call    cs:__imp_GetProcAddress
0x18003c017  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18003c01e  test    rax, rax
0x18003c021  jnz     short loc_18003C02A
0x18003c023  mov     eax, 0C0000139h
0x18003c028  jmp     short loc_18003C047
0x18003c02a  lea     r9, qword_18008C1E0
0x18003c031  xor     r8d, r8d
0x18003c034  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18003c03b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18003c042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c047  test    eax, eax
0x18003c049  jnz     short loc_18003C060
0x18003c04b  mov     r9, rdi; void *
0x18003c04e  lea     rcx, stru_18008C198; this
0x18003c055  mov     r8, rsi; void (*)(void *)
0x18003c058  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18003c05b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18003c060  lea     rcx, stru_18008C170; SRWLock
0x18003c067  call    cs:__imp_ReleaseSRWLockExclusive
0x18003c06d  mov     rbx, [rsp+38h+arg_0]
0x18003c072  mov     rsi, [rsp+38h+arg_8]
0x18003c077  add     rsp, 30h
0x18003c07b  pop     rdi
0x18003c07c  retn
```
