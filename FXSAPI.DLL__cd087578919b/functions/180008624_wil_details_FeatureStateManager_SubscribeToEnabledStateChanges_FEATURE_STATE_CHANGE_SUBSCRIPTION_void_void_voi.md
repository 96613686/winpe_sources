# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180008624`
- end: `0x18000871c`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800091a0`

## callees

- `0x180008624`
- `0x180008838`
- `0x18003e010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180008702`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180008702`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180008654`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180008654`
- `KERNEL32!GetProcAddress` at `0x1800086b0`
- `KERNEL32!GetProcAddress` at `0x1800086b0`
- `KERNEL32!GetModuleHandleW` at `0x180008693`
- `KERNEL32!GetModuleHandleW` at `0x180008693`

## string_xrefs

- `0x18000868c`: `ntdll.dll`
- `0x1800086a6`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180008624  push    rbx
0x180008626  push    rbp
0x180008627  push    rsi
0x180008628  push    rdi
0x180008629  push    r14
0x18000862b  push    r15
0x18000862d  sub     rsp, 38h
0x180008631  mov     qword ptr [rdx], 0
0x180008638  mov     rbp, r9
0x18000863b  cmp     byte ptr [rcx], 0
0x18000863e  mov     r15, r8
0x180008641  mov     r14, rdx
0x180008644  mov     rbx, rcx
0x180008647  jz      loc_18000870E
0x18000864d  lea     rdi, [rcx+20h]
0x180008651  mov     rcx, rdi; SRWLock
0x180008654  call    cs:__imp_AcquireSRWLockExclusive
0x18000865b  nop     dword ptr [rax+rax+00h]
0x180008660  lea     rsi, [rbx+90h]
0x180008667  cmp     qword ptr [rsi], 0
0x18000866b  jnz     short loc_1800086E8
0x18000866d  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180008674  mov     qword ptr [rsi], 0
0x18000867b  test    rax, rax
0x18000867e  jnz     short loc_1800086CF
0x180008680  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008687  test    rax, rax
0x18000868a  jnz     short loc_1800086A6
0x18000868c  lea     rcx, ModuleName; "ntdll.dll"
0x180008693  call    cs:__imp_GetModuleHandleW
0x18000869a  nop     dword ptr [rax+rax+00h]
0x18000869f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800086a6  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800086ad  mov     rcx, rax; hModule
0x1800086b0  call    cs:__imp_GetProcAddress
0x1800086b7  nop     dword ptr [rax+rax+00h]
0x1800086bc  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800086c3  test    rax, rax
0x1800086c6  jnz     short loc_1800086CF
0x1800086c8  mov     eax, 0C0000139h
0x1800086cd  jmp     short loc_1800086E4
0x1800086cf  mov     r9, rsi
0x1800086d2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800086d9  xor     r8d, r8d
0x1800086dc  mov     rdx, rbx
0x1800086df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086e4  test    eax, eax
0x1800086e6  jnz     short loc_1800086FA
0x1800086e8  lea     rcx, [rbx+48h]; this
0x1800086ec  mov     r9, rbp; void *
0x1800086ef  mov     r8, r15; void (*)(void *)
0x1800086f2  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800086f5  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800086fa  test    rdi, rdi
0x1800086fd  jz      short loc_18000870E
0x1800086ff  mov     rcx, rdi; SRWLock
0x180008702  call    cs:__imp_ReleaseSRWLockExclusive
0x180008709  nop     dword ptr [rax+rax+00h]
0x18000870e  add     rsp, 38h
0x180008712  pop     r15
0x180008714  pop     r14
0x180008716  pop     rdi
0x180008717  pop     rsi
0x180008718  pop     rbp
0x180008719  pop     rbx
0x18000871a  retn
```
