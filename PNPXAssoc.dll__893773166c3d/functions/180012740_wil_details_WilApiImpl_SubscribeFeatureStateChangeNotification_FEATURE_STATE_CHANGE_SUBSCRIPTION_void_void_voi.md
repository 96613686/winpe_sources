# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180012740`
- end: `0x18001284d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1800122f8`
- `0x1800123f4`
- `0x180012740`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800127e1`
- `KERNEL32!GetProcAddress` at `0x1800127e1`
- `KERNEL32!GetModuleHandleW` at `0x1800127ca`
- `KERNEL32!GetModuleHandleW` at `0x1800127ca`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180012837`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180012837`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180012790`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180012790`

## string_xrefs

- `0x1800127c3`: `ntdll.dll`
- `0x1800127d7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_18001A2C8 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18001A2C8 = 0;
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
               &qword_18001A2C8);
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
0x180012740  mov     [rsp+arg_0], rbx
0x180012745  mov     [rsp+arg_8], rsi
0x18001274a  push    rdi
0x18001274b  sub     rsp, 30h
0x18001274f  mov     rdi, r8
0x180012752  mov     rsi, rdx
0x180012755  mov     rbx, rcx
0x180012758  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001275c  jnz     short loc_180012775
0x18001275e  mov     r8, rdx; void (*)(void *)
0x180012761  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180012764  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001276b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180012770  jmp     loc_18001283D
0x180012775  mov     qword ptr [rcx], 0
0x18001277c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180012783  jz      loc_18001283D
0x180012789  lea     rcx, SRWLock; SRWLock
0x180012790  call    cs:__imp_AcquireSRWLockExclusive
0x180012796  cmp     cs:qword_18001A2C8, 0
0x18001279e  jnz     short loc_18001281B
0x1800127a0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800127a7  mov     cs:qword_18001A2C8, 0
0x1800127b2  test    rax, rax
0x1800127b5  jnz     short loc_1800127FA
0x1800127b7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800127be  test    rax, rax
0x1800127c1  jnz     short loc_1800127D7
0x1800127c3  lea     rcx, ModuleName; "ntdll.dll"
0x1800127ca  call    cs:__imp_GetModuleHandleW
0x1800127d0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800127d7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800127de  mov     rcx, rax; hModule
0x1800127e1  call    cs:__imp_GetProcAddress
0x1800127e7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800127ee  test    rax, rax
0x1800127f1  jnz     short loc_1800127FA
0x1800127f3  mov     eax, 0C0000139h
0x1800127f8  jmp     short loc_180012817
0x1800127fa  lea     r9, qword_18001A2C8
0x180012801  xor     r8d, r8d
0x180012804  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001280b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180012812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012817  test    eax, eax
0x180012819  jnz     short loc_180012830
0x18001281b  mov     r9, rdi; void *
0x18001281e  lea     rcx, CriticalSection; this
0x180012825  mov     r8, rsi; void (*)(void *)
0x180012828  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18001282b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180012830  lea     rcx, SRWLock; SRWLock
0x180012837  call    cs:__imp_ReleaseSRWLockExclusive
0x18001283d  mov     rbx, [rsp+38h+arg_0]
0x180012842  mov     rsi, [rsp+38h+arg_8]
0x180012847  add     rsp, 30h
0x18001284b  pop     rdi
0x18001284c  retn
```
