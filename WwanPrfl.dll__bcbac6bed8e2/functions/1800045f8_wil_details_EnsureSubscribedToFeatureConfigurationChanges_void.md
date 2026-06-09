# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1800045f8`
- end: `0x1800046b5`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004b44`
- `0x1800058c4`

## callees

- `0x1800045f8`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004640`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004696`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004640`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004696`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004622`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004622`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, void (__fastcall *)(__int64), void *); // rax

  v1 = dword_18001F41C;
  if ( !dword_18001F41C )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_18001F460 )
      {
        v1 = dword_18001F41C;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_18001F460 = 0;
      v2 = (void (__fastcall *)(__int64 *, void (__fastcall *)(__int64), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, void (__fastcall *)(__int64), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_18001F460,
          `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_18001F460 )
      {
        v1 = 1;
        dword_18001F41C = 1;
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
0x1800045f8  push    rbx
0x1800045fa  sub     rsp, 20h
0x1800045fe  mov     ebx, cs:dword_18001F41C
0x180004604  nop
0x180004605  test    ebx, ebx
0x180004607  jnz     loc_18000469E
0x18000460d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004613  test    eax, eax
0x180004615  jz      loc_18000469C
0x18000461b  lea     rcx, SRWLock; SRWLock
0x180004622  call    cs:__imp_AcquireSRWLockExclusive
0x180004628  cmp     cs:qword_18001F460, 0
0x180004630  jz      short loc_180004648
0x180004632  mov     ebx, cs:dword_18001F41C
0x180004638  nop
0x180004639  lea     rcx, SRWLock; SRWLock
0x180004640  call    cs:__imp_ReleaseSRWLockExclusive
0x180004646  jmp     short loc_18000469E
0x180004648  mov     cs:qword_18001F460, 0
0x180004653  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000465a  test    rax, rax
0x18000465d  jnz     short loc_18000466B
0x18000465f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180004666  test    rax, rax
0x180004669  jz      short loc_180004685
0x18000466b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004672  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z; `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x180004679  lea     rcx, qword_18001F460
0x180004680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004685  lea     rcx, SRWLock; SRWLock
0x18000468c  cmp     cs:qword_18001F460, 0
0x180004694  jnz     short loc_1800046A6
0x180004696  call    cs:__imp_ReleaseSRWLockExclusive
0x18000469c  xor     ebx, ebx
0x18000469e  mov     eax, ebx
0x1800046a0  add     rsp, 20h
0x1800046a4  pop     rbx
0x1800046a5  retn
0x1800046a6  nop
0x1800046a7  mov     ebx, 1
0x1800046ac  mov     cs:dword_18001F41C, ebx
0x1800046b2  jmp     short loc_180004640
```
