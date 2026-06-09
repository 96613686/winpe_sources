# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1800097d0`
- end: `0x1800098dd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000937c`
- `0x180009478`
- `0x1800097d0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000985a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000985a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009871`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009871`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800098c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800098c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009820`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009820`

## string_xrefs

- `0x180009853`: `ntdll.dll`
- `0x180009867`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_1800100A0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800100A0 = 0;
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
               &qword_1800100A0);
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
0x1800097d0  mov     [rsp+arg_0], rbx
0x1800097d5  mov     [rsp+arg_8], rsi
0x1800097da  push    rdi
0x1800097db  sub     rsp, 30h
0x1800097df  mov     rdi, r8
0x1800097e2  mov     rsi, rdx
0x1800097e5  mov     rbx, rcx
0x1800097e8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800097ec  jnz     short loc_180009805
0x1800097ee  mov     r8, rdx; void (*)(void *)
0x1800097f1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800097f4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800097fb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180009800  jmp     loc_1800098CD
0x180009805  mov     qword ptr [rcx], 0
0x18000980c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009813  jz      loc_1800098CD
0x180009819  lea     rcx, SRWLock; SRWLock
0x180009820  call    cs:__imp_AcquireSRWLockExclusive
0x180009826  cmp     cs:qword_1800100A0, 0
0x18000982e  jnz     short loc_1800098AB
0x180009830  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180009837  mov     cs:qword_1800100A0, 0
0x180009842  test    rax, rax
0x180009845  jnz     short loc_18000988A
0x180009847  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000984e  test    rax, rax
0x180009851  jnz     short loc_180009867
0x180009853  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000985a  call    cs:__imp_GetModuleHandleW
0x180009860  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009867  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000986e  mov     rcx, rax; hModule
0x180009871  call    cs:__imp_GetProcAddress
0x180009877  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000987e  test    rax, rax
0x180009881  jnz     short loc_18000988A
0x180009883  mov     eax, 0C0000139h
0x180009888  jmp     short loc_1800098A7
0x18000988a  lea     r9, qword_1800100A0
0x180009891  xor     r8d, r8d
0x180009894  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000989b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800098a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098a7  test    eax, eax
0x1800098a9  jnz     short loc_1800098C0
0x1800098ab  mov     r9, rdi; void *
0x1800098ae  lea     rcx, CriticalSection; this
0x1800098b5  mov     r8, rsi; void (*)(void *)
0x1800098b8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800098bb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800098c0  lea     rcx, SRWLock; SRWLock
0x1800098c7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800098cd  mov     rbx, [rsp+38h+arg_0]
0x1800098d2  mov     rsi, [rsp+38h+arg_8]
0x1800098d7  add     rsp, 30h
0x1800098db  pop     rdi
0x1800098dc  retn
```
