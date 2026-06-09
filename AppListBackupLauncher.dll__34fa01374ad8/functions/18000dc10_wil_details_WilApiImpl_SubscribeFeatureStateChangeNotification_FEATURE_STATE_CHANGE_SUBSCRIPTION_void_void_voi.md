# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000dc10`
- end: `0x18000dd1d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000d428`
- `0x18000d524`
- `0x18000dc10`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dcb1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dcb1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dc9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dc9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dd07`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dd07`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000dc60`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000dc60`

## string_xrefs

- `0x18000dc93`: `ntdll.dll`
- `0x18000dca7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180019058);
      if ( qword_1800190C8 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800190C8 = 0;
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
               &qword_1800190C8);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180019058);
    }
  }
}

```

## disassembly

```asm
0x18000dc10  mov     [rsp+arg_0], rbx
0x18000dc15  mov     [rsp+arg_8], rsi
0x18000dc1a  push    rdi
0x18000dc1b  sub     rsp, 30h
0x18000dc1f  mov     rdi, r8
0x18000dc22  mov     rsi, rdx
0x18000dc25  mov     rbx, rcx
0x18000dc28  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000dc2c  jnz     short loc_18000DC45
0x18000dc2e  mov     r8, rdx; void (*)(void *)
0x18000dc31  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000dc34  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000dc3b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000dc40  jmp     loc_18000DD0D
0x18000dc45  mov     qword ptr [rcx], 0
0x18000dc4c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000dc53  jz      loc_18000DD0D
0x18000dc59  lea     rcx, stru_180019058; SRWLock
0x18000dc60  call    cs:__imp_AcquireSRWLockExclusive
0x18000dc66  cmp     cs:qword_1800190C8, 0
0x18000dc6e  jnz     short loc_18000DCEB
0x18000dc70  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000dc77  mov     cs:qword_1800190C8, 0
0x18000dc82  test    rax, rax
0x18000dc85  jnz     short loc_18000DCCA
0x18000dc87  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000dc8e  test    rax, rax
0x18000dc91  jnz     short loc_18000DCA7
0x18000dc93  lea     rcx, ModuleName; "ntdll.dll"
0x18000dc9a  call    cs:__imp_GetModuleHandleW
0x18000dca0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000dca7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000dcae  mov     rcx, rax; hModule
0x18000dcb1  call    cs:__imp_GetProcAddress
0x18000dcb7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000dcbe  test    rax, rax
0x18000dcc1  jnz     short loc_18000DCCA
0x18000dcc3  mov     eax, 0C0000139h
0x18000dcc8  jmp     short loc_18000DCE7
0x18000dcca  lea     r9, qword_1800190C8
0x18000dcd1  xor     r8d, r8d
0x18000dcd4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000dcdb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000dce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dce7  test    eax, eax
0x18000dce9  jnz     short loc_18000DD00
0x18000dceb  mov     r9, rdi; void *
0x18000dcee  lea     rcx, CriticalSection; this
0x18000dcf5  mov     r8, rsi; void (*)(void *)
0x18000dcf8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000dcfb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000dd00  lea     rcx, stru_180019058; SRWLock
0x18000dd07  call    cs:__imp_ReleaseSRWLockExclusive
0x18000dd0d  mov     rbx, [rsp+38h+arg_0]
0x18000dd12  mov     rsi, [rsp+38h+arg_8]
0x18000dd17  add     rsp, 30h
0x18000dd1b  pop     rdi
0x18000dd1c  retn
```
