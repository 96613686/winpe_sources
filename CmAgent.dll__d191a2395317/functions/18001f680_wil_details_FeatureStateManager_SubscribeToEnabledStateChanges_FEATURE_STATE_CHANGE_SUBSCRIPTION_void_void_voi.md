# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18001f680`
- end: `0x18001f778`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800206d0`

## callees

- `0x18001f680`
- `0x18001f894`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f6ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f6ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f70c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f70c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f75e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f75e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f6b0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f6b0`

## string_xrefs

- `0x18001f6e8`: `ntdll.dll`
- `0x18001f702`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18001f680  push    rbx
0x18001f682  push    rbp
0x18001f683  push    rsi
0x18001f684  push    rdi
0x18001f685  push    r14
0x18001f687  push    r15
0x18001f689  sub     rsp, 38h
0x18001f68d  mov     qword ptr [rdx], 0
0x18001f694  mov     rbp, r9
0x18001f697  cmp     byte ptr [rcx], 0
0x18001f69a  mov     r15, r8
0x18001f69d  mov     r14, rdx
0x18001f6a0  mov     rbx, rcx
0x18001f6a3  jz      loc_18001F76A
0x18001f6a9  lea     rdi, [rcx+20h]
0x18001f6ad  mov     rcx, rdi; SRWLock
0x18001f6b0  call    cs:__imp_AcquireSRWLockExclusive
0x18001f6b7  nop     dword ptr [rax+rax+00h]
0x18001f6bc  lea     rsi, [rbx+90h]
0x18001f6c3  cmp     qword ptr [rsi], 0
0x18001f6c7  jnz     short loc_18001F744
0x18001f6c9  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001f6d0  mov     qword ptr [rsi], 0
0x18001f6d7  test    rax, rax
0x18001f6da  jnz     short loc_18001F72B
0x18001f6dc  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001f6e3  test    rax, rax
0x18001f6e6  jnz     short loc_18001F702
0x18001f6e8  lea     rcx, ModuleName; "ntdll.dll"
0x18001f6ef  call    cs:__imp_GetModuleHandleW
0x18001f6f6  nop     dword ptr [rax+rax+00h]
0x18001f6fb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001f702  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001f709  mov     rcx, rax; hModule
0x18001f70c  call    cs:__imp_GetProcAddress
0x18001f713  nop     dword ptr [rax+rax+00h]
0x18001f718  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001f71f  test    rax, rax
0x18001f722  jnz     short loc_18001F72B
0x18001f724  mov     eax, 0C0000139h
0x18001f729  jmp     short loc_18001F740
0x18001f72b  mov     r9, rsi
0x18001f72e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18001f735  xor     r8d, r8d
0x18001f738  mov     rdx, rbx
0x18001f73b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f740  test    eax, eax
0x18001f742  jnz     short loc_18001F756
0x18001f744  lea     rcx, [rbx+48h]; this
0x18001f748  mov     r9, rbp; void *
0x18001f74b  mov     r8, r15; void (*)(void *)
0x18001f74e  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18001f751  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18001f756  test    rdi, rdi
0x18001f759  jz      short loc_18001F76A
0x18001f75b  mov     rcx, rdi; SRWLock
0x18001f75e  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f765  nop     dword ptr [rax+rax+00h]
0x18001f76a  add     rsp, 38h
0x18001f76e  pop     r15
0x18001f770  pop     r14
0x18001f772  pop     rdi
0x18001f773  pop     rsi
0x18001f774  pop     rbp
0x18001f775  pop     rbx
0x18001f776  retn
```
