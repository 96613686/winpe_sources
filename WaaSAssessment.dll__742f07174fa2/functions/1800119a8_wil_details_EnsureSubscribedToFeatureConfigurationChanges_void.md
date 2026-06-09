# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1800119a8`
- end: `0x180011a65`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180012a60`
- `0x180012b40`
- `0x18001364c`

## callees

- `0x1800119a8`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800119f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011a46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800119f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011a46`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800119d2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800119d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_1800274A4;
  if ( !dword_1800274A4 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1800274E8 )
      {
        v1 = dword_1800274A4;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_1800274E8 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_1800274E8,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_1800274E8 )
      {
        v1 = 1;
        dword_1800274A4 = 1;
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
0x1800119a8  push    rbx
0x1800119aa  sub     rsp, 20h
0x1800119ae  mov     ebx, cs:dword_1800274A4
0x1800119b4  nop
0x1800119b5  test    ebx, ebx
0x1800119b7  jnz     loc_180011A4E
0x1800119bd  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800119c3  test    eax, eax
0x1800119c5  jz      loc_180011A4C
0x1800119cb  lea     rcx, SRWLock; SRWLock
0x1800119d2  call    cs:__imp_AcquireSRWLockExclusive
0x1800119d8  cmp     cs:qword_1800274E8, 0
0x1800119e0  jz      short loc_1800119F8
0x1800119e2  mov     ebx, cs:dword_1800274A4
0x1800119e8  nop
0x1800119e9  lea     rcx, SRWLock; SRWLock
0x1800119f0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800119f6  jmp     short loc_180011A4E
0x1800119f8  mov     cs:qword_1800274E8, 0
0x180011a03  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180011a0a  test    rax, rax
0x180011a0d  jnz     short loc_180011A1B
0x180011a0f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180011a16  test    rax, rax
0x180011a19  jz      short loc_180011A35
0x180011a1b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180011a22  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180011a29  lea     rcx, qword_1800274E8
0x180011a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a35  lea     rcx, SRWLock; SRWLock
0x180011a3c  cmp     cs:qword_1800274E8, 0
0x180011a44  jnz     short loc_180011A56
0x180011a46  call    cs:__imp_ReleaseSRWLockExclusive
0x180011a4c  xor     ebx, ebx
0x180011a4e  mov     eax, ebx
0x180011a50  add     rsp, 20h
0x180011a54  pop     rbx
0x180011a55  retn
0x180011a56  nop
0x180011a57  mov     ebx, 1
0x180011a5c  mov     cs:dword_1800274A4, ebx
0x180011a62  jmp     short loc_1800119F0
```
