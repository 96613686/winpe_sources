# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18001138c`
- end: `0x180011484`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void __fastcall(RTL_SRWLOCK *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180011d80`

## callees

- `0x18001138c`
- `0x1800115a0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800113fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800113fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011418`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011418`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001146a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001146a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800113bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800113bc`

## string_xrefs

- `0x1800113f4`: `ntdll.dll`
- `0x18001140e`: `RtlRegisterFeatureConfigurationChangeNotification`

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
    ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
    this[18].Ptr = 0;
    if ( ProcAddress )
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
0x18001138c  push    rbx
0x18001138e  push    rbp
0x18001138f  push    rsi
0x180011390  push    rdi
0x180011391  push    r14
0x180011393  push    r15
0x180011395  sub     rsp, 38h
0x180011399  mov     qword ptr [rdx], 0
0x1800113a0  mov     rbp, r9
0x1800113a3  cmp     byte ptr [rcx], 0
0x1800113a6  mov     r15, r8
0x1800113a9  mov     r14, rdx
0x1800113ac  mov     rbx, rcx
0x1800113af  jz      loc_180011476
0x1800113b5  lea     rdi, [rcx+20h]
0x1800113b9  mov     rcx, rdi; SRWLock
0x1800113bc  call    cs:__imp_AcquireSRWLockExclusive
0x1800113c3  nop     dword ptr [rax+rax+00h]
0x1800113c8  lea     rsi, [rbx+90h]
0x1800113cf  cmp     qword ptr [rsi], 0
0x1800113d3  jnz     short loc_180011450
0x1800113d5  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800113dc  mov     qword ptr [rsi], 0
0x1800113e3  test    rax, rax
0x1800113e6  jnz     short loc_180011437
0x1800113e8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800113ef  test    rax, rax
0x1800113f2  jnz     short loc_18001140E
0x1800113f4  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800113fb  call    cs:__imp_GetModuleHandleW
0x180011402  nop     dword ptr [rax+rax+00h]
0x180011407  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001140e  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180011415  mov     rcx, rax; hModule
0x180011418  call    cs:__imp_GetProcAddress
0x18001141f  nop     dword ptr [rax+rax+00h]
0x180011424  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001142b  test    rax, rax
0x18001142e  jnz     short loc_180011437
0x180011430  mov     eax, 0C0000139h
0x180011435  jmp     short loc_18001144C
0x180011437  mov     r9, rsi
0x18001143a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180011441  xor     r8d, r8d
0x180011444  mov     rdx, rbx
0x180011447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001144c  test    eax, eax
0x18001144e  jnz     short loc_180011462
0x180011450  lea     rcx, [rbx+48h]; this
0x180011454  mov     r9, rbp; void *
0x180011457  mov     r8, r15; void (*)(void *)
0x18001145a  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18001145d  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180011462  test    rdi, rdi
0x180011465  jz      short loc_180011476
0x180011467  mov     rcx, rdi; SRWLock
0x18001146a  call    cs:__imp_ReleaseSRWLockExclusive
0x180011471  nop     dword ptr [rax+rax+00h]
0x180011476  add     rsp, 38h
0x18001147a  pop     r15
0x18001147c  pop     r14
0x18001147e  pop     rdi
0x18001147f  pop     rsi
0x180011480  pop     rbp
0x180011481  pop     rbx
0x180011482  retn
```
