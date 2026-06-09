# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180008280`
- end: `0x18000838d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180007b84`
- `0x180007c80`
- `0x180008280`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008321`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008321`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000830a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000830a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800082d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800082d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008377`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008377`

## string_xrefs

- `0x180008303`: `ntdll.dll`
- `0x180008317`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_1800172C0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800172C0 = 0;
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
               &qword_1800172C0);
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
0x180008280  mov     [rsp+arg_0], rbx
0x180008285  mov     [rsp+arg_8], rsi
0x18000828a  push    rdi
0x18000828b  sub     rsp, 30h
0x18000828f  mov     rdi, r8
0x180008292  mov     rsi, rdx
0x180008295  mov     rbx, rcx
0x180008298  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000829c  jnz     short loc_1800082B5
0x18000829e  mov     r8, rdx; void (*)(void *)
0x1800082a1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800082a4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800082ab  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x1800082b0  jmp     loc_18000837D
0x1800082b5  mov     qword ptr [rcx], 0
0x1800082bc  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800082c3  jz      loc_18000837D
0x1800082c9  lea     rcx, SRWLock; SRWLock
0x1800082d0  call    cs:__imp_AcquireSRWLockExclusive
0x1800082d6  cmp     cs:qword_1800172C0, 0
0x1800082de  jnz     short loc_18000835B
0x1800082e0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800082e7  mov     cs:qword_1800172C0, 0
0x1800082f2  test    rax, rax
0x1800082f5  jnz     short loc_18000833A
0x1800082f7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800082fe  test    rax, rax
0x180008301  jnz     short loc_180008317
0x180008303  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000830a  call    cs:__imp_GetModuleHandleW
0x180008310  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008317  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000831e  mov     rcx, rax; hModule
0x180008321  call    cs:__imp_GetProcAddress
0x180008327  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000832e  test    rax, rax
0x180008331  jnz     short loc_18000833A
0x180008333  mov     eax, 0C0000139h
0x180008338  jmp     short loc_180008357
0x18000833a  lea     r9, qword_1800172C0
0x180008341  xor     r8d, r8d
0x180008344  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000834b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180008352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008357  test    eax, eax
0x180008359  jnz     short loc_180008370
0x18000835b  mov     r9, rdi; void *
0x18000835e  lea     rcx, CriticalSection; this
0x180008365  mov     r8, rsi; void (*)(void *)
0x180008368  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000836b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180008370  lea     rcx, SRWLock; SRWLock
0x180008377  call    cs:__imp_ReleaseSRWLockExclusive
0x18000837d  mov     rbx, [rsp+38h+arg_0]
0x180008382  mov     rsi, [rsp+38h+arg_8]
0x180008387  add     rsp, 30h
0x18000838b  pop     rdi
0x18000838c  retn
```
