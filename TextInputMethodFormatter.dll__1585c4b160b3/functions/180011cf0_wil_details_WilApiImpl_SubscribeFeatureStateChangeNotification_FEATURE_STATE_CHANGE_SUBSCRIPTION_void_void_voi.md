# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180011cf0`
- end: `0x180011dfd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18001148c`
- `0x180011588`
- `0x180011cf0`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011d91`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011d91`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011d7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011d7a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011de7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011de7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011d40`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011d40`

## string_xrefs

- `0x180011d73`: `ntdll.dll`
- `0x180011d87`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180082100);
      if ( qword_180082170 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180082170 = 0;
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
               &qword_180082170);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180082100);
    }
  }
}

```

## disassembly

```asm
0x180011cf0  mov     [rsp+arg_0], rbx
0x180011cf5  mov     [rsp+arg_8], rsi
0x180011cfa  push    rdi
0x180011cfb  sub     rsp, 30h
0x180011cff  mov     rdi, r8
0x180011d02  mov     rsi, rdx
0x180011d05  mov     rbx, rcx
0x180011d08  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180011d0c  jnz     short loc_180011D25
0x180011d0e  mov     r8, rdx; void (*)(void *)
0x180011d11  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180011d14  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180011d1b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180011d20  jmp     loc_180011DED
0x180011d25  mov     qword ptr [rcx], 0
0x180011d2c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180011d33  jz      loc_180011DED
0x180011d39  lea     rcx, stru_180082100; SRWLock
0x180011d40  call    cs:__imp_AcquireSRWLockExclusive
0x180011d46  cmp     cs:qword_180082170, 0
0x180011d4e  jnz     short loc_180011DCB
0x180011d50  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180011d57  mov     cs:qword_180082170, 0
0x180011d62  test    rax, rax
0x180011d65  jnz     short loc_180011DAA
0x180011d67  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011d6e  test    rax, rax
0x180011d71  jnz     short loc_180011D87
0x180011d73  lea     rcx, ModuleName; "ntdll.dll"
0x180011d7a  call    cs:__imp_GetModuleHandleW
0x180011d80  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011d87  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180011d8e  mov     rcx, rax; hModule
0x180011d91  call    cs:__imp_GetProcAddress
0x180011d97  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180011d9e  test    rax, rax
0x180011da1  jnz     short loc_180011DAA
0x180011da3  mov     eax, 0C0000139h
0x180011da8  jmp     short loc_180011DC7
0x180011daa  lea     r9, qword_180082170
0x180011db1  xor     r8d, r8d
0x180011db4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180011dbb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180011dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dc7  test    eax, eax
0x180011dc9  jnz     short loc_180011DE0
0x180011dcb  mov     r9, rdi; void *
0x180011dce  lea     rcx, CriticalSection; this
0x180011dd5  mov     r8, rsi; void (*)(void *)
0x180011dd8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180011ddb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180011de0  lea     rcx, stru_180082100; SRWLock
0x180011de7  call    cs:__imp_ReleaseSRWLockExclusive
0x180011ded  mov     rbx, [rsp+38h+arg_0]
0x180011df2  mov     rsi, [rsp+38h+arg_8]
0x180011df7  add     rsp, 30h
0x180011dfb  pop     rdi
0x180011dfc  retn
```
