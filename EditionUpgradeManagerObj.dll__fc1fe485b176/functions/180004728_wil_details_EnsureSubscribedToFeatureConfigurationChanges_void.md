# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180004728`
- end: `0x1800047e4`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `188`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005834`
- `0x1800090fc`
- `0x180013a10`

## callees

- `0x180004728`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004770`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800047c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004770`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800047c6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004752`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004752`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_18002F71C;
  if ( !dword_18002F71C )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_18002F760 )
      {
        v1 = dword_18002F71C;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_18002F760 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_18002F760,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_18002F760 )
      {
        v1 = 1;
        dword_18002F71C = 1;
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
0x180004728  push    rbx
0x18000472a  sub     rsp, 20h
0x18000472e  mov     ebx, cs:dword_18002F71C
0x180004734  nop
0x180004735  test    ebx, ebx
0x180004737  jnz     loc_1800047CE
0x18000473d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004743  test    eax, eax
0x180004745  jz      loc_1800047CC
0x18000474b  lea     rcx, SRWLock; SRWLock
0x180004752  call    cs:__imp_AcquireSRWLockExclusive
0x180004758  cmp     cs:qword_18002F760, 0
0x180004760  jz      short loc_180004778
0x180004762  mov     ebx, cs:dword_18002F71C
0x180004768  lea     rcx, SRWLock; SRWLock
0x18000476f  nop
0x180004770  call    cs:__imp_ReleaseSRWLockExclusive
0x180004776  jmp     short loc_1800047CE
0x180004778  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000477f  mov     cs:qword_18002F760, 0
0x18000478a  test    rax, rax
0x18000478d  jnz     short loc_18000479B
0x18000478f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180004796  test    rax, rax
0x180004799  jz      short loc_1800047B5
0x18000479b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800047a2  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x1800047a9  lea     rcx, qword_18002F760
0x1800047b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047b5  cmp     cs:qword_18002F760, 0
0x1800047bd  lea     rcx, SRWLock; SRWLock
0x1800047c4  jnz     short loc_1800047D6
0x1800047c6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800047cc  xor     ebx, ebx
0x1800047ce  mov     eax, ebx
0x1800047d0  add     rsp, 20h
0x1800047d4  pop     rbx
0x1800047d5  retn
0x1800047d6  mov     ebx, 1
0x1800047db  nop
0x1800047dc  mov     cs:dword_18002F71C, ebx
0x1800047e2  jmp     short loc_180004770
```
