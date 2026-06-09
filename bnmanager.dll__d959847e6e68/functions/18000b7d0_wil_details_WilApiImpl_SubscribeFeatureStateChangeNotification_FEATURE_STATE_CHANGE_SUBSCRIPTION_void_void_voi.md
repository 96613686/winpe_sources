# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000b7d0`
- end: `0x18000b8dd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000b0cc`
- `0x18000b1c8`
- `0x18000b7d0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b85a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b85a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b871`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b871`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b820`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b820`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b8c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b8c7`

## string_xrefs

- `0x18000b853`: `ntdll.dll`
- `0x18000b867`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_1800140A0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800140A0 = 0;
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
               &qword_1800140A0);
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
0x18000b7d0  mov     [rsp+arg_0], rbx
0x18000b7d5  mov     [rsp+arg_8], rsi
0x18000b7da  push    rdi
0x18000b7db  sub     rsp, 30h
0x18000b7df  mov     rdi, r8
0x18000b7e2  mov     rsi, rdx
0x18000b7e5  mov     rbx, rcx
0x18000b7e8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000b7ec  jnz     short loc_18000B805
0x18000b7ee  mov     r8, rdx; void (*)(void *)
0x18000b7f1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000b7f4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000b7fb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000b800  jmp     loc_18000B8CD
0x18000b805  mov     qword ptr [rcx], 0
0x18000b80c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000b813  jz      loc_18000B8CD
0x18000b819  lea     rcx, SRWLock; SRWLock
0x18000b820  call    cs:__imp_AcquireSRWLockExclusive
0x18000b826  cmp     cs:qword_1800140A0, 0
0x18000b82e  jnz     short loc_18000B8AB
0x18000b830  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000b837  mov     cs:qword_1800140A0, 0
0x18000b842  test    rax, rax
0x18000b845  jnz     short loc_18000B88A
0x18000b847  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b84e  test    rax, rax
0x18000b851  jnz     short loc_18000B867
0x18000b853  lea     rcx, ModuleName; "ntdll.dll"
0x18000b85a  call    cs:__imp_GetModuleHandleW
0x18000b860  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b867  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000b86e  mov     rcx, rax; hModule
0x18000b871  call    cs:__imp_GetProcAddress
0x18000b877  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000b87e  test    rax, rax
0x18000b881  jnz     short loc_18000B88A
0x18000b883  mov     eax, 0C0000139h
0x18000b888  jmp     short loc_18000B8A7
0x18000b88a  lea     r9, qword_1800140A0
0x18000b891  xor     r8d, r8d
0x18000b894  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000b89b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000b8a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8a7  test    eax, eax
0x18000b8a9  jnz     short loc_18000B8C0
0x18000b8ab  mov     r9, rdi; void *
0x18000b8ae  lea     rcx, CriticalSection; this
0x18000b8b5  mov     r8, rsi; void (*)(void *)
0x18000b8b8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000b8bb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000b8c0  lea     rcx, SRWLock; SRWLock
0x18000b8c7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b8cd  mov     rbx, [rsp+38h+arg_0]
0x18000b8d2  mov     rsi, [rsp+38h+arg_8]
0x18000b8d7  add     rsp, 30h
0x18000b8db  pop     rdi
0x18000b8dc  retn
```
