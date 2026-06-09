# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180007eb0`
- end: `0x180007fbd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180007764`
- `0x180007860`
- `0x180007eb0`
- `0x180017010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007fa7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007fa7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180007f00`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180007f00`
- `KERNEL32!GetModuleHandleW` at `0x180007f3a`
- `KERNEL32!GetModuleHandleW` at `0x180007f3a`
- `KERNEL32!GetProcAddress` at `0x180007f51`
- `KERNEL32!GetProcAddress` at `0x180007f51`

## string_xrefs

- `0x180007f33`: `ntdll.dll`
- `0x180007f47`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_1800201D0);
      if ( qword_180020240 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180020240 = 0;
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
               &qword_180020240);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_1800201D0);
    }
  }
}

```

## disassembly

```asm
0x180007eb0  mov     [rsp+arg_0], rbx
0x180007eb5  mov     [rsp+arg_8], rsi
0x180007eba  push    rdi
0x180007ebb  sub     rsp, 30h
0x180007ebf  mov     rdi, r8
0x180007ec2  mov     rsi, rdx
0x180007ec5  mov     rbx, rcx
0x180007ec8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180007ecc  jnz     short loc_180007EE5
0x180007ece  mov     r8, rdx; void (*)(void *)
0x180007ed1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180007ed4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180007edb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180007ee0  jmp     loc_180007FAD
0x180007ee5  mov     qword ptr [rcx], 0
0x180007eec  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180007ef3  jz      loc_180007FAD
0x180007ef9  lea     rcx, stru_1800201D0; SRWLock
0x180007f00  call    cs:__imp_AcquireSRWLockExclusive
0x180007f06  cmp     cs:qword_180020240, 0
0x180007f0e  jnz     short loc_180007F8B
0x180007f10  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180007f17  mov     cs:qword_180020240, 0
0x180007f22  test    rax, rax
0x180007f25  jnz     short loc_180007F6A
0x180007f27  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007f2e  test    rax, rax
0x180007f31  jnz     short loc_180007F47
0x180007f33  lea     rcx, ModuleName; "ntdll.dll"
0x180007f3a  call    cs:__imp_GetModuleHandleW
0x180007f40  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007f47  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180007f4e  mov     rcx, rax; hModule
0x180007f51  call    cs:__imp_GetProcAddress
0x180007f57  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180007f5e  test    rax, rax
0x180007f61  jnz     short loc_180007F6A
0x180007f63  mov     eax, 0C0000139h
0x180007f68  jmp     short loc_180007F87
0x180007f6a  lea     r9, qword_180020240
0x180007f71  xor     r8d, r8d
0x180007f74  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180007f7b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180007f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f87  test    eax, eax
0x180007f89  jnz     short loc_180007FA0
0x180007f8b  mov     r9, rdi; void *
0x180007f8e  lea     rcx, CriticalSection; this
0x180007f95  mov     r8, rsi; void (*)(void *)
0x180007f98  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180007f9b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180007fa0  lea     rcx, stru_1800201D0; SRWLock
0x180007fa7  call    cs:__imp_ReleaseSRWLockExclusive
0x180007fad  mov     rbx, [rsp+38h+arg_0]
0x180007fb2  mov     rsi, [rsp+38h+arg_8]
0x180007fb7  add     rsp, 30h
0x180007fbb  pop     rdi
0x180007fbc  retn
```
