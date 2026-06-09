# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180005b50`
- end: `0x180005c0d`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006c68`
- `0x180015924`
- `0x1800255e0`
- `0x1800256c0`
- `0x1800257a0`

## callees

- `0x180005b50`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005b7a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005b7a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005b98`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005bee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005b98`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005bee`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_180059AC4;
  if ( !dword_180059AC4 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180059B08 )
      {
        v1 = dword_180059AC4;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180059B08 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180059B08,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180059B08 )
      {
        v1 = 1;
        dword_180059AC4 = 1;
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
0x180005b50  push    rbx
0x180005b52  sub     rsp, 20h
0x180005b56  mov     ebx, cs:dword_180059AC4
0x180005b5c  nop
0x180005b5d  test    ebx, ebx
0x180005b5f  jnz     loc_180005BF6
0x180005b65  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005b6b  test    eax, eax
0x180005b6d  jz      loc_180005BF4
0x180005b73  lea     rcx, SRWLock; SRWLock
0x180005b7a  call    cs:__imp_AcquireSRWLockExclusive
0x180005b80  cmp     cs:qword_180059B08, 0
0x180005b88  jz      short loc_180005BA0
0x180005b8a  mov     ebx, cs:dword_180059AC4
0x180005b90  nop
0x180005b91  lea     rcx, SRWLock; SRWLock
0x180005b98  call    cs:__imp_ReleaseSRWLockExclusive
0x180005b9e  jmp     short loc_180005BF6
0x180005ba0  mov     cs:qword_180059B08, 0
0x180005bab  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180005bb2  test    rax, rax
0x180005bb5  jnz     short loc_180005BC3
0x180005bb7  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180005bbe  test    rax, rax
0x180005bc1  jz      short loc_180005BDD
0x180005bc3  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005bca  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180005bd1  lea     rcx, qword_180059B08
0x180005bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bdd  lea     rcx, SRWLock; SRWLock
0x180005be4  cmp     cs:qword_180059B08, 0
0x180005bec  jnz     short loc_180005BFE
0x180005bee  call    cs:__imp_ReleaseSRWLockExclusive
0x180005bf4  xor     ebx, ebx
0x180005bf6  mov     eax, ebx
0x180005bf8  add     rsp, 20h
0x180005bfc  pop     rbx
0x180005bfd  retn
0x180005bfe  nop
0x180005bff  mov     ebx, 1
0x180005c04  mov     cs:dword_180059AC4, ebx
0x180005c0a  jmp     short loc_180005B98
```
