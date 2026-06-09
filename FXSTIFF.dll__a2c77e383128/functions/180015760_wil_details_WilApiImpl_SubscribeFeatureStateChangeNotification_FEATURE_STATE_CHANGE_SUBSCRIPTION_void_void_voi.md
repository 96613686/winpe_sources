# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180015760`
- end: `0x18001586e`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `270`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180015074`
- `0x180015170`
- `0x180015760`
- `0x180019010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180015858`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180015858`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800157b0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800157b0`
- `KERNEL32!GetModuleHandleW` at `0x1800157ea`
- `KERNEL32!GetModuleHandleW` at `0x1800157ea`
- `KERNEL32!GetProcAddress` at `0x180015801`
- `KERNEL32!GetProcAddress` at `0x180015801`

## string_xrefs

- `0x1800157e3`: `ntdll.dll`
- `0x1800157f7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180070030);
      if ( qword_1800700A0 )
        goto LABEL_12;
      qword_1800700A0 = 0;
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
        v9 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), char *, _QWORD, __int64 *))ProcAddress)(
               _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
               &wil::details::g_featureStateManager,
               0,
               &qword_1800700A0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180070030);
    }
  }
}

```

## disassembly

```asm
0x180015760  mov     [rsp+arg_0], rbx
0x180015765  mov     [rsp+arg_8], rsi
0x18001576a  push    rdi
0x18001576b  sub     rsp, 30h
0x18001576f  mov     rdi, r8
0x180015772  mov     rsi, rdx
0x180015775  mov     rbx, rcx
0x180015778  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001577c  jnz     short loc_180015795
0x18001577e  mov     r8, rdx; void (*)(void *)
0x180015781  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180015784  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001578b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180015790  jmp     loc_18001585E
0x180015795  mov     qword ptr [rcx], 0
0x18001579c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800157a3  jz      loc_18001585E
0x1800157a9  lea     rcx, stru_180070030; SRWLock
0x1800157b0  call    cs:__imp_AcquireSRWLockExclusive
0x1800157b6  cmp     cs:qword_1800700A0, 0
0x1800157be  jnz     short loc_18001583C
0x1800157c0  mov     cs:qword_1800700A0, 0
0x1800157cb  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800157d2  test    rax, rax
0x1800157d5  jnz     short loc_18001581B
0x1800157d7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800157de  test    rax, rax
0x1800157e1  jnz     short loc_1800157F7
0x1800157e3  lea     rcx, ModuleName; "ntdll.dll"
0x1800157ea  call    cs:__imp_GetModuleHandleW
0x1800157f0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800157f7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800157fe  mov     rcx, rax; hModule
0x180015801  call    cs:__imp_GetProcAddress
0x180015807  nop
0x180015808  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001580f  test    rax, rax
0x180015812  jnz     short loc_18001581B
0x180015814  mov     eax, 0C0000139h
0x180015819  jmp     short loc_180015838
0x18001581b  lea     r9, qword_1800700A0
0x180015822  xor     r8d, r8d
0x180015825  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001582c  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180015833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015838  test    eax, eax
0x18001583a  jnz     short loc_180015851
0x18001583c  mov     r9, rdi; void *
0x18001583f  mov     r8, rsi; void (*)(void *)
0x180015842  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180015845  lea     rcx, CriticalSection; this
0x18001584c  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180015851  lea     rcx, stru_180070030; SRWLock
0x180015858  call    cs:__imp_ReleaseSRWLockExclusive
0x18001585e  mov     rbx, [rsp+38h+arg_0]
0x180015863  mov     rsi, [rsp+38h+arg_8]
0x180015868  add     rsp, 30h
0x18001586c  pop     rdi
0x18001586d  retn
```
