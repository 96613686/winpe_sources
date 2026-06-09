# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x140009d10`
- end: `0x140009e1d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x140009580`
- `0x14000967c`
- `0x140009d10`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009d9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009d9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009db1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009db1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009d60`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009d60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009e07`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009e07`

## string_xrefs

- `0x140009d93`: `ntdll.dll`
- `0x140009da7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_1400C81D0);
      if ( qword_1400C8240 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1400C8240 = 0;
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
               &qword_1400C8240);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_1400C81D0);
    }
  }
}

```

## disassembly

```asm
0x140009d10  mov     [rsp+arg_0], rbx
0x140009d15  mov     [rsp+arg_8], rsi
0x140009d1a  push    rdi
0x140009d1b  sub     rsp, 30h
0x140009d1f  mov     rdi, r8
0x140009d22  mov     rsi, rdx
0x140009d25  mov     rbx, rcx
0x140009d28  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140009d2c  jnz     short loc_140009D45
0x140009d2e  mov     r8, rdx; void (*)(void *)
0x140009d31  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140009d34  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x140009d3b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x140009d40  jmp     loc_140009E0D
0x140009d45  mov     qword ptr [rcx], 0
0x140009d4c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140009d53  jz      loc_140009E0D
0x140009d59  lea     rcx, stru_1400C81D0; SRWLock
0x140009d60  call    cs:__imp_AcquireSRWLockExclusive
0x140009d66  cmp     cs:qword_1400C8240, 0
0x140009d6e  jnz     short loc_140009DEB
0x140009d70  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140009d77  mov     cs:qword_1400C8240, 0
0x140009d82  test    rax, rax
0x140009d85  jnz     short loc_140009DCA
0x140009d87  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009d8e  test    rax, rax
0x140009d91  jnz     short loc_140009DA7
0x140009d93  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x140009d9a  call    cs:__imp_GetModuleHandleW
0x140009da0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009da7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x140009dae  mov     rcx, rax; hModule
0x140009db1  call    cs:__imp_GetProcAddress
0x140009db7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x140009dbe  test    rax, rax
0x140009dc1  jnz     short loc_140009DCA
0x140009dc3  mov     eax, 0C0000139h
0x140009dc8  jmp     short loc_140009DE7
0x140009dca  lea     r9, qword_1400C8240
0x140009dd1  xor     r8d, r8d
0x140009dd4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140009ddb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x140009de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009de7  test    eax, eax
0x140009de9  jnz     short loc_140009E00
0x140009deb  mov     r9, rdi; void *
0x140009dee  lea     rcx, CriticalSection; this
0x140009df5  mov     r8, rsi; void (*)(void *)
0x140009df8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140009dfb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x140009e00  lea     rcx, stru_1400C81D0; SRWLock
0x140009e07  call    cs:__imp_ReleaseSRWLockExclusive
0x140009e0d  mov     rbx, [rsp+38h+arg_0]
0x140009e12  mov     rsi, [rsp+38h+arg_8]
0x140009e17  add     rsp, 30h
0x140009e1b  pop     rdi
0x140009e1c  retn
```
