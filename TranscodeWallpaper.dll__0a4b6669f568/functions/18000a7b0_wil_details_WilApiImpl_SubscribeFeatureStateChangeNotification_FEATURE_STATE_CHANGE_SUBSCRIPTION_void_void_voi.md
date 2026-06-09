# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000a7b0`
- end: `0x18000a8bd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000a358`
- `0x18000a454`
- `0x18000a7b0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a851`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a851`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a83a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a83a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a8a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a8a7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a800`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a800`

## string_xrefs

- `0x18000a833`: `ntdll.dll`
- `0x18000a847`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_180016110 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180016110 = 0;
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
               &qword_180016110);
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
0x18000a7b0  mov     [rsp+arg_0], rbx
0x18000a7b5  mov     [rsp+arg_8], rsi
0x18000a7ba  push    rdi
0x18000a7bb  sub     rsp, 30h
0x18000a7bf  mov     rdi, r8
0x18000a7c2  mov     rsi, rdx
0x18000a7c5  mov     rbx, rcx
0x18000a7c8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000a7cc  jnz     short loc_18000A7E5
0x18000a7ce  mov     r8, rdx; void (*)(void *)
0x18000a7d1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000a7d4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000a7db  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000a7e0  jmp     loc_18000A8AD
0x18000a7e5  mov     qword ptr [rcx], 0
0x18000a7ec  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000a7f3  jz      loc_18000A8AD
0x18000a7f9  lea     rcx, SRWLock; SRWLock
0x18000a800  call    cs:__imp_AcquireSRWLockExclusive
0x18000a806  cmp     cs:qword_180016110, 0
0x18000a80e  jnz     short loc_18000A88B
0x18000a810  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000a817  mov     cs:qword_180016110, 0
0x18000a822  test    rax, rax
0x18000a825  jnz     short loc_18000A86A
0x18000a827  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a82e  test    rax, rax
0x18000a831  jnz     short loc_18000A847
0x18000a833  lea     rcx, ModuleName; "ntdll.dll"
0x18000a83a  call    cs:__imp_GetModuleHandleW
0x18000a840  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a847  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000a84e  mov     rcx, rax; hModule
0x18000a851  call    cs:__imp_GetProcAddress
0x18000a857  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000a85e  test    rax, rax
0x18000a861  jnz     short loc_18000A86A
0x18000a863  mov     eax, 0C0000139h
0x18000a868  jmp     short loc_18000A887
0x18000a86a  lea     r9, qword_180016110
0x18000a871  xor     r8d, r8d
0x18000a874  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000a87b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000a882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a887  test    eax, eax
0x18000a889  jnz     short loc_18000A8A0
0x18000a88b  mov     r9, rdi; void *
0x18000a88e  lea     rcx, CriticalSection; this
0x18000a895  mov     r8, rsi; void (*)(void *)
0x18000a898  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000a89b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000a8a0  lea     rcx, SRWLock; SRWLock
0x18000a8a7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a8ad  mov     rbx, [rsp+38h+arg_0]
0x18000a8b2  mov     rsi, [rsp+38h+arg_8]
0x18000a8b7  add     rsp, 30h
0x18000a8bb  pop     rdi
0x18000a8bc  retn
```
