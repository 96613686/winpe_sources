# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180009e50`
- end: `0x180009f4e`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `254`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180009618`
- `0x18000971c`
- `0x180009e50`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009eea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009eea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009ed3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009ed3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009e99`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009e99`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009f40`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009f40`

## string_xrefs

- `0x180009ecc`: `ntdll.dll`
- `0x180009ee0`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180015070);
      if ( qword_1800150E0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800150E0 = 0;
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
               &qword_1800150E0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180015070);
    }
  }
}

```

## disassembly

```asm
0x180009e50  push    rbx
0x180009e52  push    rsi
0x180009e53  push    rdi
0x180009e54  sub     rsp, 30h
0x180009e58  mov     rsi, r8
0x180009e5b  mov     rdi, rdx
0x180009e5e  mov     rbx, rcx
0x180009e61  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180009e65  jnz     short loc_180009E7E
0x180009e67  mov     r8, rdx; void (*)(void *)
0x180009e6a  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180009e6d  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180009e74  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180009e79  jmp     loc_180009F46
0x180009e7e  mov     qword ptr [rcx], 0
0x180009e85  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009e8c  jz      loc_180009F46
0x180009e92  lea     rcx, stru_180015070; SRWLock
0x180009e99  call    cs:__imp_AcquireSRWLockExclusive
0x180009e9f  cmp     cs:qword_1800150E0, 0
0x180009ea7  jnz     short loc_180009F24
0x180009ea9  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180009eb0  mov     cs:qword_1800150E0, 0
0x180009ebb  test    rax, rax
0x180009ebe  jnz     short loc_180009F03
0x180009ec0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009ec7  test    rax, rax
0x180009eca  jnz     short loc_180009EE0
0x180009ecc  lea     rcx, ModuleName; "ntdll.dll"
0x180009ed3  call    cs:__imp_GetModuleHandleW
0x180009ed9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009ee0  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180009ee7  mov     rcx, rax; hModule
0x180009eea  call    cs:__imp_GetProcAddress
0x180009ef0  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180009ef7  test    rax, rax
0x180009efa  jnz     short loc_180009F03
0x180009efc  mov     eax, 0C0000139h
0x180009f01  jmp     short loc_180009F20
0x180009f03  lea     r9, qword_1800150E0
0x180009f0a  xor     r8d, r8d
0x180009f0d  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009f14  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180009f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f20  test    eax, eax
0x180009f22  jnz     short loc_180009F39
0x180009f24  mov     r9, rsi; void *
0x180009f27  lea     rcx, CriticalSection; this
0x180009f2e  mov     r8, rdi; void (*)(void *)
0x180009f31  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180009f34  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180009f39  lea     rcx, stru_180015070; SRWLock
0x180009f40  call    cs:__imp_ReleaseSRWLockExclusive
0x180009f46  add     rsp, 30h
0x180009f4a  pop     rdi
0x180009f4b  pop     rsi
0x180009f4c  pop     rbx
0x180009f4d  retn
```
