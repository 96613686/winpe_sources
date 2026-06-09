# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14000d1b0`
- end: `0x14000d2bd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x14000cb5c`
- `0x14000cc58`
- `0x14000d1b0`
- `0x14000f010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000d251`
- `KERNEL32!GetProcAddress` at `0x14000d251`
- `KERNEL32!GetModuleHandleW` at `0x14000d23a`
- `KERNEL32!GetModuleHandleW` at `0x14000d23a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000d200`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000d200`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000d2a7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000d2a7`

## string_xrefs

- `0x14000d233`: `ntdll.dll`
- `0x14000d247`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_1400170B8);
      if ( qword_140017128 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_140017128 = 0;
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
        v9 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), void *, _QWORD, __int64 *))ProcAddress)(
               _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
               &wil::details::g_featureStateManager,
               0,
               &qword_140017128);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_1400170B8);
    }
  }
}

```

## disassembly

```asm
0x14000d1b0  mov     [rsp+arg_0], rbx
0x14000d1b5  mov     [rsp+arg_8], rsi
0x14000d1ba  push    rdi
0x14000d1bb  sub     rsp, 30h
0x14000d1bf  mov     rdi, r8
0x14000d1c2  mov     rsi, rdx
0x14000d1c5  mov     rbx, rcx
0x14000d1c8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14000d1cc  jnz     short loc_14000D1E5
0x14000d1ce  mov     r8, rdx; void (*)(void *)
0x14000d1d1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000d1d4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000d1db  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x14000d1e0  jmp     loc_14000D2AD
0x14000d1e5  mov     qword ptr [rcx], 0
0x14000d1ec  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000d1f3  jz      loc_14000D2AD
0x14000d1f9  lea     rcx, stru_1400170B8; SRWLock
0x14000d200  call    cs:__imp_AcquireSRWLockExclusive
0x14000d206  cmp     cs:qword_140017128, 0
0x14000d20e  jnz     short loc_14000D28B
0x14000d210  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000d217  mov     cs:qword_140017128, 0
0x14000d222  test    rax, rax
0x14000d225  jnz     short loc_14000D26A
0x14000d227  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000d22e  test    rax, rax
0x14000d231  jnz     short loc_14000D247
0x14000d233  lea     rcx, ModuleName; "ntdll.dll"
0x14000d23a  call    cs:__imp_GetModuleHandleW
0x14000d240  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000d247  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000d24e  mov     rcx, rax; hModule
0x14000d251  call    cs:__imp_GetProcAddress
0x14000d257  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000d25e  test    rax, rax
0x14000d261  jnz     short loc_14000D26A
0x14000d263  mov     eax, 0C0000139h
0x14000d268  jmp     short loc_14000D287
0x14000d26a  lea     r9, qword_140017128
0x14000d271  xor     r8d, r8d
0x14000d274  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000d27b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x14000d282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d287  test    eax, eax
0x14000d289  jnz     short loc_14000D2A0
0x14000d28b  mov     r9, rdi; void *
0x14000d28e  lea     rcx, CriticalSection; this
0x14000d295  mov     r8, rsi; void (*)(void *)
0x14000d298  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000d29b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x14000d2a0  lea     rcx, stru_1400170B8; SRWLock
0x14000d2a7  call    cs:__imp_ReleaseSRWLockExclusive
0x14000d2ad  mov     rbx, [rsp+38h+arg_0]
0x14000d2b2  mov     rsi, [rsp+38h+arg_8]
0x14000d2b7  add     rsp, 30h
0x14000d2bb  pop     rdi
0x14000d2bc  retn
```
