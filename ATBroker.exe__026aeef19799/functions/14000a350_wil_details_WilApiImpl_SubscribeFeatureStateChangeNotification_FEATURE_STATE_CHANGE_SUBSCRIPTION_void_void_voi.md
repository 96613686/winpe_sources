# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14000a350`
- end: `0x14000a45d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x140009c08`
- `0x140009d04`
- `0x14000a350`
- `0x140017010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a447`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a447`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a3a0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a3a0`
- `KERNEL32!GetProcAddress` at `0x14000a3f1`
- `KERNEL32!GetProcAddress` at `0x14000a3f1`
- `KERNEL32!GetModuleHandleW` at `0x14000a3da`
- `KERNEL32!GetModuleHandleW` at `0x14000a3da`

## string_xrefs

- `0x14000a3d3`: `ntdll.dll`
- `0x14000a3e7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_1400203D0);
      if ( qword_140020440 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_140020440 = 0;
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
               &qword_140020440);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_1400203D0);
    }
  }
}

```

## disassembly

```asm
0x14000a350  mov     [rsp+arg_0], rbx
0x14000a355  mov     [rsp+arg_8], rsi
0x14000a35a  push    rdi
0x14000a35b  sub     rsp, 30h
0x14000a35f  mov     rdi, r8
0x14000a362  mov     rsi, rdx
0x14000a365  mov     rbx, rcx
0x14000a368  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14000a36c  jnz     short loc_14000A385
0x14000a36e  mov     r8, rdx; void (*)(void *)
0x14000a371  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000a374  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000a37b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x14000a380  jmp     loc_14000A44D
0x14000a385  mov     qword ptr [rcx], 0
0x14000a38c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000a393  jz      loc_14000A44D
0x14000a399  lea     rcx, stru_1400203D0; SRWLock
0x14000a3a0  call    cs:__imp_AcquireSRWLockExclusive
0x14000a3a6  cmp     cs:qword_140020440, 0
0x14000a3ae  jnz     short loc_14000A42B
0x14000a3b0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000a3b7  mov     cs:qword_140020440, 0
0x14000a3c2  test    rax, rax
0x14000a3c5  jnz     short loc_14000A40A
0x14000a3c7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a3ce  test    rax, rax
0x14000a3d1  jnz     short loc_14000A3E7
0x14000a3d3  lea     rcx, ModuleName; "ntdll.dll"
0x14000a3da  call    cs:__imp_GetModuleHandleW
0x14000a3e0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a3e7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000a3ee  mov     rcx, rax; hModule
0x14000a3f1  call    cs:__imp_GetProcAddress
0x14000a3f7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000a3fe  test    rax, rax
0x14000a401  jnz     short loc_14000A40A
0x14000a403  mov     eax, 0C0000139h
0x14000a408  jmp     short loc_14000A427
0x14000a40a  lea     r9, qword_140020440
0x14000a411  xor     r8d, r8d
0x14000a414  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000a41b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x14000a422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a427  test    eax, eax
0x14000a429  jnz     short loc_14000A440
0x14000a42b  mov     r9, rdi; void *
0x14000a42e  lea     rcx, CriticalSection; this
0x14000a435  mov     r8, rsi; void (*)(void *)
0x14000a438  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000a43b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x14000a440  lea     rcx, stru_1400203D0; SRWLock
0x14000a447  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a44d  mov     rbx, [rsp+38h+arg_0]
0x14000a452  mov     rsi, [rsp+38h+arg_8]
0x14000a457  add     rsp, 30h
0x14000a45b  pop     rdi
0x14000a45c  retn
```
