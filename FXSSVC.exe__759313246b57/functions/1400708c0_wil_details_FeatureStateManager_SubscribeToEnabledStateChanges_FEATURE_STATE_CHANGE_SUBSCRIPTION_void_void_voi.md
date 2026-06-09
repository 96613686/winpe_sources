# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1400708c0`
- end: `0x1400709b8`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400711c0`

## callees

- `0x1400708c0`
- `0x140070ad4`
- `0x14008b010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1400708f0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400708f0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14007099e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14007099e`
- `KERNEL32!GetProcAddress` at `0x14007094c`
- `KERNEL32!GetProcAddress` at `0x14007094c`
- `KERNEL32!GetModuleHandleW` at `0x14007092f`
- `KERNEL32!GetModuleHandleW` at `0x14007092f`

## string_xrefs

- `0x140070928`: `ntdll.dll`
- `0x140070942`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x1400708c0  push    rbx
0x1400708c2  push    rbp
0x1400708c3  push    rsi
0x1400708c4  push    rdi
0x1400708c5  push    r14
0x1400708c7  push    r15
0x1400708c9  sub     rsp, 38h
0x1400708cd  mov     qword ptr [rdx], 0
0x1400708d4  mov     rbp, r9
0x1400708d7  cmp     byte ptr [rcx], 0
0x1400708da  mov     r15, r8
0x1400708dd  mov     r14, rdx
0x1400708e0  mov     rbx, rcx
0x1400708e3  jz      loc_1400709AA
0x1400708e9  lea     rdi, [rcx+20h]
0x1400708ed  mov     rcx, rdi; SRWLock
0x1400708f0  call    cs:__imp_AcquireSRWLockExclusive
0x1400708f7  nop     dword ptr [rax+rax+00h]
0x1400708fc  lea     rsi, [rbx+90h]
0x140070903  cmp     qword ptr [rsi], 0
0x140070907  jnz     short loc_140070984
0x140070909  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140070910  mov     qword ptr [rsi], 0
0x140070917  test    rax, rax
0x14007091a  jnz     short loc_14007096B
0x14007091c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140070923  test    rax, rax
0x140070926  jnz     short loc_140070942
0x140070928  lea     rcx, ModuleName; "ntdll.dll"
0x14007092f  call    cs:__imp_GetModuleHandleW
0x140070936  nop     dword ptr [rax+rax+00h]
0x14007093b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140070942  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x140070949  mov     rcx, rax; hModule
0x14007094c  call    cs:__imp_GetProcAddress
0x140070953  nop     dword ptr [rax+rax+00h]
0x140070958  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14007095f  test    rax, rax
0x140070962  jnz     short loc_14007096B
0x140070964  mov     eax, 0C0000139h
0x140070969  jmp     short loc_140070980
0x14007096b  mov     r9, rsi
0x14007096e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x140070975  xor     r8d, r8d
0x140070978  mov     rdx, rbx
0x14007097b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140070980  test    eax, eax
0x140070982  jnz     short loc_140070996
0x140070984  lea     rcx, [rbx+48h]; this
0x140070988  mov     r9, rbp; void *
0x14007098b  mov     r8, r15; void (*)(void *)
0x14007098e  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140070991  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x140070996  test    rdi, rdi
0x140070999  jz      short loc_1400709AA
0x14007099b  mov     rcx, rdi; SRWLock
0x14007099e  call    cs:__imp_ReleaseSRWLockExclusive
0x1400709a5  nop     dword ptr [rax+rax+00h]
0x1400709aa  add     rsp, 38h
0x1400709ae  pop     r15
0x1400709b0  pop     r14
0x1400709b2  pop     rdi
0x1400709b3  pop     rsi
0x1400709b4  pop     rbp
0x1400709b5  pop     rbx
0x1400709b6  retn
```
