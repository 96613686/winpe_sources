# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1400049e0`
- end: `0x140004a9d`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140004f24`
- `0x1400050f8`
- `0x14000526c`
- `0x1400053e0`
- `0x140005554`
- `0x140005634`
- `0x140005714`
- `0x1400057f4`
- `0x1400075d0`

## callees

- `0x1400049e0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004a0a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004a0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004a28`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004a7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004a28`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004a7e`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_14001937C;
  if ( !dword_14001937C )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1400193C0 )
      {
        v1 = dword_14001937C;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_1400193C0 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_1400193C0,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_1400193C0 )
      {
        v1 = 1;
        dword_14001937C = 1;
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
0x1400049e0  push    rbx
0x1400049e2  sub     rsp, 20h
0x1400049e6  mov     ebx, cs:dword_14001937C
0x1400049ec  nop
0x1400049ed  test    ebx, ebx
0x1400049ef  jnz     loc_140004A86
0x1400049f5  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1400049fb  test    eax, eax
0x1400049fd  jz      loc_140004A84
0x140004a03  lea     rcx, SRWLock; SRWLock
0x140004a0a  call    cs:__imp_AcquireSRWLockExclusive
0x140004a10  cmp     cs:qword_1400193C0, 0
0x140004a18  jz      short loc_140004A30
0x140004a1a  mov     ebx, cs:dword_14001937C
0x140004a20  nop
0x140004a21  lea     rcx, SRWLock; SRWLock
0x140004a28  call    cs:__imp_ReleaseSRWLockExclusive
0x140004a2e  jmp     short loc_140004A86
0x140004a30  mov     cs:qword_1400193C0, 0
0x140004a3b  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x140004a42  test    rax, rax
0x140004a45  jnz     short loc_140004A53
0x140004a47  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x140004a4e  test    rax, rax
0x140004a51  jz      short loc_140004A6D
0x140004a53  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140004a5a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x140004a61  lea     rcx, qword_1400193C0
0x140004a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004a6d  lea     rcx, SRWLock; SRWLock
0x140004a74  cmp     cs:qword_1400193C0, 0
0x140004a7c  jnz     short loc_140004A8E
0x140004a7e  call    cs:__imp_ReleaseSRWLockExclusive
0x140004a84  xor     ebx, ebx
0x140004a86  mov     eax, ebx
0x140004a88  add     rsp, 20h
0x140004a8c  pop     rbx
0x140004a8d  retn
0x140004a8e  nop
0x140004a8f  mov     ebx, 1
0x140004a94  mov     cs:dword_14001937C, ebx
0x140004a9a  jmp     short loc_140004A28
```
