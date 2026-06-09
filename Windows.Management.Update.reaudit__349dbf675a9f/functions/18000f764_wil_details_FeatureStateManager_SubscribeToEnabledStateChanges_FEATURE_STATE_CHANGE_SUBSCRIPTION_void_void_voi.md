# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000f764`
- end: `0x18000f86d`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `265`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180010110`

## callees

- `0x18000f764`
- `0x18000f998`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f7f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f7f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f7d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f7d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f847`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f847`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f79c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f79c`

## string_xrefs

- `0x18000f7d1`: `ntdll.dll`
- `0x18000f7eb`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(
        RTL_SRWLOCK *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  RTL_SRWLOCK *v8; // rdi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v11; // eax

  *a2 = 0;
  if ( LOBYTE(this->Ptr) )
  {
    v8 = this + 4;
    AcquireSRWLockExclusive(this + 4);
    if ( this[18].Ptr )
      goto LABEL_10;
    this[18].Ptr = 0;
    ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
    if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification )
      goto LABEL_8;
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlRegisterFeatureConfigurationChangeNotification");
    g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_8:
      v11 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), RTL_SRWLOCK *, _QWORD, RTL_SRWLOCK *))ProcAddress)(
              _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
              this,
              0,
              &this[18]);
    else
      v11 = -1073741511;
    if ( !v11 )
LABEL_10:
      wil::details_abi::SubscriptionList::SubscribeUnderLock((wil::details_abi::SubscriptionList *)&this[9], a2, a3, a4);
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
  }
}

```

## disassembly

```asm
0x18000f764  mov     [rsp+arg_0], rbx
0x18000f769  mov     [rsp+arg_8], rbp
0x18000f76e  mov     [rsp+arg_10], rsi
0x18000f773  push    rdi
0x18000f774  push    r14
0x18000f776  push    r15
0x18000f778  sub     rsp, 30h
0x18000f77c  and     qword ptr [rdx], 0
0x18000f780  mov     rbp, r9
0x18000f783  cmp     byte ptr [rcx], 0
0x18000f786  mov     r15, r8
0x18000f789  mov     r14, rdx
0x18000f78c  mov     rbx, rcx
0x18000f78f  jz      loc_18000F853
0x18000f795  lea     rdi, [rcx+20h]
0x18000f799  mov     rcx, rdi; SRWLock
0x18000f79c  call    cs:__imp_AcquireSRWLockExclusive
0x18000f7a3  nop     dword ptr [rax+rax+00h]
0x18000f7a8  lea     rsi, [rbx+90h]
0x18000f7af  cmp     qword ptr [rsi], 0
0x18000f7b3  jnz     short loc_18000F82D
0x18000f7b5  and     qword ptr [rsi], 0
0x18000f7b9  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000f7c0  test    rax, rax
0x18000f7c3  jnz     short loc_18000F814
0x18000f7c5  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f7cc  test    rax, rax
0x18000f7cf  jnz     short loc_18000F7EB
0x18000f7d1  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000f7d8  call    cs:__imp_GetModuleHandleW
0x18000f7df  nop     dword ptr [rax+rax+00h]
0x18000f7e4  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f7eb  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000f7f2  mov     rcx, rax; hModule
0x18000f7f5  call    cs:__imp_GetProcAddress
0x18000f7fc  nop     dword ptr [rax+rax+00h]
0x18000f801  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000f808  test    rax, rax
0x18000f80b  jnz     short loc_18000F814
0x18000f80d  mov     eax, 0C0000139h
0x18000f812  jmp     short loc_18000F829
0x18000f814  mov     r9, rsi
0x18000f817  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000f81e  xor     r8d, r8d
0x18000f821  mov     rdx, rbx
0x18000f824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f829  test    eax, eax
0x18000f82b  jnz     short loc_18000F83F
0x18000f82d  lea     rcx, [rbx+48h]; this
0x18000f831  mov     r9, rbp; void *
0x18000f834  mov     r8, r15; void (*)(void *)
0x18000f837  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000f83a  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000f83f  test    rdi, rdi
0x18000f842  jz      short loc_18000F853
0x18000f844  mov     rcx, rdi; SRWLock
0x18000f847  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f84e  nop     dword ptr [rax+rax+00h]
0x18000f853  mov     rbx, [rsp+48h+arg_0]
0x18000f858  mov     rbp, [rsp+48h+arg_8]
0x18000f85d  mov     rsi, [rsp+48h+arg_10]
0x18000f862  add     rsp, 30h
0x18000f866  pop     r15
0x18000f868  pop     r14
0x18000f86a  pop     rdi
0x18000f86b  retn
```
