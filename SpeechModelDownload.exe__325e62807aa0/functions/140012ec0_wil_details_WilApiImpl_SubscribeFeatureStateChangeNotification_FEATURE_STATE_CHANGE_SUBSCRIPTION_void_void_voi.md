# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x140012ec0`
- end: `0x140012fcd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1400122d0`
- `0x1400123cc`
- `0x140012ec0`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012f4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012f4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140012f61`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140012f61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140012fb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140012fb7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140012f10`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140012f10`

## string_xrefs

- `0x140012f43`: `ntdll.dll`
- `0x140012f57`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_140030158);
      if ( qword_1400301C8 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1400301C8 = 0;
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
               &qword_1400301C8);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_140030158);
    }
  }
}

```

## disassembly

```asm
0x140012ec0  mov     [rsp+arg_0], rbx
0x140012ec5  mov     [rsp+arg_8], rsi
0x140012eca  push    rdi
0x140012ecb  sub     rsp, 30h
0x140012ecf  mov     rdi, r8
0x140012ed2  mov     rsi, rdx
0x140012ed5  mov     rbx, rcx
0x140012ed8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140012edc  jnz     short loc_140012EF5
0x140012ede  mov     r8, rdx; void (*)(void *)
0x140012ee1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140012ee4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x140012eeb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x140012ef0  jmp     loc_140012FBD
0x140012ef5  mov     qword ptr [rcx], 0
0x140012efc  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140012f03  jz      loc_140012FBD
0x140012f09  lea     rcx, stru_140030158; SRWLock
0x140012f10  call    cs:__imp_AcquireSRWLockExclusive
0x140012f16  cmp     cs:qword_1400301C8, 0
0x140012f1e  jnz     short loc_140012F9B
0x140012f20  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140012f27  mov     cs:qword_1400301C8, 0
0x140012f32  test    rax, rax
0x140012f35  jnz     short loc_140012F7A
0x140012f37  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140012f3e  test    rax, rax
0x140012f41  jnz     short loc_140012F57
0x140012f43  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x140012f4a  call    cs:__imp_GetModuleHandleW
0x140012f50  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140012f57  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x140012f5e  mov     rcx, rax; hModule
0x140012f61  call    cs:__imp_GetProcAddress
0x140012f67  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x140012f6e  test    rax, rax
0x140012f71  jnz     short loc_140012F7A
0x140012f73  mov     eax, 0C0000139h
0x140012f78  jmp     short loc_140012F97
0x140012f7a  lea     r9, qword_1400301C8
0x140012f81  xor     r8d, r8d
0x140012f84  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140012f8b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x140012f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012f97  test    eax, eax
0x140012f99  jnz     short loc_140012FB0
0x140012f9b  mov     r9, rdi; void *
0x140012f9e  lea     rcx, CriticalSection; this
0x140012fa5  mov     r8, rsi; void (*)(void *)
0x140012fa8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140012fab  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x140012fb0  lea     rcx, stru_140030158; SRWLock
0x140012fb7  call    cs:__imp_ReleaseSRWLockExclusive
0x140012fbd  mov     rbx, [rsp+38h+arg_0]
0x140012fc2  mov     rsi, [rsp+38h+arg_8]
0x140012fc7  add     rsp, 30h
0x140012fcb  pop     rdi
0x140012fcc  retn
```
