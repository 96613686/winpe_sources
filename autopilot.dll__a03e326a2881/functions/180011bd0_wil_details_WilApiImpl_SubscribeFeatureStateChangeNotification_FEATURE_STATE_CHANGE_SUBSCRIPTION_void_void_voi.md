# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180011bd0`
- end: `0x180011cdd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1800113bc`
- `0x1800114b8`
- `0x180011bd0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011c5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011c5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011c71`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011c71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011cc7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011cc7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011c20`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011c20`

## string_xrefs

- `0x180011c53`: `ntdll.dll`
- `0x180011c67`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180042178);
      if ( qword_1800421E8 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800421E8 = 0;
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
               &qword_1800421E8);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180042178);
    }
  }
}

```

## disassembly

```asm
0x180011bd0  mov     [rsp+arg_0], rbx
0x180011bd5  mov     [rsp+arg_8], rsi
0x180011bda  push    rdi
0x180011bdb  sub     rsp, 30h
0x180011bdf  mov     rdi, r8
0x180011be2  mov     rsi, rdx
0x180011be5  mov     rbx, rcx
0x180011be8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180011bec  jnz     short loc_180011C05
0x180011bee  mov     r8, rdx; void (*)(void *)
0x180011bf1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180011bf4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180011bfb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180011c00  jmp     loc_180011CCD
0x180011c05  mov     qword ptr [rcx], 0
0x180011c0c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180011c13  jz      loc_180011CCD
0x180011c19  lea     rcx, stru_180042178; SRWLock
0x180011c20  call    cs:__imp_AcquireSRWLockExclusive
0x180011c26  cmp     cs:qword_1800421E8, 0
0x180011c2e  jnz     short loc_180011CAB
0x180011c30  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180011c37  mov     cs:qword_1800421E8, 0
0x180011c42  test    rax, rax
0x180011c45  jnz     short loc_180011C8A
0x180011c47  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011c4e  test    rax, rax
0x180011c51  jnz     short loc_180011C67
0x180011c53  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180011c5a  call    cs:__imp_GetModuleHandleW
0x180011c60  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011c67  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180011c6e  mov     rcx, rax; hModule
0x180011c71  call    cs:__imp_GetProcAddress
0x180011c77  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180011c7e  test    rax, rax
0x180011c81  jnz     short loc_180011C8A
0x180011c83  mov     eax, 0C0000139h
0x180011c88  jmp     short loc_180011CA7
0x180011c8a  lea     r9, qword_1800421E8
0x180011c91  xor     r8d, r8d
0x180011c94  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180011c9b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180011ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ca7  test    eax, eax
0x180011ca9  jnz     short loc_180011CC0
0x180011cab  mov     r9, rdi; void *
0x180011cae  lea     rcx, CriticalSection; this
0x180011cb5  mov     r8, rsi; void (*)(void *)
0x180011cb8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180011cbb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180011cc0  lea     rcx, stru_180042178; SRWLock
0x180011cc7  call    cs:__imp_ReleaseSRWLockExclusive
0x180011ccd  mov     rbx, [rsp+38h+arg_0]
0x180011cd2  mov     rsi, [rsp+38h+arg_8]
0x180011cd7  add     rsp, 30h
0x180011cdb  pop     rdi
0x180011cdc  retn
```
