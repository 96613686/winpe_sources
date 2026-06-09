# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180006d2c`
- end: `0x180006e24`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180007600`

## callees

- `0x180006d2c`
- `0x180006f40`
- `0x18000a010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180006db8`
- `KERNEL32!GetProcAddress` at `0x180006db8`
- `KERNEL32!GetModuleHandleW` at `0x180006d9b`
- `KERNEL32!GetModuleHandleW` at `0x180006d9b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180006d5c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180006d5c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180006e0a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180006e0a`

## string_xrefs

- `0x180006d94`: `ntdll.dll`
- `0x180006dae`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180006d2c  push    rbx
0x180006d2e  push    rbp
0x180006d2f  push    rsi
0x180006d30  push    rdi
0x180006d31  push    r14
0x180006d33  push    r15
0x180006d35  sub     rsp, 38h
0x180006d39  mov     qword ptr [rdx], 0
0x180006d40  mov     rbp, r9
0x180006d43  cmp     byte ptr [rcx], 0
0x180006d46  mov     r15, r8
0x180006d49  mov     r14, rdx
0x180006d4c  mov     rbx, rcx
0x180006d4f  jz      loc_180006E16
0x180006d55  lea     rdi, [rcx+20h]
0x180006d59  mov     rcx, rdi; SRWLock
0x180006d5c  call    cs:__imp_AcquireSRWLockExclusive
0x180006d63  nop     dword ptr [rax+rax+00h]
0x180006d68  lea     rsi, [rbx+90h]
0x180006d6f  cmp     qword ptr [rsi], 0
0x180006d73  jnz     short loc_180006DF0
0x180006d75  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180006d7c  mov     qword ptr [rsi], 0
0x180006d83  test    rax, rax
0x180006d86  jnz     short loc_180006DD7
0x180006d88  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006d8f  test    rax, rax
0x180006d92  jnz     short loc_180006DAE
0x180006d94  lea     rcx, ModuleName; "ntdll.dll"
0x180006d9b  call    cs:__imp_GetModuleHandleW
0x180006da2  nop     dword ptr [rax+rax+00h]
0x180006da7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006dae  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180006db5  mov     rcx, rax; hModule
0x180006db8  call    cs:__imp_GetProcAddress
0x180006dbf  nop     dword ptr [rax+rax+00h]
0x180006dc4  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180006dcb  test    rax, rax
0x180006dce  jnz     short loc_180006DD7
0x180006dd0  mov     eax, 0C0000139h
0x180006dd5  jmp     short loc_180006DEC
0x180006dd7  mov     r9, rsi
0x180006dda  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180006de1  xor     r8d, r8d
0x180006de4  mov     rdx, rbx
0x180006de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dec  test    eax, eax
0x180006dee  jnz     short loc_180006E02
0x180006df0  lea     rcx, [rbx+48h]; this
0x180006df4  mov     r9, rbp; void *
0x180006df7  mov     r8, r15; void (*)(void *)
0x180006dfa  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180006dfd  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180006e02  test    rdi, rdi
0x180006e05  jz      short loc_180006E16
0x180006e07  mov     rcx, rdi; SRWLock
0x180006e0a  call    cs:__imp_ReleaseSRWLockExclusive
0x180006e11  nop     dword ptr [rax+rax+00h]
0x180006e16  add     rsp, 38h
0x180006e1a  pop     r15
0x180006e1c  pop     r14
0x180006e1e  pop     rdi
0x180006e1f  pop     rsi
0x180006e20  pop     rbp
0x180006e21  pop     rbx
0x180006e22  retn
```
