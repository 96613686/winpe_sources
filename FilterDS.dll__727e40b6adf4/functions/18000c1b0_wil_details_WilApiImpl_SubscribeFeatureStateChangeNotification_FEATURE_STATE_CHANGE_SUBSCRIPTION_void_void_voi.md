# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000c1b0`
- end: `0x18000c2bd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000bbb8`
- `0x18000bcb4`
- `0x18000c1b0`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c251`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c251`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c23a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c23a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c200`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c200`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c2a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c2a7`

## string_xrefs

- `0x18000c233`: `ntdll.dll`
- `0x18000c247`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180030080);
      if ( qword_1800300F0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800300F0 = 0;
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
               &qword_1800300F0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180030080);
    }
  }
}

```

## disassembly

```asm
0x18000c1b0  mov     [rsp+arg_0], rbx
0x18000c1b5  mov     [rsp+arg_8], rsi
0x18000c1ba  push    rdi
0x18000c1bb  sub     rsp, 30h
0x18000c1bf  mov     rdi, r8
0x18000c1c2  mov     rsi, rdx
0x18000c1c5  mov     rbx, rcx
0x18000c1c8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000c1cc  jnz     short loc_18000C1E5
0x18000c1ce  mov     r8, rdx; void (*)(void *)
0x18000c1d1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000c1d4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000c1db  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000c1e0  jmp     loc_18000C2AD
0x18000c1e5  mov     qword ptr [rcx], 0
0x18000c1ec  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000c1f3  jz      loc_18000C2AD
0x18000c1f9  lea     rcx, stru_180030080; SRWLock
0x18000c200  call    cs:__imp_AcquireSRWLockExclusive
0x18000c206  cmp     cs:qword_1800300F0, 0
0x18000c20e  jnz     short loc_18000C28B
0x18000c210  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000c217  mov     cs:qword_1800300F0, 0
0x18000c222  test    rax, rax
0x18000c225  jnz     short loc_18000C26A
0x18000c227  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c22e  test    rax, rax
0x18000c231  jnz     short loc_18000C247
0x18000c233  lea     rcx, ModuleName; "ntdll.dll"
0x18000c23a  call    cs:__imp_GetModuleHandleW
0x18000c240  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c247  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000c24e  mov     rcx, rax; hModule
0x18000c251  call    cs:__imp_GetProcAddress
0x18000c257  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000c25e  test    rax, rax
0x18000c261  jnz     short loc_18000C26A
0x18000c263  mov     eax, 0C0000139h
0x18000c268  jmp     short loc_18000C287
0x18000c26a  lea     r9, qword_1800300F0
0x18000c271  xor     r8d, r8d
0x18000c274  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000c27b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000c282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c287  test    eax, eax
0x18000c289  jnz     short loc_18000C2A0
0x18000c28b  mov     r9, rdi; void *
0x18000c28e  lea     rcx, CriticalSection; this
0x18000c295  mov     r8, rsi; void (*)(void *)
0x18000c298  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000c29b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000c2a0  lea     rcx, stru_180030080; SRWLock
0x18000c2a7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c2ad  mov     rbx, [rsp+38h+arg_0]
0x18000c2b2  mov     rsi, [rsp+38h+arg_8]
0x18000c2b7  add     rsp, 30h
0x18000c2bb  pop     rdi
0x18000c2bc  retn
```
