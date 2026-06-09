# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000a98c`
- end: `0x18000aa49`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `20`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b49c`
- `0x18000b65c`
- `0x18000b81c`
- `0x18000b990`
- `0x18000bb04`
- `0x18000bc78`
- `0x18000bdec`
- `0x18000bf60`
- `0x18000c0d4`
- `0x18000c1b4`
- `0x18000c294`
- `0x18000c374`
- `0x18000c454`
- `0x18000c5c8`
- `0x18000c79c`
- `0x18000c87c`
- `0x18000c95c`
- `0x18000dc08`
- `0x1800160cc`
- `0x180031638`

## callees

- `0x18000a98c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a9d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000aa2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a9d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000aa2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a9b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a9b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_180082434;
  if ( !dword_180082434 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180082478 )
      {
        v1 = dword_180082434;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180082478 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180082478,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180082478 )
      {
        v1 = 1;
        dword_180082434 = 1;
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
0x18000a98c  push    rbx
0x18000a98e  sub     rsp, 20h
0x18000a992  mov     ebx, cs:dword_180082434
0x18000a998  nop
0x18000a999  test    ebx, ebx
0x18000a99b  jnz     loc_18000AA32
0x18000a9a1  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000a9a7  test    eax, eax
0x18000a9a9  jz      loc_18000AA30
0x18000a9af  lea     rcx, SRWLock; SRWLock
0x18000a9b6  call    cs:__imp_AcquireSRWLockExclusive
0x18000a9bc  cmp     cs:qword_180082478, 0
0x18000a9c4  jz      short loc_18000A9DC
0x18000a9c6  mov     ebx, cs:dword_180082434
0x18000a9cc  nop
0x18000a9cd  lea     rcx, SRWLock; SRWLock
0x18000a9d4  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a9da  jmp     short loc_18000AA32
0x18000a9dc  mov     cs:qword_180082478, 0
0x18000a9e7  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000a9ee  test    rax, rax
0x18000a9f1  jnz     short loc_18000A9FF
0x18000a9f3  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000a9fa  test    rax, rax
0x18000a9fd  jz      short loc_18000AA19
0x18000a9ff  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000aa06  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18000aa0d  lea     rcx, qword_180082478
0x18000aa14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa19  lea     rcx, SRWLock; SRWLock
0x18000aa20  cmp     cs:qword_180082478, 0
0x18000aa28  jnz     short loc_18000AA3A
0x18000aa2a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000aa30  xor     ebx, ebx
0x18000aa32  mov     eax, ebx
0x18000aa34  add     rsp, 20h
0x18000aa38  pop     rbx
0x18000aa39  retn
0x18000aa3a  nop
0x18000aa3b  mov     ebx, 1
0x18000aa40  mov     cs:dword_180082434, ebx
0x18000aa46  jmp     short loc_18000A9D4
```
