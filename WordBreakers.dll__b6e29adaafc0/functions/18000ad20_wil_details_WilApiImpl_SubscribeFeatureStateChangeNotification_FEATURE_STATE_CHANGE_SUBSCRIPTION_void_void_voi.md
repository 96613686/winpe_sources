# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000ad20`
- end: `0x18000ae2d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000a8e4`
- `0x18000a9e0`
- `0x18000ad20`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000adc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000adc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000adaa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000adaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ae17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ae17`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ad70`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ad70`

## string_xrefs

- `0x18000ada3`: `ntdll.dll`
- `0x18000adb7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_1800121A8 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800121A8 = 0;
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
               &qword_1800121A8);
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
0x18000ad20  mov     [rsp+arg_0], rbx
0x18000ad25  mov     [rsp+arg_8], rsi
0x18000ad2a  push    rdi
0x18000ad2b  sub     rsp, 30h
0x18000ad2f  mov     rdi, r8
0x18000ad32  mov     rsi, rdx
0x18000ad35  mov     rbx, rcx
0x18000ad38  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000ad3c  jnz     short loc_18000AD55
0x18000ad3e  mov     r8, rdx; void (*)(void *)
0x18000ad41  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000ad44  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000ad4b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000ad50  jmp     loc_18000AE1D
0x18000ad55  mov     qword ptr [rcx], 0
0x18000ad5c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000ad63  jz      loc_18000AE1D
0x18000ad69  lea     rcx, SRWLock; SRWLock
0x18000ad70  call    cs:__imp_AcquireSRWLockExclusive
0x18000ad76  cmp     cs:qword_1800121A8, 0
0x18000ad7e  jnz     short loc_18000ADFB
0x18000ad80  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000ad87  mov     cs:qword_1800121A8, 0
0x18000ad92  test    rax, rax
0x18000ad95  jnz     short loc_18000ADDA
0x18000ad97  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ad9e  test    rax, rax
0x18000ada1  jnz     short loc_18000ADB7
0x18000ada3  lea     rcx, ModuleName; "ntdll.dll"
0x18000adaa  call    cs:__imp_GetModuleHandleW
0x18000adb0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000adb7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000adbe  mov     rcx, rax; hModule
0x18000adc1  call    cs:__imp_GetProcAddress
0x18000adc7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000adce  test    rax, rax
0x18000add1  jnz     short loc_18000ADDA
0x18000add3  mov     eax, 0C0000139h
0x18000add8  jmp     short loc_18000ADF7
0x18000adda  lea     r9, qword_1800121A8
0x18000ade1  xor     r8d, r8d
0x18000ade4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000adeb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000adf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adf7  test    eax, eax
0x18000adf9  jnz     short loc_18000AE10
0x18000adfb  mov     r9, rdi; void *
0x18000adfe  lea     rcx, CriticalSection; this
0x18000ae05  mov     r8, rsi; void (*)(void *)
0x18000ae08  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000ae0b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000ae10  lea     rcx, SRWLock; SRWLock
0x18000ae17  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ae1d  mov     rbx, [rsp+38h+arg_0]
0x18000ae22  mov     rsi, [rsp+38h+arg_8]
0x18000ae27  add     rsp, 30h
0x18000ae2b  pop     rdi
0x18000ae2c  retn
```
