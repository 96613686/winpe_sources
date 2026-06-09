# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1800097b0`
- end: `0x1800098bd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180009040`
- `0x18000913c`
- `0x1800097b0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009851`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009851`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000983a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000983a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009800`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009800`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800098a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800098a7`

## string_xrefs

- `0x180009833`: `ntdll.dll`
- `0x180009847`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_1800230C0);
      if ( qword_180023130 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180023130 = 0;
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
               &qword_180023130);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_1800230C0);
    }
  }
}

```

## disassembly

```asm
0x1800097b0  mov     [rsp+arg_0], rbx
0x1800097b5  mov     [rsp+arg_8], rsi
0x1800097ba  push    rdi
0x1800097bb  sub     rsp, 30h
0x1800097bf  mov     rdi, r8
0x1800097c2  mov     rsi, rdx
0x1800097c5  mov     rbx, rcx
0x1800097c8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800097cc  jnz     short loc_1800097E5
0x1800097ce  mov     r8, rdx; void (*)(void *)
0x1800097d1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800097d4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800097db  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x1800097e0  jmp     loc_1800098AD
0x1800097e5  mov     qword ptr [rcx], 0
0x1800097ec  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800097f3  jz      loc_1800098AD
0x1800097f9  lea     rcx, stru_1800230C0; SRWLock
0x180009800  call    cs:__imp_AcquireSRWLockExclusive
0x180009806  cmp     cs:qword_180023130, 0
0x18000980e  jnz     short loc_18000988B
0x180009810  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180009817  mov     cs:qword_180023130, 0
0x180009822  test    rax, rax
0x180009825  jnz     short loc_18000986A
0x180009827  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000982e  test    rax, rax
0x180009831  jnz     short loc_180009847
0x180009833  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000983a  call    cs:__imp_GetModuleHandleW
0x180009840  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009847  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000984e  mov     rcx, rax; hModule
0x180009851  call    cs:__imp_GetProcAddress
0x180009857  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000985e  test    rax, rax
0x180009861  jnz     short loc_18000986A
0x180009863  mov     eax, 0C0000139h
0x180009868  jmp     short loc_180009887
0x18000986a  lea     r9, qword_180023130
0x180009871  xor     r8d, r8d
0x180009874  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000987b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180009882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009887  test    eax, eax
0x180009889  jnz     short loc_1800098A0
0x18000988b  mov     r9, rdi; void *
0x18000988e  lea     rcx, CriticalSection; this
0x180009895  mov     r8, rsi; void (*)(void *)
0x180009898  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000989b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800098a0  lea     rcx, stru_1800230C0; SRWLock
0x1800098a7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800098ad  mov     rbx, [rsp+38h+arg_0]
0x1800098b2  mov     rsi, [rsp+38h+arg_8]
0x1800098b7  add     rsp, 30h
0x1800098bb  pop     rdi
0x1800098bc  retn
```
