# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180009030`
- end: `0x18000913d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000887c`
- `0x180008978`
- `0x180009030`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800090ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800090ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800090d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800090d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009127`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009127`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009080`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009080`

## string_xrefs

- `0x1800090b3`: `ntdll.dll`
- `0x1800090c7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180044080);
      if ( qword_1800440F0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800440F0 = 0;
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
               &qword_1800440F0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180044080);
    }
  }
}

```

## disassembly

```asm
0x180009030  mov     [rsp+arg_0], rbx
0x180009035  mov     [rsp+arg_8], rsi
0x18000903a  push    rdi
0x18000903b  sub     rsp, 30h
0x18000903f  mov     rdi, r8
0x180009042  mov     rsi, rdx
0x180009045  mov     rbx, rcx
0x180009048  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000904c  jnz     short loc_180009065
0x18000904e  mov     r8, rdx; void (*)(void *)
0x180009051  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180009054  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000905b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180009060  jmp     loc_18000912D
0x180009065  mov     qword ptr [rcx], 0
0x18000906c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009073  jz      loc_18000912D
0x180009079  lea     rcx, stru_180044080; SRWLock
0x180009080  call    cs:__imp_AcquireSRWLockExclusive
0x180009086  cmp     cs:qword_1800440F0, 0
0x18000908e  jnz     short loc_18000910B
0x180009090  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180009097  mov     cs:qword_1800440F0, 0
0x1800090a2  test    rax, rax
0x1800090a5  jnz     short loc_1800090EA
0x1800090a7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800090ae  test    rax, rax
0x1800090b1  jnz     short loc_1800090C7
0x1800090b3  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1800090ba  call    cs:__imp_GetModuleHandleW
0x1800090c0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800090c7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800090ce  mov     rcx, rax; hModule
0x1800090d1  call    cs:__imp_GetProcAddress
0x1800090d7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800090de  test    rax, rax
0x1800090e1  jnz     short loc_1800090EA
0x1800090e3  mov     eax, 0C0000139h
0x1800090e8  jmp     short loc_180009107
0x1800090ea  lea     r9, qword_1800440F0
0x1800090f1  xor     r8d, r8d
0x1800090f4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800090fb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180009102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009107  test    eax, eax
0x180009109  jnz     short loc_180009120
0x18000910b  mov     r9, rdi; void *
0x18000910e  lea     rcx, CriticalSection; this
0x180009115  mov     r8, rsi; void (*)(void *)
0x180009118  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000911b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180009120  lea     rcx, stru_180044080; SRWLock
0x180009127  call    cs:__imp_ReleaseSRWLockExclusive
0x18000912d  mov     rbx, [rsp+38h+arg_0]
0x180009132  mov     rsi, [rsp+38h+arg_8]
0x180009137  add     rsp, 30h
0x18000913b  pop     rdi
0x18000913c  retn
```
