# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180027a00`
- end: `0x180027b0d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1800272fc`
- `0x1800273f8`
- `0x180027a00`
- `0x18005d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180027a8a`
- `KERNEL32!GetModuleHandleW` at `0x180027a8a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180027a50`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180027a50`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180027af7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180027af7`
- `KERNEL32!GetProcAddress` at `0x180027aa1`
- `KERNEL32!GetProcAddress` at `0x180027aa1`

## string_xrefs

- `0x180027a83`: `ntdll.dll`
- `0x180027a97`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_180072210 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180072210 = 0;
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
               &qword_180072210);
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
0x180027a00  mov     [rsp+arg_0], rbx
0x180027a05  mov     [rsp+arg_8], rsi
0x180027a0a  push    rdi
0x180027a0b  sub     rsp, 30h
0x180027a0f  mov     rdi, r8
0x180027a12  mov     rsi, rdx
0x180027a15  mov     rbx, rcx
0x180027a18  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180027a1c  jnz     short loc_180027A35
0x180027a1e  mov     r8, rdx; void (*)(void *)
0x180027a21  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180027a24  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180027a2b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180027a30  jmp     loc_180027AFD
0x180027a35  mov     qword ptr [rcx], 0
0x180027a3c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180027a43  jz      loc_180027AFD
0x180027a49  lea     rcx, SRWLock; SRWLock
0x180027a50  call    cs:__imp_AcquireSRWLockExclusive
0x180027a56  cmp     cs:qword_180072210, 0
0x180027a5e  jnz     short loc_180027ADB
0x180027a60  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180027a67  mov     cs:qword_180072210, 0
0x180027a72  test    rax, rax
0x180027a75  jnz     short loc_180027ABA
0x180027a77  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180027a7e  test    rax, rax
0x180027a81  jnz     short loc_180027A97
0x180027a83  lea     rcx, aNtdllDll; "ntdll.dll"
0x180027a8a  call    cs:__imp_GetModuleHandleW
0x180027a90  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180027a97  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180027a9e  mov     rcx, rax; hModule
0x180027aa1  call    cs:__imp_GetProcAddress
0x180027aa7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180027aae  test    rax, rax
0x180027ab1  jnz     short loc_180027ABA
0x180027ab3  mov     eax, 0C0000139h
0x180027ab8  jmp     short loc_180027AD7
0x180027aba  lea     r9, qword_180072210
0x180027ac1  xor     r8d, r8d
0x180027ac4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180027acb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180027ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ad7  test    eax, eax
0x180027ad9  jnz     short loc_180027AF0
0x180027adb  mov     r9, rdi; void *
0x180027ade  lea     rcx, CriticalSection; this
0x180027ae5  mov     r8, rsi; void (*)(void *)
0x180027ae8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180027aeb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180027af0  lea     rcx, SRWLock; SRWLock
0x180027af7  call    cs:__imp_ReleaseSRWLockExclusive
0x180027afd  mov     rbx, [rsp+38h+arg_0]
0x180027b02  mov     rsi, [rsp+38h+arg_8]
0x180027b07  add     rsp, 30h
0x180027b0b  pop     rdi
0x180027b0c  retn
```
