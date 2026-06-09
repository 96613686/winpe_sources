# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180024180`
- end: `0x18002428d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18002329c`
- `0x180023398`
- `0x180024180`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002420a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002420a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024221`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024221`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024277`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024277`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800241d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800241d0`

## string_xrefs

- `0x180024203`: `ntdll.dll`
- `0x180024217`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_180051128 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180051128 = 0;
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
               &qword_180051128);
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
0x180024180  mov     [rsp+arg_0], rbx
0x180024185  mov     [rsp+arg_8], rsi
0x18002418a  push    rdi
0x18002418b  sub     rsp, 30h
0x18002418f  mov     rdi, r8
0x180024192  mov     rsi, rdx
0x180024195  mov     rbx, rcx
0x180024198  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18002419c  jnz     short loc_1800241B5
0x18002419e  mov     r8, rdx; void (*)(void *)
0x1800241a1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800241a4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800241ab  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x1800241b0  jmp     loc_18002427D
0x1800241b5  mov     qword ptr [rcx], 0
0x1800241bc  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800241c3  jz      loc_18002427D
0x1800241c9  lea     rcx, SRWLock; SRWLock
0x1800241d0  call    cs:__imp_AcquireSRWLockExclusive
0x1800241d6  cmp     cs:qword_180051128, 0
0x1800241de  jnz     short loc_18002425B
0x1800241e0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800241e7  mov     cs:qword_180051128, 0
0x1800241f2  test    rax, rax
0x1800241f5  jnz     short loc_18002423A
0x1800241f7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800241fe  test    rax, rax
0x180024201  jnz     short loc_180024217
0x180024203  lea     rcx, LibFileName; "ntdll.dll"
0x18002420a  call    cs:__imp_GetModuleHandleW
0x180024210  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180024217  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18002421e  mov     rcx, rax; hModule
0x180024221  call    cs:__imp_GetProcAddress
0x180024227  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18002422e  test    rax, rax
0x180024231  jnz     short loc_18002423A
0x180024233  mov     eax, 0C0000139h
0x180024238  jmp     short loc_180024257
0x18002423a  lea     r9, qword_180051128
0x180024241  xor     r8d, r8d
0x180024244  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18002424b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180024252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024257  test    eax, eax
0x180024259  jnz     short loc_180024270
0x18002425b  mov     r9, rdi; void *
0x18002425e  lea     rcx, CriticalSection; this
0x180024265  mov     r8, rsi; void (*)(void *)
0x180024268  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18002426b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180024270  lea     rcx, SRWLock; SRWLock
0x180024277  call    cs:__imp_ReleaseSRWLockExclusive
0x18002427d  mov     rbx, [rsp+38h+arg_0]
0x180024282  mov     rsi, [rsp+38h+arg_8]
0x180024287  add     rsp, 30h
0x18002428b  pop     rdi
0x18002428c  retn
```
