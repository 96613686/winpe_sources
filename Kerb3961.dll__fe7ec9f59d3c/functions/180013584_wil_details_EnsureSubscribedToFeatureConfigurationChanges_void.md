# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180013584`
- end: `0x180013640`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `188`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180013c8c`
- `0x180013e5c`
- `0x180014828`

## callees

- `0x180013584`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800135ae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800135ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800135cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013622`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800135cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013622`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(), void *); // rax

  v1 = dword_1800297EC;
  if ( !dword_1800297EC )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180029830 )
      {
        v1 = dword_1800297EC;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_180029830 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180029830,
          `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180029830 )
      {
        v1 = 1;
        dword_1800297EC = 1;
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
0x180013584  push    rbx
0x180013586  sub     rsp, 20h
0x18001358a  mov     ebx, cs:dword_1800297EC
0x180013590  nop
0x180013591  test    ebx, ebx
0x180013593  jnz     loc_18001362A
0x180013599  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001359f  test    eax, eax
0x1800135a1  jz      loc_180013628
0x1800135a7  lea     rcx, SRWLock; SRWLock
0x1800135ae  call    cs:__imp_AcquireSRWLockExclusive
0x1800135b4  cmp     cs:qword_180029830, 0
0x1800135bc  jz      short loc_1800135D4
0x1800135be  mov     ebx, cs:dword_1800297EC
0x1800135c4  lea     rcx, SRWLock; SRWLock
0x1800135cb  nop
0x1800135cc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800135d2  jmp     short loc_18001362A
0x1800135d4  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800135db  mov     cs:qword_180029830, 0
0x1800135e6  test    rax, rax
0x1800135e9  jnz     short loc_1800135F7
0x1800135eb  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800135f2  test    rax, rax
0x1800135f5  jz      short loc_180013611
0x1800135f7  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800135fe  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z; `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x180013605  lea     rcx, qword_180029830
0x18001360c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013611  cmp     cs:qword_180029830, 0
0x180013619  lea     rcx, SRWLock; SRWLock
0x180013620  jnz     short loc_180013632
0x180013622  call    cs:__imp_ReleaseSRWLockExclusive
0x180013628  xor     ebx, ebx
0x18001362a  mov     eax, ebx
0x18001362c  add     rsp, 20h
0x180013630  pop     rbx
0x180013631  retn
0x180013632  mov     ebx, 1
0x180013637  nop
0x180013638  mov     cs:dword_1800297EC, ebx
0x18001363e  jmp     short loc_1800135CC
```
