# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000a080`
- end: `0x18000a18d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1800098bc`
- `0x1800099b8`
- `0x18000a080`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a121`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a121`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a10a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a10a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a0d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a0d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a177`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a177`

## string_xrefs

- `0x18000a103`: `ntdll.dll`
- `0x18000a117`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_1800520E0);
      if ( qword_180052150 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180052150 = 0;
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
               &qword_180052150);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_1800520E0);
    }
  }
}

```

## disassembly

```asm
0x18000a080  mov     [rsp+arg_0], rbx
0x18000a085  mov     [rsp+arg_8], rsi
0x18000a08a  push    rdi
0x18000a08b  sub     rsp, 30h
0x18000a08f  mov     rdi, r8
0x18000a092  mov     rsi, rdx
0x18000a095  mov     rbx, rcx
0x18000a098  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000a09c  jnz     short loc_18000A0B5
0x18000a09e  mov     r8, rdx; void (*)(void *)
0x18000a0a1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000a0a4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000a0ab  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000a0b0  jmp     loc_18000A17D
0x18000a0b5  mov     qword ptr [rcx], 0
0x18000a0bc  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000a0c3  jz      loc_18000A17D
0x18000a0c9  lea     rcx, stru_1800520E0; SRWLock
0x18000a0d0  call    cs:__imp_AcquireSRWLockExclusive
0x18000a0d6  cmp     cs:qword_180052150, 0
0x18000a0de  jnz     short loc_18000A15B
0x18000a0e0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000a0e7  mov     cs:qword_180052150, 0
0x18000a0f2  test    rax, rax
0x18000a0f5  jnz     short loc_18000A13A
0x18000a0f7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a0fe  test    rax, rax
0x18000a101  jnz     short loc_18000A117
0x18000a103  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000a10a  call    cs:__imp_GetModuleHandleW
0x18000a110  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a117  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000a11e  mov     rcx, rax; hModule
0x18000a121  call    cs:__imp_GetProcAddress
0x18000a127  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000a12e  test    rax, rax
0x18000a131  jnz     short loc_18000A13A
0x18000a133  mov     eax, 0C0000139h
0x18000a138  jmp     short loc_18000A157
0x18000a13a  lea     r9, qword_180052150
0x18000a141  xor     r8d, r8d
0x18000a144  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000a14b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000a152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a157  test    eax, eax
0x18000a159  jnz     short loc_18000A170
0x18000a15b  mov     r9, rdi; void *
0x18000a15e  lea     rcx, CriticalSection; this
0x18000a165  mov     r8, rsi; void (*)(void *)
0x18000a168  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000a16b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000a170  lea     rcx, stru_1800520E0; SRWLock
0x18000a177  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a17d  mov     rbx, [rsp+38h+arg_0]
0x18000a182  mov     rsi, [rsp+38h+arg_8]
0x18000a187  add     rsp, 30h
0x18000a18b  pop     rdi
0x18000a18c  retn
```
