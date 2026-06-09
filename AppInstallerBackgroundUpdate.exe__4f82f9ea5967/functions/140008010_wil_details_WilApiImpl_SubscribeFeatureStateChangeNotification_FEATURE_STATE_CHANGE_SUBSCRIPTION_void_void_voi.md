# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x140008010`
- end: `0x14000811d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x140007bb4`
- `0x140007cb0`
- `0x140008010`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000809a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000809a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400080b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400080b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008107`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008107`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008060`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008060`

## string_xrefs

- `0x140008093`: `ntdll.dll`
- `0x1400080a7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_14000D0A0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_14000D0A0 = 0;
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
               &qword_14000D0A0);
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
0x140008010  mov     [rsp+arg_0], rbx
0x140008015  mov     [rsp+arg_8], rsi
0x14000801a  push    rdi
0x14000801b  sub     rsp, 30h
0x14000801f  mov     rdi, r8
0x140008022  mov     rsi, rdx
0x140008025  mov     rbx, rcx
0x140008028  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14000802c  jnz     short loc_140008045
0x14000802e  mov     r8, rdx; void (*)(void *)
0x140008031  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140008034  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000803b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x140008040  jmp     loc_14000810D
0x140008045  mov     qword ptr [rcx], 0
0x14000804c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140008053  jz      loc_14000810D
0x140008059  lea     rcx, SRWLock; SRWLock
0x140008060  call    cs:__imp_AcquireSRWLockExclusive
0x140008066  cmp     cs:qword_14000D0A0, 0
0x14000806e  jnz     short loc_1400080EB
0x140008070  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140008077  mov     cs:qword_14000D0A0, 0
0x140008082  test    rax, rax
0x140008085  jnz     short loc_1400080CA
0x140008087  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000808e  test    rax, rax
0x140008091  jnz     short loc_1400080A7
0x140008093  lea     rcx, ModuleName; "ntdll.dll"
0x14000809a  call    cs:__imp_GetModuleHandleW
0x1400080a0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400080a7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1400080ae  mov     rcx, rax; hModule
0x1400080b1  call    cs:__imp_GetProcAddress
0x1400080b7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1400080be  test    rax, rax
0x1400080c1  jnz     short loc_1400080CA
0x1400080c3  mov     eax, 0C0000139h
0x1400080c8  jmp     short loc_1400080E7
0x1400080ca  lea     r9, qword_14000D0A0
0x1400080d1  xor     r8d, r8d
0x1400080d4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1400080db  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1400080e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080e7  test    eax, eax
0x1400080e9  jnz     short loc_140008100
0x1400080eb  mov     r9, rdi; void *
0x1400080ee  lea     rcx, CriticalSection; this
0x1400080f5  mov     r8, rsi; void (*)(void *)
0x1400080f8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1400080fb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x140008100  lea     rcx, SRWLock; SRWLock
0x140008107  call    cs:__imp_ReleaseSRWLockExclusive
0x14000810d  mov     rbx, [rsp+38h+arg_0]
0x140008112  mov     rsi, [rsp+38h+arg_8]
0x140008117  add     rsp, 30h
0x14000811b  pop     rdi
0x14000811c  retn
```
