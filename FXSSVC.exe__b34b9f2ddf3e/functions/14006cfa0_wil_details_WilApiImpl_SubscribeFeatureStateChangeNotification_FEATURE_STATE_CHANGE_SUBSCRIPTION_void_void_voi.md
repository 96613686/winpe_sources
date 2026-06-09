# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14006cfa0`
- end: `0x14006d0ad`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x14006c8c4`
- `0x14006c9c0`
- `0x14006cfa0`
- `0x140085010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14006cff0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14006cff0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14006d097`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14006d097`
- `KERNEL32!GetProcAddress` at `0x14006d041`
- `KERNEL32!GetProcAddress` at `0x14006d041`
- `KERNEL32!GetModuleHandleW` at `0x14006d02a`
- `KERNEL32!GetModuleHandleW` at `0x14006d02a`

## string_xrefs

- `0x14006d023`: `ntdll.dll`
- `0x14006d037`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_14009D918 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_14009D918 = 0;
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
               &qword_14009D918);
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
0x14006cfa0  mov     [rsp+arg_0], rbx
0x14006cfa5  mov     [rsp+arg_8], rsi
0x14006cfaa  push    rdi
0x14006cfab  sub     rsp, 30h
0x14006cfaf  mov     rdi, r8
0x14006cfb2  mov     rsi, rdx
0x14006cfb5  mov     rbx, rcx
0x14006cfb8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14006cfbc  jnz     short loc_14006CFD5
0x14006cfbe  mov     r8, rdx; void (*)(void *)
0x14006cfc1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14006cfc4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14006cfcb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x14006cfd0  jmp     loc_14006D09D
0x14006cfd5  mov     qword ptr [rcx], 0
0x14006cfdc  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14006cfe3  jz      loc_14006D09D
0x14006cfe9  lea     rcx, SRWLock; SRWLock
0x14006cff0  call    cs:__imp_AcquireSRWLockExclusive
0x14006cff6  cmp     cs:qword_14009D918, 0
0x14006cffe  jnz     short loc_14006D07B
0x14006d000  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14006d007  mov     cs:qword_14009D918, 0
0x14006d012  test    rax, rax
0x14006d015  jnz     short loc_14006D05A
0x14006d017  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14006d01e  test    rax, rax
0x14006d021  jnz     short loc_14006D037
0x14006d023  lea     rcx, ModuleName; "ntdll.dll"
0x14006d02a  call    cs:__imp_GetModuleHandleW
0x14006d030  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14006d037  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14006d03e  mov     rcx, rax; hModule
0x14006d041  call    cs:__imp_GetProcAddress
0x14006d047  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14006d04e  test    rax, rax
0x14006d051  jnz     short loc_14006D05A
0x14006d053  mov     eax, 0C0000139h
0x14006d058  jmp     short loc_14006D077
0x14006d05a  lea     r9, qword_14009D918
0x14006d061  xor     r8d, r8d
0x14006d064  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14006d06b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x14006d072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006d077  test    eax, eax
0x14006d079  jnz     short loc_14006D090
0x14006d07b  mov     r9, rdi; void *
0x14006d07e  lea     rcx, CriticalSection; this
0x14006d085  mov     r8, rsi; void (*)(void *)
0x14006d088  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14006d08b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x14006d090  lea     rcx, SRWLock; SRWLock
0x14006d097  call    cs:__imp_ReleaseSRWLockExclusive
0x14006d09d  mov     rbx, [rsp+38h+arg_0]
0x14006d0a2  mov     rsi, [rsp+38h+arg_8]
0x14006d0a7  add     rsp, 30h
0x14006d0ab  pop     rdi
0x14006d0ac  retn
```
