# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x140015fe0`
- end: `0x1400160ed`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x140015b90`
- `0x140015c8c`
- `0x140015fe0`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001606a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001606a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140016081`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140016081`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140016030`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140016030`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400160d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400160d7`

## string_xrefs

- `0x140016063`: `ntdll.dll`
- `0x140016077`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_140025110 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_140025110 = 0;
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
        v9 = ((__int64 (__fastcall *)(void (__fastcall *)(__int64), char *, _QWORD, __int64 *))ProcAddress)(
               `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
               &wil::details::g_featureStateManager,
               0,
               &qword_140025110);
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
0x140015fe0  mov     [rsp+arg_0], rbx
0x140015fe5  mov     [rsp+arg_8], rsi
0x140015fea  push    rdi
0x140015feb  sub     rsp, 30h
0x140015fef  mov     rdi, r8
0x140015ff2  mov     rsi, rdx
0x140015ff5  mov     rbx, rcx
0x140015ff8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140015ffc  jnz     short loc_140016015
0x140015ffe  mov     r8, rdx; void (*)(void *)
0x140016001  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140016004  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14001600b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x140016010  jmp     loc_1400160DD
0x140016015  mov     qword ptr [rcx], 0
0x14001601c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140016023  jz      loc_1400160DD
0x140016029  lea     rcx, SRWLock; SRWLock
0x140016030  call    cs:__imp_AcquireSRWLockExclusive
0x140016036  cmp     cs:qword_140025110, 0
0x14001603e  jnz     short loc_1400160BB
0x140016040  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140016047  mov     cs:qword_140025110, 0
0x140016052  test    rax, rax
0x140016055  jnz     short loc_14001609A
0x140016057  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001605e  test    rax, rax
0x140016061  jnz     short loc_140016077
0x140016063  lea     rcx, ModuleName; "ntdll.dll"
0x14001606a  call    cs:__imp_GetModuleHandleW
0x140016070  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140016077  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14001607e  mov     rcx, rax; hModule
0x140016081  call    cs:__imp_GetProcAddress
0x140016087  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14001608e  test    rax, rax
0x140016091  jnz     short loc_14001609A
0x140016093  mov     eax, 0C0000139h
0x140016098  jmp     short loc_1400160B7
0x14001609a  lea     r9, qword_140025110
0x1400160a1  xor     r8d, r8d
0x1400160a4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1400160ab  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToStateChangesUnderLock@FeatureStateManager@details@wil@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@5@PEAX@Z@SA@1@Z; `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,void *)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x1400160b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400160b7  test    eax, eax
0x1400160b9  jnz     short loc_1400160D0
0x1400160bb  mov     r9, rdi; void *
0x1400160be  lea     rcx, CriticalSection; this
0x1400160c5  mov     r8, rsi; void (*)(void *)
0x1400160c8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1400160cb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1400160d0  lea     rcx, SRWLock; SRWLock
0x1400160d7  call    cs:__imp_ReleaseSRWLockExclusive
0x1400160dd  mov     rbx, [rsp+38h+arg_0]
0x1400160e2  mov     rsi, [rsp+38h+arg_8]
0x1400160e7  add     rsp, 30h
0x1400160eb  pop     rdi
0x1400160ec  retn
```
