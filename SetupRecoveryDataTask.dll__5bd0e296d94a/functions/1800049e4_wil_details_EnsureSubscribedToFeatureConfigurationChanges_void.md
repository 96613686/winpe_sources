# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1800049e4`
- end: `0x180004aa1`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005054`
- `0x180005148`
- `0x1800068e4`

## callees

- `0x1800049e4`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004a0e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004a0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004a2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004a82`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004a2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004a82`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_180015714;
  if ( !dword_180015714 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180015758 )
      {
        v1 = dword_180015714;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180015758 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180015758,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180015758 )
      {
        v1 = 1;
        dword_180015714 = 1;
        goto LABEL_5;
      }
      ReleaseSRWLockExclusive(&SRWLock);
    }
    return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x1800049e4  push    rbx
0x1800049e6  sub     rsp, 20h
0x1800049ea  mov     ebx, cs:dword_180015714
0x1800049f0  nop
0x1800049f1  test    ebx, ebx
0x1800049f3  jnz     loc_180004A8A
0x1800049f9  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800049ff  test    eax, eax
0x180004a01  jz      loc_180004A88
0x180004a07  lea     rcx, SRWLock; SRWLock
0x180004a0e  call    cs:__imp_AcquireSRWLockExclusive
0x180004a14  cmp     cs:qword_180015758, 0
0x180004a1c  jz      short loc_180004A34
0x180004a1e  mov     ebx, cs:dword_180015714
0x180004a24  nop
0x180004a25  lea     rcx, SRWLock; SRWLock
0x180004a2c  call    cs:__imp_ReleaseSRWLockExclusive
0x180004a32  jmp     short loc_180004A8A
0x180004a34  mov     cs:qword_180015758, 0
0x180004a3f  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180004a46  test    rax, rax
0x180004a49  jnz     short loc_180004A57
0x180004a4b  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180004a52  test    rax, rax
0x180004a55  jz      short loc_180004A71
0x180004a57  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004a5e  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180004a65  lea     rcx, qword_180015758
0x180004a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a71  lea     rcx, SRWLock; SRWLock
0x180004a78  cmp     cs:qword_180015758, 0
0x180004a80  jnz     short loc_180004A92
0x180004a82  call    cs:__imp_ReleaseSRWLockExclusive
0x180004a88  xor     ebx, ebx
0x180004a8a  mov     eax, ebx
0x180004a8c  add     rsp, 20h
0x180004a90  pop     rbx
0x180004a91  retn
0x180004a92  nop
0x180004a93  mov     ebx, 1
0x180004a98  mov     cs:dword_180015714, ebx
0x180004a9e  jmp     short loc_180004A2C
```
