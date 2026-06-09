# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x140006cac`
- end: `0x140006d68`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `188`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140007140`
- `0x140007304`
- `0x1400074c0`
- `0x140007684`
- `0x140007ce4`

## callees

- `0x140006cac`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006cf4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006d4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006cf4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006d4a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140006cd6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140006cd6`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_1400193FC;
  if ( !dword_1400193FC )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_140019440 )
      {
        v1 = dword_1400193FC;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_140019440 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_140019440,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_140019440 )
      {
        v1 = 1;
        dword_1400193FC = 1;
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
0x140006cac  push    rbx
0x140006cae  sub     rsp, 20h
0x140006cb2  mov     ebx, cs:dword_1400193FC
0x140006cb8  nop
0x140006cb9  test    ebx, ebx
0x140006cbb  jnz     loc_140006D52
0x140006cc1  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140006cc7  test    eax, eax
0x140006cc9  jz      loc_140006D50
0x140006ccf  lea     rcx, SRWLock; SRWLock
0x140006cd6  call    cs:__imp_AcquireSRWLockExclusive
0x140006cdc  cmp     cs:qword_140019440, 0
0x140006ce4  jz      short loc_140006CFC
0x140006ce6  mov     ebx, cs:dword_1400193FC
0x140006cec  lea     rcx, SRWLock; SRWLock
0x140006cf3  nop
0x140006cf4  call    cs:__imp_ReleaseSRWLockExclusive
0x140006cfa  jmp     short loc_140006D52
0x140006cfc  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x140006d03  mov     cs:qword_140019440, 0
0x140006d0e  test    rax, rax
0x140006d11  jnz     short loc_140006D1F
0x140006d13  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x140006d1a  test    rax, rax
0x140006d1d  jz      short loc_140006D39
0x140006d1f  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140006d26  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x140006d2d  lea     rcx, qword_140019440
0x140006d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d39  cmp     cs:qword_140019440, 0
0x140006d41  lea     rcx, SRWLock; SRWLock
0x140006d48  jnz     short loc_140006D5A
0x140006d4a  call    cs:__imp_ReleaseSRWLockExclusive
0x140006d50  xor     ebx, ebx
0x140006d52  mov     eax, ebx
0x140006d54  add     rsp, 20h
0x140006d58  pop     rbx
0x140006d59  retn
0x140006d5a  mov     ebx, 1
0x140006d5f  nop
0x140006d60  mov     cs:dword_1400193FC, ebx
0x140006d66  jmp     short loc_140006CF4
```
