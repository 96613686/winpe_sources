# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180008050`
- end: `0x18000815d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180007934`
- `0x180007a30`
- `0x180008050`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800080f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800080f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800080da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800080da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800080a0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800080a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008147`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008147`

## string_xrefs

- `0x1800080d3`: `ntdll.dll`
- `0x1800080e7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_1800170D0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800170D0 = 0;
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
               &qword_1800170D0);
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
0x180008050  mov     [rsp+arg_0], rbx
0x180008055  mov     [rsp+arg_8], rsi
0x18000805a  push    rdi
0x18000805b  sub     rsp, 30h
0x18000805f  mov     rdi, r8
0x180008062  mov     rsi, rdx
0x180008065  mov     rbx, rcx
0x180008068  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000806c  jnz     short loc_180008085
0x18000806e  mov     r8, rdx; void (*)(void *)
0x180008071  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180008074  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000807b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180008080  jmp     loc_18000814D
0x180008085  mov     qword ptr [rcx], 0
0x18000808c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180008093  jz      loc_18000814D
0x180008099  lea     rcx, SRWLock; SRWLock
0x1800080a0  call    cs:__imp_AcquireSRWLockExclusive
0x1800080a6  cmp     cs:qword_1800170D0, 0
0x1800080ae  jnz     short loc_18000812B
0x1800080b0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800080b7  mov     cs:qword_1800170D0, 0
0x1800080c2  test    rax, rax
0x1800080c5  jnz     short loc_18000810A
0x1800080c7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800080ce  test    rax, rax
0x1800080d1  jnz     short loc_1800080E7
0x1800080d3  lea     rcx, ModuleName; "ntdll.dll"
0x1800080da  call    cs:__imp_GetModuleHandleW
0x1800080e0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800080e7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800080ee  mov     rcx, rax; hModule
0x1800080f1  call    cs:__imp_GetProcAddress
0x1800080f7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800080fe  test    rax, rax
0x180008101  jnz     short loc_18000810A
0x180008103  mov     eax, 0C0000139h
0x180008108  jmp     short loc_180008127
0x18000810a  lea     r9, qword_1800170D0
0x180008111  xor     r8d, r8d
0x180008114  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000811b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180008122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008127  test    eax, eax
0x180008129  jnz     short loc_180008140
0x18000812b  mov     r9, rdi; void *
0x18000812e  lea     rcx, CriticalSection; this
0x180008135  mov     r8, rsi; void (*)(void *)
0x180008138  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000813b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180008140  lea     rcx, SRWLock; SRWLock
0x180008147  call    cs:__imp_ReleaseSRWLockExclusive
0x18000814d  mov     rbx, [rsp+38h+arg_0]
0x180008152  mov     rsi, [rsp+38h+arg_8]
0x180008157  add     rsp, 30h
0x18000815b  pop     rdi
0x18000815c  retn
```
