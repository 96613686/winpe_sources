# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180006b18`
- end: `0x180006bd5`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `46`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007240`
- `0x1800073bc`
- `0x180007538`
- `0x1800083e4`
- `0x180015330`
- `0x180015410`
- `0x1800155e4`
- `0x1800156c4`
- `0x1800157a4`
- `0x180015924`
- `0x180015aec`
- `0x180015cb4`
- `0x180015e7c`
- `0x180016044`
- `0x18001620c`
- `0x1800162f0`
- `0x1800164b8`
- `0x18001659c`
- `0x18001667c`
- `0x180016844`
- `0x180016928`
- `0x180016a0c`
- `0x180016aec`
- `0x180016bd0`
- `0x180016cb4`
- `0x180016d94`
- `0x180016e74`
- `0x180016f54`
- `0x1800170d4`
- `0x180017248`
- `0x1800173bc`
- `0x180017530`
- `0x1800176a4`
- `0x180017818`
- `0x18001798c`
- `0x180017b00`
- `0x180017c74`
- `0x180017d54`
- `0x180017e34`
- `0x180017f14`
- `0x1800180e8`
- `0x180018268`
- `0x1800183e8`
- `0x1800184c8`
- `0x180018648`
- `0x180029fd0`

## callees

- `0x180006b18`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006b42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006b42`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006b60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006bb6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006b60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006bb6`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_180041804;
  if ( !dword_180041804 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180041848 )
      {
        v1 = dword_180041804;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180041848 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180041848,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180041848 )
      {
        v1 = 1;
        dword_180041804 = 1;
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
0x180006b18  push    rbx
0x180006b1a  sub     rsp, 20h
0x180006b1e  mov     ebx, cs:dword_180041804
0x180006b24  nop
0x180006b25  test    ebx, ebx
0x180006b27  jnz     loc_180006BBE
0x180006b2d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180006b33  test    eax, eax
0x180006b35  jz      loc_180006BBC
0x180006b3b  lea     rcx, SRWLock; SRWLock
0x180006b42  call    cs:__imp_AcquireSRWLockExclusive
0x180006b48  cmp     cs:qword_180041848, 0
0x180006b50  jz      short loc_180006B68
0x180006b52  mov     ebx, cs:dword_180041804
0x180006b58  nop
0x180006b59  lea     rcx, SRWLock; SRWLock
0x180006b60  call    cs:__imp_ReleaseSRWLockExclusive
0x180006b66  jmp     short loc_180006BBE
0x180006b68  mov     cs:qword_180041848, 0
0x180006b73  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180006b7a  test    rax, rax
0x180006b7d  jnz     short loc_180006B8B
0x180006b7f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180006b86  test    rax, rax
0x180006b89  jz      short loc_180006BA5
0x180006b8b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180006b92  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180006b99  lea     rcx, qword_180041848
0x180006ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ba5  lea     rcx, SRWLock; SRWLock
0x180006bac  cmp     cs:qword_180041848, 0
0x180006bb4  jnz     short loc_180006BC6
0x180006bb6  call    cs:__imp_ReleaseSRWLockExclusive
0x180006bbc  xor     ebx, ebx
0x180006bbe  mov     eax, ebx
0x180006bc0  add     rsp, 20h
0x180006bc4  pop     rbx
0x180006bc5  retn
0x180006bc6  nop
0x180006bc7  mov     ebx, 1
0x180006bcc  mov     cs:dword_180041804, ebx
0x180006bd2  jmp     short loc_180006B60
```
