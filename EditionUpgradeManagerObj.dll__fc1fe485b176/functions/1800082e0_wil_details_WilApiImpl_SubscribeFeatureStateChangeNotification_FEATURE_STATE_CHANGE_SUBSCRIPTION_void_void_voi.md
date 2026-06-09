# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1800082e0`
- end: `0x1800083ed`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180007b84`
- `0x180007c80`
- `0x1800082e0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008381`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008381`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000836a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000836a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800083d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800083d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008330`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008330`

## string_xrefs

- `0x180008363`: `ntdll.dll`
- `0x180008377`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_18002F260);
      if ( qword_18002F2D0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18002F2D0 = 0;
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
               &qword_18002F2D0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_18002F260);
    }
  }
}

```

## disassembly

```asm
0x1800082e0  mov     [rsp+arg_0], rbx
0x1800082e5  mov     [rsp+arg_8], rsi
0x1800082ea  push    rdi
0x1800082eb  sub     rsp, 30h
0x1800082ef  mov     rdi, r8
0x1800082f2  mov     rsi, rdx
0x1800082f5  mov     rbx, rcx
0x1800082f8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800082fc  jnz     short loc_180008315
0x1800082fe  mov     r8, rdx; void (*)(void *)
0x180008301  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180008304  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000830b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180008310  jmp     loc_1800083DD
0x180008315  mov     qword ptr [rcx], 0
0x18000831c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180008323  jz      loc_1800083DD
0x180008329  lea     rcx, stru_18002F260; SRWLock
0x180008330  call    cs:__imp_AcquireSRWLockExclusive
0x180008336  cmp     cs:qword_18002F2D0, 0
0x18000833e  jnz     short loc_1800083BB
0x180008340  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180008347  mov     cs:qword_18002F2D0, 0
0x180008352  test    rax, rax
0x180008355  jnz     short loc_18000839A
0x180008357  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000835e  test    rax, rax
0x180008361  jnz     short loc_180008377
0x180008363  lea     rcx, ModuleName; "ntdll.dll"
0x18000836a  call    cs:__imp_GetModuleHandleW
0x180008370  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008377  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000837e  mov     rcx, rax; hModule
0x180008381  call    cs:__imp_GetProcAddress
0x180008387  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000838e  test    rax, rax
0x180008391  jnz     short loc_18000839A
0x180008393  mov     eax, 0C0000139h
0x180008398  jmp     short loc_1800083B7
0x18000839a  lea     r9, qword_18002F2D0
0x1800083a1  xor     r8d, r8d
0x1800083a4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800083ab  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800083b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083b7  test    eax, eax
0x1800083b9  jnz     short loc_1800083D0
0x1800083bb  mov     r9, rdi; void *
0x1800083be  lea     rcx, CriticalSection; this
0x1800083c5  mov     r8, rsi; void (*)(void *)
0x1800083c8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800083cb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800083d0  lea     rcx, stru_18002F260; SRWLock
0x1800083d7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800083dd  mov     rbx, [rsp+38h+arg_0]
0x1800083e2  mov     rsi, [rsp+38h+arg_8]
0x1800083e7  add     rsp, 30h
0x1800083eb  pop     rdi
0x1800083ec  retn
```
