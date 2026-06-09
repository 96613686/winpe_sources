# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180010f90`
- end: `0x18001109d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180010758`
- `0x180010854`
- `0x180010f90`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180011031`
- `KERNEL32!GetProcAddress` at `0x180011031`
- `KERNEL32!GetModuleHandleW` at `0x18001101a`
- `KERNEL32!GetModuleHandleW` at `0x18001101a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180010fe0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180010fe0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011087`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011087`

## string_xrefs

- `0x180011013`: `ntdll.dll`
- `0x180011027`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180023118);
      if ( qword_180023188 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180023188 = 0;
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
               &qword_180023188);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180023118);
    }
  }
}

```

## disassembly

```asm
0x180010f90  mov     [rsp+arg_0], rbx
0x180010f95  mov     [rsp+arg_8], rsi
0x180010f9a  push    rdi
0x180010f9b  sub     rsp, 30h
0x180010f9f  mov     rdi, r8
0x180010fa2  mov     rsi, rdx
0x180010fa5  mov     rbx, rcx
0x180010fa8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180010fac  jnz     short loc_180010FC5
0x180010fae  mov     r8, rdx; void (*)(void *)
0x180010fb1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180010fb4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180010fbb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180010fc0  jmp     loc_18001108D
0x180010fc5  mov     qword ptr [rcx], 0
0x180010fcc  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180010fd3  jz      loc_18001108D
0x180010fd9  lea     rcx, stru_180023118; SRWLock
0x180010fe0  call    cs:__imp_AcquireSRWLockExclusive
0x180010fe6  cmp     cs:qword_180023188, 0
0x180010fee  jnz     short loc_18001106B
0x180010ff0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180010ff7  mov     cs:qword_180023188, 0
0x180011002  test    rax, rax
0x180011005  jnz     short loc_18001104A
0x180011007  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001100e  test    rax, rax
0x180011011  jnz     short loc_180011027
0x180011013  lea     rcx, ModuleName; "ntdll.dll"
0x18001101a  call    cs:__imp_GetModuleHandleW
0x180011020  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011027  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001102e  mov     rcx, rax; hModule
0x180011031  call    cs:__imp_GetProcAddress
0x180011037  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001103e  test    rax, rax
0x180011041  jnz     short loc_18001104A
0x180011043  mov     eax, 0C0000139h
0x180011048  jmp     short loc_180011067
0x18001104a  lea     r9, qword_180023188
0x180011051  xor     r8d, r8d
0x180011054  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001105b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180011062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011067  test    eax, eax
0x180011069  jnz     short loc_180011080
0x18001106b  mov     r9, rdi; void *
0x18001106e  lea     rcx, CriticalSection; this
0x180011075  mov     r8, rsi; void (*)(void *)
0x180011078  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18001107b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180011080  lea     rcx, stru_180023118; SRWLock
0x180011087  call    cs:__imp_ReleaseSRWLockExclusive
0x18001108d  mov     rbx, [rsp+38h+arg_0]
0x180011092  mov     rsi, [rsp+38h+arg_8]
0x180011097  add     rsp, 30h
0x18001109b  pop     rdi
0x18001109c  retn
```
