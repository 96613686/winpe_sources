# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180015f20`
- end: `0x18001602d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180015a78`
- `0x180015b74`
- `0x180015f20`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015fc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015fc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015faa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015faa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016017`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016017`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015f70`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015f70`

## string_xrefs

- `0x180015fa3`: `ntdll.dll`
- `0x180015fb7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_1800271B8);
      if ( qword_180027228 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180027228 = 0;
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
               &qword_180027228);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_1800271B8);
    }
  }
}

```

## disassembly

```asm
0x180015f20  mov     [rsp+arg_0], rbx
0x180015f25  mov     [rsp+arg_8], rsi
0x180015f2a  push    rdi
0x180015f2b  sub     rsp, 30h
0x180015f2f  mov     rdi, r8
0x180015f32  mov     rsi, rdx
0x180015f35  mov     rbx, rcx
0x180015f38  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180015f3c  jnz     short loc_180015F55
0x180015f3e  mov     r8, rdx; void (*)(void *)
0x180015f41  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180015f44  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180015f4b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180015f50  jmp     loc_18001601D
0x180015f55  mov     qword ptr [rcx], 0
0x180015f5c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180015f63  jz      loc_18001601D
0x180015f69  lea     rcx, stru_1800271B8; SRWLock
0x180015f70  call    cs:__imp_AcquireSRWLockExclusive
0x180015f76  cmp     cs:qword_180027228, 0
0x180015f7e  jnz     short loc_180015FFB
0x180015f80  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180015f87  mov     cs:qword_180027228, 0
0x180015f92  test    rax, rax
0x180015f95  jnz     short loc_180015FDA
0x180015f97  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180015f9e  test    rax, rax
0x180015fa1  jnz     short loc_180015FB7
0x180015fa3  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180015faa  call    cs:__imp_GetModuleHandleW
0x180015fb0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180015fb7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180015fbe  mov     rcx, rax; hModule
0x180015fc1  call    cs:__imp_GetProcAddress
0x180015fc7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180015fce  test    rax, rax
0x180015fd1  jnz     short loc_180015FDA
0x180015fd3  mov     eax, 0C0000139h
0x180015fd8  jmp     short loc_180015FF7
0x180015fda  lea     r9, qword_180027228
0x180015fe1  xor     r8d, r8d
0x180015fe4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180015feb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180015ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ff7  test    eax, eax
0x180015ff9  jnz     short loc_180016010
0x180015ffb  mov     r9, rdi; void *
0x180015ffe  lea     rcx, CriticalSection; this
0x180016005  mov     r8, rsi; void (*)(void *)
0x180016008  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18001600b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180016010  lea     rcx, stru_1800271B8; SRWLock
0x180016017  call    cs:__imp_ReleaseSRWLockExclusive
0x18001601d  mov     rbx, [rsp+38h+arg_0]
0x180016022  mov     rsi, [rsp+38h+arg_8]
0x180016027  add     rsp, 30h
0x18001602b  pop     rdi
0x18001602c  retn
```
