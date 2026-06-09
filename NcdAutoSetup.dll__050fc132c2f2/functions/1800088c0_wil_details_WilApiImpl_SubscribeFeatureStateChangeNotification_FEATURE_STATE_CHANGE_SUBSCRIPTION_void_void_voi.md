# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1800088c0`
- end: `0x1800089cd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180008200`
- `0x1800082fc`
- `0x1800088c0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000894a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000894a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008961`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008961`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800089b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800089b7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008910`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008910`

## string_xrefs

- `0x180008943`: `ntdll.dll`
- `0x180008957`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_18001A308 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18001A308 = 0;
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
               &qword_18001A308);
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
0x1800088c0  mov     [rsp+arg_0], rbx
0x1800088c5  mov     [rsp+arg_8], rsi
0x1800088ca  push    rdi
0x1800088cb  sub     rsp, 30h
0x1800088cf  mov     rdi, r8
0x1800088d2  mov     rsi, rdx
0x1800088d5  mov     rbx, rcx
0x1800088d8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800088dc  jnz     short loc_1800088F5
0x1800088de  mov     r8, rdx; void (*)(void *)
0x1800088e1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800088e4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800088eb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x1800088f0  jmp     loc_1800089BD
0x1800088f5  mov     qword ptr [rcx], 0
0x1800088fc  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180008903  jz      loc_1800089BD
0x180008909  lea     rcx, SRWLock; SRWLock
0x180008910  call    cs:__imp_AcquireSRWLockExclusive
0x180008916  cmp     cs:qword_18001A308, 0
0x18000891e  jnz     short loc_18000899B
0x180008920  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180008927  mov     cs:qword_18001A308, 0
0x180008932  test    rax, rax
0x180008935  jnz     short loc_18000897A
0x180008937  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000893e  test    rax, rax
0x180008941  jnz     short loc_180008957
0x180008943  lea     rcx, ModuleName; "ntdll.dll"
0x18000894a  call    cs:__imp_GetModuleHandleW
0x180008950  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008957  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000895e  mov     rcx, rax; hModule
0x180008961  call    cs:__imp_GetProcAddress
0x180008967  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000896e  test    rax, rax
0x180008971  jnz     short loc_18000897A
0x180008973  mov     eax, 0C0000139h
0x180008978  jmp     short loc_180008997
0x18000897a  lea     r9, qword_18001A308
0x180008981  xor     r8d, r8d
0x180008984  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000898b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180008992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008997  test    eax, eax
0x180008999  jnz     short loc_1800089B0
0x18000899b  mov     r9, rdi; void *
0x18000899e  lea     rcx, CriticalSection; this
0x1800089a5  mov     r8, rsi; void (*)(void *)
0x1800089a8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800089ab  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800089b0  lea     rcx, SRWLock; SRWLock
0x1800089b7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800089bd  mov     rbx, [rsp+38h+arg_0]
0x1800089c2  mov     rsi, [rsp+38h+arg_8]
0x1800089c7  add     rsp, 30h
0x1800089cb  pop     rdi
0x1800089cc  retn
```
