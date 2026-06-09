# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180028124`
- end: `0x18002821c`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void __fastcall(RTL_SRWLOCK *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180028a10`

## callees

- `0x180028124`
- `0x180028338`
- `0x18005f010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180028193`
- `KERNEL32!GetModuleHandleW` at `0x180028193`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180028154`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180028154`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180028202`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180028202`
- `KERNEL32!GetProcAddress` at `0x1800281b0`
- `KERNEL32!GetProcAddress` at `0x1800281b0`

## string_xrefs

- `0x18002818c`: `ntdll.dll`
- `0x1800281a6`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      v11 = ((__int64 (__fastcall *)(void (__fastcall *)(char *), RTL_SRWLOCK *, _QWORD, RTL_SRWLOCK *))ProcAddress)(
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
0x180028124  push    rbx
0x180028126  push    rbp
0x180028127  push    rsi
0x180028128  push    rdi
0x180028129  push    r14
0x18002812b  push    r15
0x18002812d  sub     rsp, 38h
0x180028131  mov     qword ptr [rdx], 0
0x180028138  mov     rbp, r9
0x18002813b  cmp     byte ptr [rcx], 0
0x18002813e  mov     r15, r8
0x180028141  mov     r14, rdx
0x180028144  mov     rbx, rcx
0x180028147  jz      loc_18002820E
0x18002814d  lea     rdi, [rcx+20h]
0x180028151  mov     rcx, rdi; SRWLock
0x180028154  call    cs:__imp_AcquireSRWLockExclusive
0x18002815b  nop     dword ptr [rax+rax+00h]
0x180028160  lea     rsi, [rbx+90h]
0x180028167  cmp     qword ptr [rsi], 0
0x18002816b  jnz     short loc_1800281E8
0x18002816d  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180028174  mov     qword ptr [rsi], 0
0x18002817b  test    rax, rax
0x18002817e  jnz     short loc_1800281CF
0x180028180  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180028187  test    rax, rax
0x18002818a  jnz     short loc_1800281A6
0x18002818c  lea     rcx, aNtdllDll; "ntdll.dll"
0x180028193  call    cs:__imp_GetModuleHandleW
0x18002819a  nop     dword ptr [rax+rax+00h]
0x18002819f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800281a6  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800281ad  mov     rcx, rax; hModule
0x1800281b0  call    cs:__imp_GetProcAddress
0x1800281b7  nop     dword ptr [rax+rax+00h]
0x1800281bc  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800281c3  test    rax, rax
0x1800281c6  jnz     short loc_1800281CF
0x1800281c8  mov     eax, 0C0000139h
0x1800281cd  jmp     short loc_1800281E4
0x1800281cf  mov     r9, rsi
0x1800281d2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800281d9  xor     r8d, r8d
0x1800281dc  mov     rdx, rbx
0x1800281df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281e4  test    eax, eax
0x1800281e6  jnz     short loc_1800281FA
0x1800281e8  lea     rcx, [rbx+48h]; this
0x1800281ec  mov     r9, rbp; void *
0x1800281ef  mov     r8, r15; void (*)(void *)
0x1800281f2  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800281f5  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800281fa  test    rdi, rdi
0x1800281fd  jz      short loc_18002820E
0x1800281ff  mov     rcx, rdi; SRWLock
0x180028202  call    cs:__imp_ReleaseSRWLockExclusive
0x180028209  nop     dword ptr [rax+rax+00h]
0x18002820e  add     rsp, 38h
0x180028212  pop     r15
0x180028214  pop     r14
0x180028216  pop     rdi
0x180028217  pop     rsi
0x180028218  pop     rbp
0x180028219  pop     rbx
0x18002821a  retn
```
