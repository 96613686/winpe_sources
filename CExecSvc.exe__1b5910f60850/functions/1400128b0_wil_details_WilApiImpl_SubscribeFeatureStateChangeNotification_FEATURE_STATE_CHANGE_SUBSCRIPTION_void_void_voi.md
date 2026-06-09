# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1400128b0`
- end: `0x1400129bd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x140012404`
- `0x140012508`
- `0x1400128b0`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140012951`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140012951`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001293a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001293a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140012900`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140012900`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400129a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400129a7`

## string_xrefs

- `0x140012933`: `ntdll.dll`
- `0x140012947`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_140031170);
      if ( qword_1400311E0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1400311E0 = 0;
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
               &qword_1400311E0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&stru_140031198,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_140031170);
    }
  }
}

```

## disassembly

```asm
0x1400128b0  mov     [rsp+arg_8], rbx
0x1400128b5  mov     [rsp+arg_10], rsi
0x1400128ba  push    rdi
0x1400128bb  sub     rsp, 30h
0x1400128bf  mov     rsi, r8
0x1400128c2  mov     rdi, rdx
0x1400128c5  mov     rbx, rcx
0x1400128c8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1400128cc  jnz     short loc_1400128E5
0x1400128ce  mov     r8, rdx; void (*)(void *)
0x1400128d1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1400128d4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1400128db  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x1400128e0  jmp     loc_1400129AD
0x1400128e5  mov     qword ptr [rcx], 0
0x1400128ec  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1400128f3  jz      loc_1400129AD
0x1400128f9  lea     rcx, stru_140031170; SRWLock
0x140012900  call    cs:__imp_AcquireSRWLockExclusive
0x140012906  cmp     cs:qword_1400311E0, 0
0x14001290e  jnz     short loc_14001298B
0x140012910  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140012917  mov     cs:qword_1400311E0, 0
0x140012922  test    rax, rax
0x140012925  jnz     short loc_14001296A
0x140012927  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001292e  test    rax, rax
0x140012931  jnz     short loc_140012947
0x140012933  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14001293a  call    cs:__imp_GetModuleHandleW
0x140012940  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140012947  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14001294e  mov     rcx, rax; hModule
0x140012951  call    cs:__imp_GetProcAddress
0x140012957  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14001295e  test    rax, rax
0x140012961  jnz     short loc_14001296A
0x140012963  mov     eax, 0C0000139h
0x140012968  jmp     short loc_140012987
0x14001296a  lea     r9, qword_1400311E0
0x140012971  xor     r8d, r8d
0x140012974  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14001297b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x140012982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012987  test    eax, eax
0x140012989  jnz     short loc_1400129A0
0x14001298b  mov     r9, rsi; void *
0x14001298e  lea     rcx, stru_140031198; this
0x140012995  mov     r8, rdi; void (*)(void *)
0x140012998  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14001299b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1400129a0  lea     rcx, stru_140031170; SRWLock
0x1400129a7  call    cs:__imp_ReleaseSRWLockExclusive
0x1400129ad  mov     rbx, [rsp+38h+arg_8]
0x1400129b2  mov     rsi, [rsp+38h+arg_10]
0x1400129b7  add     rsp, 30h
0x1400129bb  pop     rdi
0x1400129bc  retn
```
