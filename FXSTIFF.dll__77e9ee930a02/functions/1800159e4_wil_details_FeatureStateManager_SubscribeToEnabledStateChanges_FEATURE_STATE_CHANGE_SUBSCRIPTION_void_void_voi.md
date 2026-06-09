# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1800159e4`
- end: `0x180015add`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `249`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800162e0`

## callees

- `0x1800159e4`
- `0x180015bf8`
- `0x180019010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180015ac3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180015ac3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180015a14`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180015a14`
- `KERNEL32!GetModuleHandleW` at `0x180015a53`
- `KERNEL32!GetModuleHandleW` at `0x180015a53`
- `KERNEL32!GetProcAddress` at `0x180015a70`
- `KERNEL32!GetProcAddress` at `0x180015a70`

## string_xrefs

- `0x180015a4c`: `ntdll.dll`
- `0x180015a66`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x1800159e4  push    rbx
0x1800159e6  push    rbp
0x1800159e7  push    rsi
0x1800159e8  push    rdi
0x1800159e9  push    r14
0x1800159eb  push    r15
0x1800159ed  sub     rsp, 38h
0x1800159f1  mov     rbp, r9
0x1800159f4  mov     r15, r8
0x1800159f7  mov     r14, rdx
0x1800159fa  mov     rbx, rcx
0x1800159fd  mov     qword ptr [rdx], 0
0x180015a04  cmp     byte ptr [rcx], 0
0x180015a07  jz      loc_180015ACF
0x180015a0d  lea     rdi, [rcx+20h]
0x180015a11  mov     rcx, rdi; SRWLock
0x180015a14  call    cs:__imp_AcquireSRWLockExclusive
0x180015a1b  nop     dword ptr [rax+rax+00h]
0x180015a20  lea     rsi, [rbx+90h]
0x180015a27  cmp     qword ptr [rsi], 0
0x180015a2b  jnz     short loc_180015AA9
0x180015a2d  mov     qword ptr [rsi], 0
0x180015a34  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180015a3b  test    rax, rax
0x180015a3e  jnz     short loc_180015A90
0x180015a40  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180015a47  test    rax, rax
0x180015a4a  jnz     short loc_180015A66
0x180015a4c  lea     rcx, ModuleName; "ntdll.dll"
0x180015a53  call    cs:__imp_GetModuleHandleW
0x180015a5a  nop     dword ptr [rax+rax+00h]
0x180015a5f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180015a66  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180015a6d  mov     rcx, rax; hModule
0x180015a70  call    cs:__imp_GetProcAddress
0x180015a77  nop     dword ptr [rax+rax+00h]
0x180015a7c  nop
0x180015a7d  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180015a84  test    rax, rax
0x180015a87  jnz     short loc_180015A90
0x180015a89  mov     eax, 0C0000139h
0x180015a8e  jmp     short loc_180015AA5
0x180015a90  mov     r9, rsi
0x180015a93  xor     r8d, r8d
0x180015a96  mov     rdx, rbx
0x180015a99  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180015aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015aa5  test    eax, eax
0x180015aa7  jnz     short loc_180015ABB
0x180015aa9  lea     rcx, [rbx+48h]; this
0x180015aad  mov     r9, rbp; void *
0x180015ab0  mov     r8, r15; void (*)(void *)
0x180015ab3  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180015ab6  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180015abb  test    rdi, rdi
0x180015abe  jz      short loc_180015ACF
0x180015ac0  mov     rcx, rdi; SRWLock
0x180015ac3  call    cs:__imp_ReleaseSRWLockExclusive
0x180015aca  nop     dword ptr [rax+rax+00h]
0x180015acf  add     rsp, 38h
0x180015ad3  pop     r15
0x180015ad5  pop     r14
0x180015ad7  pop     rdi
0x180015ad8  pop     rsi
0x180015ad9  pop     rbp
0x180015ada  pop     rbx
0x180015adb  retn
```
