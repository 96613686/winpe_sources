# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180016060`
- end: `0x18001611d`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180016eb4`
- `0x18001709c`
- `0x180017234`
- `0x1800187bc`

## callees

- `0x180016060`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800160a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800160fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800160a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800160fe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001608a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001608a`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_180037494;
  if ( !dword_180037494 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1800374D8 )
      {
        v1 = dword_180037494;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_1800374D8 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_1800374D8,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_1800374D8 )
      {
        v1 = 1;
        dword_180037494 = 1;
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
0x180016060  push    rbx
0x180016062  sub     rsp, 20h
0x180016066  mov     ebx, cs:dword_180037494
0x18001606c  nop
0x18001606d  test    ebx, ebx
0x18001606f  jnz     loc_180016106
0x180016075  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001607b  test    eax, eax
0x18001607d  jz      loc_180016104
0x180016083  lea     rcx, SRWLock; SRWLock
0x18001608a  call    cs:__imp_AcquireSRWLockExclusive
0x180016090  cmp     cs:qword_1800374D8, 0
0x180016098  jz      short loc_1800160B0
0x18001609a  mov     ebx, cs:dword_180037494
0x1800160a0  nop
0x1800160a1  lea     rcx, SRWLock; SRWLock
0x1800160a8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800160ae  jmp     short loc_180016106
0x1800160b0  mov     cs:qword_1800374D8, 0
0x1800160bb  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800160c2  test    rax, rax
0x1800160c5  jnz     short loc_1800160D3
0x1800160c7  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800160ce  test    rax, rax
0x1800160d1  jz      short loc_1800160ED
0x1800160d3  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800160da  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x1800160e1  lea     rcx, qword_1800374D8
0x1800160e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160ed  lea     rcx, SRWLock; SRWLock
0x1800160f4  cmp     cs:qword_1800374D8, 0
0x1800160fc  jnz     short loc_18001610E
0x1800160fe  call    cs:__imp_ReleaseSRWLockExclusive
0x180016104  xor     ebx, ebx
0x180016106  mov     eax, ebx
0x180016108  add     rsp, 20h
0x18001610c  pop     rbx
0x18001610d  retn
0x18001610e  nop
0x18001610f  mov     ebx, 1
0x180016114  mov     cs:dword_180037494, ebx
0x18001611a  jmp     short loc_1800160A8
```
