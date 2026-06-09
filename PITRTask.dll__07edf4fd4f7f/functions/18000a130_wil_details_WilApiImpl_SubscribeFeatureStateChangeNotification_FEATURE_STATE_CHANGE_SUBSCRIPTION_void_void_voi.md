# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000a130`
- end: `0x18000a22e`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `254`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1800098f0`
- `0x1800099f4`
- `0x18000a130`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a1ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a1ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a1b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a1b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a220`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a220`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a179`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a179`

## string_xrefs

- `0x18000a1ac`: `ntdll.dll`
- `0x18000a1c0`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_18001B070);
      if ( qword_18001B0E0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18001B0E0 = 0;
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
               &qword_18001B0E0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_18001B070);
    }
  }
}

```

## disassembly

```asm
0x18000a130  push    rbx
0x18000a132  push    rsi
0x18000a133  push    rdi
0x18000a134  sub     rsp, 30h
0x18000a138  mov     rsi, r8
0x18000a13b  mov     rdi, rdx
0x18000a13e  mov     rbx, rcx
0x18000a141  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000a145  jnz     short loc_18000A15E
0x18000a147  mov     r8, rdx; void (*)(void *)
0x18000a14a  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000a14d  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000a154  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000a159  jmp     loc_18000A226
0x18000a15e  mov     qword ptr [rcx], 0
0x18000a165  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000a16c  jz      loc_18000A226
0x18000a172  lea     rcx, stru_18001B070; SRWLock
0x18000a179  call    cs:__imp_AcquireSRWLockExclusive
0x18000a17f  cmp     cs:qword_18001B0E0, 0
0x18000a187  jnz     short loc_18000A204
0x18000a189  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000a190  mov     cs:qword_18001B0E0, 0
0x18000a19b  test    rax, rax
0x18000a19e  jnz     short loc_18000A1E3
0x18000a1a0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a1a7  test    rax, rax
0x18000a1aa  jnz     short loc_18000A1C0
0x18000a1ac  lea     rcx, ModuleName; "ntdll.dll"
0x18000a1b3  call    cs:__imp_GetModuleHandleW
0x18000a1b9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a1c0  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000a1c7  mov     rcx, rax; hModule
0x18000a1ca  call    cs:__imp_GetProcAddress
0x18000a1d0  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000a1d7  test    rax, rax
0x18000a1da  jnz     short loc_18000A1E3
0x18000a1dc  mov     eax, 0C0000139h
0x18000a1e1  jmp     short loc_18000A200
0x18000a1e3  lea     r9, qword_18001B0E0
0x18000a1ea  xor     r8d, r8d
0x18000a1ed  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000a1f4  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000a1fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a200  test    eax, eax
0x18000a202  jnz     short loc_18000A219
0x18000a204  mov     r9, rsi; void *
0x18000a207  lea     rcx, CriticalSection; this
0x18000a20e  mov     r8, rdi; void (*)(void *)
0x18000a211  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000a214  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000a219  lea     rcx, stru_18001B070; SRWLock
0x18000a220  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a226  add     rsp, 30h
0x18000a22a  pop     rdi
0x18000a22b  pop     rsi
0x18000a22c  pop     rbx
0x18000a22d  retn
```
