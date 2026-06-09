# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180007850`
- end: `0x18000795d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000712c`
- `0x180007228`
- `0x180007850`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800078f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800078f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800078da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800078da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007947`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007947`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800078a0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800078a0`

## string_xrefs

- `0x1800078d3`: `ntdll.dll`
- `0x1800078e7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180012060);
      if ( qword_1800120D0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800120D0 = 0;
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
               &qword_1800120D0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180012060);
    }
  }
}

```

## disassembly

```asm
0x180007850  mov     [rsp+arg_0], rbx
0x180007855  mov     [rsp+arg_8], rsi
0x18000785a  push    rdi
0x18000785b  sub     rsp, 30h
0x18000785f  mov     rdi, r8
0x180007862  mov     rsi, rdx
0x180007865  mov     rbx, rcx
0x180007868  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000786c  jnz     short loc_180007885
0x18000786e  mov     r8, rdx; void (*)(void *)
0x180007871  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180007874  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000787b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180007880  jmp     loc_18000794D
0x180007885  mov     qword ptr [rcx], 0
0x18000788c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180007893  jz      loc_18000794D
0x180007899  lea     rcx, stru_180012060; SRWLock
0x1800078a0  call    cs:__imp_AcquireSRWLockExclusive
0x1800078a6  cmp     cs:qword_1800120D0, 0
0x1800078ae  jnz     short loc_18000792B
0x1800078b0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800078b7  mov     cs:qword_1800120D0, 0
0x1800078c2  test    rax, rax
0x1800078c5  jnz     short loc_18000790A
0x1800078c7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800078ce  test    rax, rax
0x1800078d1  jnz     short loc_1800078E7
0x1800078d3  lea     rcx, ModuleName; "ntdll.dll"
0x1800078da  call    cs:__imp_GetModuleHandleW
0x1800078e0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800078e7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800078ee  mov     rcx, rax; hModule
0x1800078f1  call    cs:__imp_GetProcAddress
0x1800078f7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800078fe  test    rax, rax
0x180007901  jnz     short loc_18000790A
0x180007903  mov     eax, 0C0000139h
0x180007908  jmp     short loc_180007927
0x18000790a  lea     r9, qword_1800120D0
0x180007911  xor     r8d, r8d
0x180007914  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000791b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180007922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007927  test    eax, eax
0x180007929  jnz     short loc_180007940
0x18000792b  mov     r9, rdi; void *
0x18000792e  lea     rcx, CriticalSection; this
0x180007935  mov     r8, rsi; void (*)(void *)
0x180007938  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000793b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180007940  lea     rcx, stru_180012060; SRWLock
0x180007947  call    cs:__imp_ReleaseSRWLockExclusive
0x18000794d  mov     rbx, [rsp+38h+arg_0]
0x180007952  mov     rsi, [rsp+38h+arg_8]
0x180007957  add     rsp, 30h
0x18000795b  pop     rdi
0x18000795c  retn
```
