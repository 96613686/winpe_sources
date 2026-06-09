# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000ac50`
- end: `0x18000ad5d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000a11c`
- `0x18000a220`
- `0x18000ac50`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000acdd`
- `KERNEL32!GetModuleHandleW` at `0x18000acdd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ad4c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ad4c`
- `KERNEL32!GetProcAddress` at `0x18000acf4`
- `KERNEL32!GetProcAddress` at `0x18000acf4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000ac9e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000ac9e`

## string_xrefs

- `0x18000acd6`: `ntdll.dll`
- `0x18000acea`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
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
      AcquireSRWLockExclusive(&stru_180017040);
      if ( qword_1800170B0 )
      {
        v9 = 0;
      }
      else
      {
        qword_1800170B0 = 0;
        ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
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
                 &qword_1800170B0);
        else
          v9 = -1073741511;
      }
      if ( !v9 )
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180017040);
    }
  }
}

```

## disassembly

```asm
0x18000ac50  push    rbx
0x18000ac52  push    rsi
0x18000ac53  push    rdi
0x18000ac54  push    r14
0x18000ac56  sub     rsp, 38h
0x18000ac5a  mov     rdi, r8
0x18000ac5d  mov     rsi, rdx
0x18000ac60  mov     rbx, rcx
0x18000ac63  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000ac67  jnz     short loc_18000AC80
0x18000ac69  mov     r8, rdx; void (*)(void *)
0x18000ac6c  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000ac6f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000ac76  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000ac7b  jmp     loc_18000AD53
0x18000ac80  mov     qword ptr [rcx], 0
0x18000ac87  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000ac8e  jz      loc_18000AD53
0x18000ac94  lea     r14, stru_180017040
0x18000ac9b  mov     rcx, r14; SRWLock
0x18000ac9e  call    cs:__imp_AcquireSRWLockExclusive
0x18000aca4  mov     [rsp+58h+arg_10], r14
0x18000aca9  cmp     cs:qword_1800170B0, 0
0x18000acb1  jnz     short loc_18000AD2D
0x18000acb3  mov     cs:qword_1800170B0, 0
0x18000acbe  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000acc5  test    rax, rax
0x18000acc8  jnz     short loc_18000AD0E
0x18000acca  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000acd1  test    rax, rax
0x18000acd4  jnz     short loc_18000ACEA
0x18000acd6  lea     rcx, ModuleName; "ntdll.dll"
0x18000acdd  call    cs:__imp_GetModuleHandleW
0x18000ace3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000acea  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000acf1  mov     rcx, rax; hModule
0x18000acf4  call    cs:__imp_GetProcAddress
0x18000acfa  nop
0x18000acfb  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000ad02  test    rax, rax
0x18000ad05  jnz     short loc_18000AD0E
0x18000ad07  mov     eax, 0C0000139h
0x18000ad0c  jmp     short loc_18000AD2F
0x18000ad0e  lea     r9, qword_1800170B0
0x18000ad15  xor     r8d, r8d
0x18000ad18  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000ad1f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000ad26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad2b  jmp     short loc_18000AD2F
0x18000ad2d  xor     eax, eax
0x18000ad2f  test    eax, eax
0x18000ad31  jnz     short loc_18000AD49
0x18000ad33  mov     r9, rdi; void *
0x18000ad36  mov     r8, rsi; void (*)(void *)
0x18000ad39  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000ad3c  lea     rcx, CriticalSection; this
0x18000ad43  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000ad48  nop
0x18000ad49  mov     rcx, r14; SRWLock
0x18000ad4c  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ad52  nop
0x18000ad53  add     rsp, 38h
0x18000ad57  pop     r14
0x18000ad59  pop     rdi
0x18000ad5a  pop     rsi
0x18000ad5b  pop     rbx
0x18000ad5c  retn
```
