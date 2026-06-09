# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000e740`
- end: `0x18000e84d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000e040`
- `0x18000e13c`
- `0x18000e740`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e7e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e7e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e7ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e7ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e837`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e837`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e790`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e790`

## string_xrefs

- `0x18000e7c3`: `ntdll.dll`
- `0x18000e7d7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_1800220F0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800220F0 = 0;
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
               &qword_1800220F0);
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
0x18000e740  mov     [rsp+arg_0], rbx
0x18000e745  mov     [rsp+arg_8], rsi
0x18000e74a  push    rdi
0x18000e74b  sub     rsp, 30h
0x18000e74f  mov     rdi, r8
0x18000e752  mov     rsi, rdx
0x18000e755  mov     rbx, rcx
0x18000e758  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000e75c  jnz     short loc_18000E775
0x18000e75e  mov     r8, rdx; void (*)(void *)
0x18000e761  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000e764  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000e76b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000e770  jmp     loc_18000E83D
0x18000e775  mov     qword ptr [rcx], 0
0x18000e77c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000e783  jz      loc_18000E83D
0x18000e789  lea     rcx, SRWLock; SRWLock
0x18000e790  call    cs:__imp_AcquireSRWLockExclusive
0x18000e796  cmp     cs:qword_1800220F0, 0
0x18000e79e  jnz     short loc_18000E81B
0x18000e7a0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000e7a7  mov     cs:qword_1800220F0, 0
0x18000e7b2  test    rax, rax
0x18000e7b5  jnz     short loc_18000E7FA
0x18000e7b7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e7be  test    rax, rax
0x18000e7c1  jnz     short loc_18000E7D7
0x18000e7c3  lea     rcx, ModuleName; "ntdll.dll"
0x18000e7ca  call    cs:__imp_GetModuleHandleW
0x18000e7d0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e7d7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000e7de  mov     rcx, rax; hModule
0x18000e7e1  call    cs:__imp_GetProcAddress
0x18000e7e7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000e7ee  test    rax, rax
0x18000e7f1  jnz     short loc_18000E7FA
0x18000e7f3  mov     eax, 0C0000139h
0x18000e7f8  jmp     short loc_18000E817
0x18000e7fa  lea     r9, qword_1800220F0
0x18000e801  xor     r8d, r8d
0x18000e804  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000e80b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000e812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e817  test    eax, eax
0x18000e819  jnz     short loc_18000E830
0x18000e81b  mov     r9, rdi; void *
0x18000e81e  lea     rcx, CriticalSection; this
0x18000e825  mov     r8, rsi; void (*)(void *)
0x18000e828  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000e82b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000e830  lea     rcx, SRWLock; SRWLock
0x18000e837  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e83d  mov     rbx, [rsp+38h+arg_0]
0x18000e842  mov     rsi, [rsp+38h+arg_8]
0x18000e847  add     rsp, 30h
0x18000e84b  pop     rdi
0x18000e84c  retn
```
