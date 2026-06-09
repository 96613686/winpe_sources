# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000c140`
- end: `0x18000c24d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000b8c8`
- `0x18000b9c4`
- `0x18000c140`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c1ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c1ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c1e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c1e1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c190`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c190`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c237`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c237`

## string_xrefs

- `0x18000c1c3`: `ntdll.dll`
- `0x18000c1d7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_1800410C0);
      if ( qword_180041130 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180041130 = 0;
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
               &qword_180041130);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_1800410C0);
    }
  }
}

```

## disassembly

```asm
0x18000c140  mov     [rsp+arg_0], rbx
0x18000c145  mov     [rsp+arg_8], rsi
0x18000c14a  push    rdi
0x18000c14b  sub     rsp, 30h
0x18000c14f  mov     rdi, r8
0x18000c152  mov     rsi, rdx
0x18000c155  mov     rbx, rcx
0x18000c158  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000c15c  jnz     short loc_18000C175
0x18000c15e  mov     r8, rdx; void (*)(void *)
0x18000c161  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000c164  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000c16b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000c170  jmp     loc_18000C23D
0x18000c175  mov     qword ptr [rcx], 0
0x18000c17c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000c183  jz      loc_18000C23D
0x18000c189  lea     rcx, stru_1800410C0; SRWLock
0x18000c190  call    cs:__imp_AcquireSRWLockExclusive
0x18000c196  cmp     cs:qword_180041130, 0
0x18000c19e  jnz     short loc_18000C21B
0x18000c1a0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000c1a7  mov     cs:qword_180041130, 0
0x18000c1b2  test    rax, rax
0x18000c1b5  jnz     short loc_18000C1FA
0x18000c1b7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c1be  test    rax, rax
0x18000c1c1  jnz     short loc_18000C1D7
0x18000c1c3  lea     rcx, ModuleName; "ntdll.dll"
0x18000c1ca  call    cs:__imp_GetModuleHandleW
0x18000c1d0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c1d7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000c1de  mov     rcx, rax; hModule
0x18000c1e1  call    cs:__imp_GetProcAddress
0x18000c1e7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000c1ee  test    rax, rax
0x18000c1f1  jnz     short loc_18000C1FA
0x18000c1f3  mov     eax, 0C0000139h
0x18000c1f8  jmp     short loc_18000C217
0x18000c1fa  lea     r9, qword_180041130
0x18000c201  xor     r8d, r8d
0x18000c204  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000c20b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000c212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c217  test    eax, eax
0x18000c219  jnz     short loc_18000C230
0x18000c21b  mov     r9, rdi; void *
0x18000c21e  lea     rcx, CriticalSection; this
0x18000c225  mov     r8, rsi; void (*)(void *)
0x18000c228  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000c22b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000c230  lea     rcx, stru_1800410C0; SRWLock
0x18000c237  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c23d  mov     rbx, [rsp+38h+arg_0]
0x18000c242  mov     rsi, [rsp+38h+arg_8]
0x18000c247  add     rsp, 30h
0x18000c24b  pop     rdi
0x18000c24c  retn
```
