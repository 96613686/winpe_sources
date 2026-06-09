# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000ab78`
- end: `0x18000ac35`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `12`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ac3c`
- `0x18000ae10`
- `0x18000af84`
- `0x18000b0f8`
- `0x18000b26c`
- `0x18000b3e0`
- `0x18000b554`
- `0x18000b634`
- `0x18000b714`
- `0x18000b7f4`
- `0x18000b8d4`
- `0x18000b9b4`

## callees

- `0x18000ab78`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000aba2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000aba2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000abc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ac16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000abc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ac16`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(), void *); // rax

  v1 = dword_180015374;
  if ( !dword_180015374 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1800153B8 )
      {
        v1 = dword_180015374;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_1800153B8 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_1800153B8,
          `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_1800153B8 )
      {
        v1 = 1;
        dword_180015374 = 1;
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
0x18000ab78  push    rbx
0x18000ab7a  sub     rsp, 20h
0x18000ab7e  mov     ebx, cs:dword_180015374
0x18000ab84  nop
0x18000ab85  test    ebx, ebx
0x18000ab87  jnz     loc_18000AC1E
0x18000ab8d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000ab93  test    eax, eax
0x18000ab95  jz      loc_18000AC1C
0x18000ab9b  lea     rcx, SRWLock; SRWLock
0x18000aba2  call    cs:__imp_AcquireSRWLockExclusive
0x18000aba8  cmp     cs:qword_1800153B8, 0
0x18000abb0  jz      short loc_18000ABC8
0x18000abb2  mov     ebx, cs:dword_180015374
0x18000abb8  nop
0x18000abb9  lea     rcx, SRWLock; SRWLock
0x18000abc0  call    cs:__imp_ReleaseSRWLockExclusive
0x18000abc6  jmp     short loc_18000AC1E
0x18000abc8  mov     cs:qword_1800153B8, 0
0x18000abd3  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000abda  test    rax, rax
0x18000abdd  jnz     short loc_18000ABEB
0x18000abdf  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000abe6  test    rax, rax
0x18000abe9  jz      short loc_18000AC05
0x18000abeb  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000abf2  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z; `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x18000abf9  lea     rcx, qword_1800153B8
0x18000ac00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac05  lea     rcx, SRWLock; SRWLock
0x18000ac0c  cmp     cs:qword_1800153B8, 0
0x18000ac14  jnz     short loc_18000AC26
0x18000ac16  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ac1c  xor     ebx, ebx
0x18000ac1e  mov     eax, ebx
0x18000ac20  add     rsp, 20h
0x18000ac24  pop     rbx
0x18000ac25  retn
0x18000ac26  nop
0x18000ac27  mov     ebx, 1
0x18000ac2c  mov     cs:dword_180015374, ebx
0x18000ac32  jmp     short loc_18000ABC0
```
