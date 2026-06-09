# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x14000e738`
- end: `0x14000e7f5`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140010084`

## callees

- `0x14000e738`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000e780`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000e7d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000e780`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000e7d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000e762`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000e762`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_140030444;
  if ( !dword_140030444 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_140030488 )
      {
        v1 = dword_140030444;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_140030488 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_140030488,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_140030488 )
      {
        v1 = 1;
        dword_140030444 = 1;
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
0x14000e738  push    rbx
0x14000e73a  sub     rsp, 20h
0x14000e73e  mov     ebx, cs:dword_140030444
0x14000e744  nop
0x14000e745  test    ebx, ebx
0x14000e747  jnz     loc_14000E7DE
0x14000e74d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000e753  test    eax, eax
0x14000e755  jz      loc_14000E7DC
0x14000e75b  lea     rcx, SRWLock; SRWLock
0x14000e762  call    cs:__imp_AcquireSRWLockExclusive
0x14000e768  cmp     cs:qword_140030488, 0
0x14000e770  jz      short loc_14000E788
0x14000e772  mov     ebx, cs:dword_140030444
0x14000e778  nop
0x14000e779  lea     rcx, SRWLock; SRWLock
0x14000e780  call    cs:__imp_ReleaseSRWLockExclusive
0x14000e786  jmp     short loc_14000E7DE
0x14000e788  mov     cs:qword_140030488, 0
0x14000e793  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x14000e79a  test    rax, rax
0x14000e79d  jnz     short loc_14000E7AB
0x14000e79f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x14000e7a6  test    rax, rax
0x14000e7a9  jz      short loc_14000E7C5
0x14000e7ab  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000e7b2  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x14000e7b9  lea     rcx, qword_140030488
0x14000e7c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e7c5  lea     rcx, SRWLock; SRWLock
0x14000e7cc  cmp     cs:qword_140030488, 0
0x14000e7d4  jnz     short loc_14000E7E6
0x14000e7d6  call    cs:__imp_ReleaseSRWLockExclusive
0x14000e7dc  xor     ebx, ebx
0x14000e7de  mov     eax, ebx
0x14000e7e0  add     rsp, 20h
0x14000e7e4  pop     rbx
0x14000e7e5  retn
0x14000e7e6  nop
0x14000e7e7  mov     ebx, 1
0x14000e7ec  mov     cs:dword_140030444, ebx
0x14000e7f2  jmp     short loc_14000E780
```
