# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14000ca10`
- end: `0x14000cb1d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x14000c350`
- `0x14000c44c`
- `0x14000ca10`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000ca9a`
- `KERNEL32!GetModuleHandleW` at `0x14000ca9a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000ca60`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000ca60`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000cb07`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000cb07`
- `KERNEL32!GetProcAddress` at `0x14000cab1`
- `KERNEL32!GetProcAddress` at `0x14000cab1`

## string_xrefs

- `0x14000ca93`: `ntdll.dll`
- `0x14000caa7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_1400160A0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1400160A0 = 0;
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
               &qword_1400160A0);
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
0x14000ca10  mov     [rsp+arg_0], rbx
0x14000ca15  mov     [rsp+arg_8], rsi
0x14000ca1a  push    rdi
0x14000ca1b  sub     rsp, 30h
0x14000ca1f  mov     rdi, r8
0x14000ca22  mov     rsi, rdx
0x14000ca25  mov     rbx, rcx
0x14000ca28  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14000ca2c  jnz     short loc_14000CA45
0x14000ca2e  mov     r8, rdx; void (*)(void *)
0x14000ca31  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000ca34  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000ca3b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x14000ca40  jmp     loc_14000CB0D
0x14000ca45  mov     qword ptr [rcx], 0
0x14000ca4c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000ca53  jz      loc_14000CB0D
0x14000ca59  lea     rcx, SRWLock; SRWLock
0x14000ca60  call    cs:__imp_AcquireSRWLockExclusive
0x14000ca66  cmp     cs:qword_1400160A0, 0
0x14000ca6e  jnz     short loc_14000CAEB
0x14000ca70  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000ca77  mov     cs:qword_1400160A0, 0
0x14000ca82  test    rax, rax
0x14000ca85  jnz     short loc_14000CACA
0x14000ca87  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000ca8e  test    rax, rax
0x14000ca91  jnz     short loc_14000CAA7
0x14000ca93  lea     rcx, ModuleName; "ntdll.dll"
0x14000ca9a  call    cs:__imp_GetModuleHandleW
0x14000caa0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000caa7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000caae  mov     rcx, rax; hModule
0x14000cab1  call    cs:__imp_GetProcAddress
0x14000cab7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000cabe  test    rax, rax
0x14000cac1  jnz     short loc_14000CACA
0x14000cac3  mov     eax, 0C0000139h
0x14000cac8  jmp     short loc_14000CAE7
0x14000caca  lea     r9, qword_1400160A0
0x14000cad1  xor     r8d, r8d
0x14000cad4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000cadb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x14000cae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cae7  test    eax, eax
0x14000cae9  jnz     short loc_14000CB00
0x14000caeb  mov     r9, rdi; void *
0x14000caee  lea     rcx, CriticalSection; this
0x14000caf5  mov     r8, rsi; void (*)(void *)
0x14000caf8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000cafb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x14000cb00  lea     rcx, SRWLock; SRWLock
0x14000cb07  call    cs:__imp_ReleaseSRWLockExclusive
0x14000cb0d  mov     rbx, [rsp+38h+arg_0]
0x14000cb12  mov     rsi, [rsp+38h+arg_8]
0x14000cb17  add     rsp, 30h
0x14000cb1b  pop     rdi
0x14000cb1c  retn
```
