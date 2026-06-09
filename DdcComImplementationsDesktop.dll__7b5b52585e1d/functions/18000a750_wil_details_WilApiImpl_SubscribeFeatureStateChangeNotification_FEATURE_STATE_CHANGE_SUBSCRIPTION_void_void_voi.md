# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000a750`
- end: `0x18000a85d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000a054`
- `0x18000a150`
- `0x18000a750`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a7f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a7f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a7da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a7da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a847`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a847`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a7a0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a7a0`

## string_xrefs

- `0x18000a7d3`: `ntdll.dll`
- `0x18000a7e7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_180013120 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180013120 = 0;
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
        v9 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), char *, _QWORD, __int64 *))ProcAddress)(
               _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
               &wil::details::g_featureStateManager,
               0,
               &qword_180013120);
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
0x18000a750  mov     [rsp+arg_0], rbx
0x18000a755  mov     [rsp+arg_8], rsi
0x18000a75a  push    rdi
0x18000a75b  sub     rsp, 30h
0x18000a75f  mov     rdi, r8
0x18000a762  mov     rsi, rdx
0x18000a765  mov     rbx, rcx
0x18000a768  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000a76c  jnz     short loc_18000A785
0x18000a76e  mov     r8, rdx; void (*)(void *)
0x18000a771  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000a774  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000a77b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000a780  jmp     loc_18000A84D
0x18000a785  mov     qword ptr [rcx], 0
0x18000a78c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000a793  jz      loc_18000A84D
0x18000a799  lea     rcx, SRWLock; SRWLock
0x18000a7a0  call    cs:__imp_AcquireSRWLockExclusive
0x18000a7a6  cmp     cs:qword_180013120, 0
0x18000a7ae  jnz     short loc_18000A82B
0x18000a7b0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000a7b7  mov     cs:qword_180013120, 0
0x18000a7c2  test    rax, rax
0x18000a7c5  jnz     short loc_18000A80A
0x18000a7c7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a7ce  test    rax, rax
0x18000a7d1  jnz     short loc_18000A7E7
0x18000a7d3  lea     rcx, ModuleName; "ntdll.dll"
0x18000a7da  call    cs:__imp_GetModuleHandleW
0x18000a7e0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a7e7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000a7ee  mov     rcx, rax; hModule
0x18000a7f1  call    cs:__imp_GetProcAddress
0x18000a7f7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000a7fe  test    rax, rax
0x18000a801  jnz     short loc_18000A80A
0x18000a803  mov     eax, 0C0000139h
0x18000a808  jmp     short loc_18000A827
0x18000a80a  lea     r9, qword_180013120
0x18000a811  xor     r8d, r8d
0x18000a814  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000a81b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000a822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a827  test    eax, eax
0x18000a829  jnz     short loc_18000A840
0x18000a82b  mov     r9, rdi; void *
0x18000a82e  lea     rcx, CriticalSection; this
0x18000a835  mov     r8, rsi; void (*)(void *)
0x18000a838  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000a83b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000a840  lea     rcx, SRWLock; SRWLock
0x18000a847  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a84d  mov     rbx, [rsp+38h+arg_0]
0x18000a852  mov     rsi, [rsp+38h+arg_8]
0x18000a857  add     rsp, 30h
0x18000a85b  pop     rdi
0x18000a85c  retn
```
