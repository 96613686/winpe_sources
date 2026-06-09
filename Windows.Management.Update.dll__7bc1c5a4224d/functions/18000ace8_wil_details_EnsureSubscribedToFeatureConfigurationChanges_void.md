# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000ace8`
- end: `0x18000ada5`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c3a0`
- `0x18001b984`
- `0x18001bb04`
- `0x18001bcd8`

## callees

- `0x18000ace8`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ad12`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ad12`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ad30`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ad86`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ad30`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ad86`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_18003AA74;
  if ( !dword_18003AA74 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_18003AAB8 )
      {
        v1 = dword_18003AA74;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_18003AAB8 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_18003AAB8,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_18003AAB8 )
      {
        v1 = 1;
        dword_18003AA74 = 1;
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
0x18000ace8  push    rbx
0x18000acea  sub     rsp, 20h
0x18000acee  mov     ebx, cs:dword_18003AA74
0x18000acf4  nop
0x18000acf5  test    ebx, ebx
0x18000acf7  jnz     loc_18000AD8E
0x18000acfd  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000ad03  test    eax, eax
0x18000ad05  jz      loc_18000AD8C
0x18000ad0b  lea     rcx, SRWLock; SRWLock
0x18000ad12  call    cs:__imp_AcquireSRWLockExclusive
0x18000ad18  cmp     cs:qword_18003AAB8, 0
0x18000ad20  jz      short loc_18000AD38
0x18000ad22  mov     ebx, cs:dword_18003AA74
0x18000ad28  nop
0x18000ad29  lea     rcx, SRWLock; SRWLock
0x18000ad30  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ad36  jmp     short loc_18000AD8E
0x18000ad38  mov     cs:qword_18003AAB8, 0
0x18000ad43  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000ad4a  test    rax, rax
0x18000ad4d  jnz     short loc_18000AD5B
0x18000ad4f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000ad56  test    rax, rax
0x18000ad59  jz      short loc_18000AD75
0x18000ad5b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000ad62  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18000ad69  lea     rcx, qword_18003AAB8
0x18000ad70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad75  lea     rcx, SRWLock; SRWLock
0x18000ad7c  cmp     cs:qword_18003AAB8, 0
0x18000ad84  jnz     short loc_18000AD96
0x18000ad86  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ad8c  xor     ebx, ebx
0x18000ad8e  mov     eax, ebx
0x18000ad90  add     rsp, 20h
0x18000ad94  pop     rbx
0x18000ad95  retn
0x18000ad96  nop
0x18000ad97  mov     ebx, 1
0x18000ad9c  mov     cs:dword_18003AA74, ebx
0x18000ada2  jmp     short loc_18000AD30
```
