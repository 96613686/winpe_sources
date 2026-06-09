# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180004f64`
- end: `0x180005021`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800055d4`
- `0x1800056c8`
- `0x1800057bc`
- `0x1800058b0`
- `0x1800069d0`

## callees

- `0x180004f64`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004fac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005002`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004fac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005002`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004f8e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004f8e`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_18001B714;
  if ( !dword_18001B714 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_18001B758 )
      {
        v1 = dword_18001B714;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_18001B758 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_18001B758,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_18001B758 )
      {
        v1 = 1;
        dword_18001B714 = 1;
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
0x180004f64  push    rbx
0x180004f66  sub     rsp, 20h
0x180004f6a  mov     ebx, cs:dword_18001B714
0x180004f70  nop
0x180004f71  test    ebx, ebx
0x180004f73  jnz     loc_18000500A
0x180004f79  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004f7f  test    eax, eax
0x180004f81  jz      loc_180005008
0x180004f87  lea     rcx, SRWLock; SRWLock
0x180004f8e  call    cs:__imp_AcquireSRWLockExclusive
0x180004f94  cmp     cs:qword_18001B758, 0
0x180004f9c  jz      short loc_180004FB4
0x180004f9e  mov     ebx, cs:dword_18001B714
0x180004fa4  nop
0x180004fa5  lea     rcx, SRWLock; SRWLock
0x180004fac  call    cs:__imp_ReleaseSRWLockExclusive
0x180004fb2  jmp     short loc_18000500A
0x180004fb4  mov     cs:qword_18001B758, 0
0x180004fbf  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180004fc6  test    rax, rax
0x180004fc9  jnz     short loc_180004FD7
0x180004fcb  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180004fd2  test    rax, rax
0x180004fd5  jz      short loc_180004FF1
0x180004fd7  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004fde  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180004fe5  lea     rcx, qword_18001B758
0x180004fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ff1  lea     rcx, SRWLock; SRWLock
0x180004ff8  cmp     cs:qword_18001B758, 0
0x180005000  jnz     short loc_180005012
0x180005002  call    cs:__imp_ReleaseSRWLockExclusive
0x180005008  xor     ebx, ebx
0x18000500a  mov     eax, ebx
0x18000500c  add     rsp, 20h
0x180005010  pop     rbx
0x180005011  retn
0x180005012  nop
0x180005013  mov     ebx, 1
0x180005018  mov     cs:dword_18001B714, ebx
0x18000501e  jmp     short loc_180004FAC
```
