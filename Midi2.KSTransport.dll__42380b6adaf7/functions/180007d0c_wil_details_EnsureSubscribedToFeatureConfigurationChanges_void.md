# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180007d0c`
- end: `0x180007dc9`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `20`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180019068`
- `0x18001923c`
- `0x180019410`
- `0x180019584`
- `0x1800196f8`
- `0x18001986c`
- `0x1800199e0`
- `0x180019b54`
- `0x180019cc8`
- `0x180019da8`
- `0x180019e88`
- `0x180019f68`
- `0x18001a048`
- `0x18001a128`
- `0x18001a208`
- `0x1800261c8`
- `0x18002639c`
- `0x18002647c`
- `0x18002caf8`
- `0x18003c8e8`

## callees

- `0x180007d0c`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007d54`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007daa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007d54`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007daa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007d36`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007d36`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(), void *); // rax

  v1 = dword_180071894;
  if ( !dword_180071894 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1800718D8 )
      {
        v1 = dword_180071894;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_1800718D8 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_1800718D8,
          `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_1800718D8 )
      {
        v1 = 1;
        dword_180071894 = 1;
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
0x180007d0c  push    rbx
0x180007d0e  sub     rsp, 20h
0x180007d12  mov     ebx, cs:dword_180071894
0x180007d18  nop
0x180007d19  test    ebx, ebx
0x180007d1b  jnz     loc_180007DB2
0x180007d21  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180007d27  test    eax, eax
0x180007d29  jz      loc_180007DB0
0x180007d2f  lea     rcx, SRWLock; SRWLock
0x180007d36  call    cs:__imp_AcquireSRWLockExclusive
0x180007d3c  cmp     cs:qword_1800718D8, 0
0x180007d44  jz      short loc_180007D5C
0x180007d46  mov     ebx, cs:dword_180071894
0x180007d4c  nop
0x180007d4d  lea     rcx, SRWLock; SRWLock
0x180007d54  call    cs:__imp_ReleaseSRWLockExclusive
0x180007d5a  jmp     short loc_180007DB2
0x180007d5c  mov     cs:qword_1800718D8, 0
0x180007d67  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180007d6e  test    rax, rax
0x180007d71  jnz     short loc_180007D7F
0x180007d73  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180007d7a  test    rax, rax
0x180007d7d  jz      short loc_180007D99
0x180007d7f  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180007d86  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z; `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x180007d8d  lea     rcx, qword_1800718D8
0x180007d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d99  lea     rcx, SRWLock; SRWLock
0x180007da0  cmp     cs:qword_1800718D8, 0
0x180007da8  jnz     short loc_180007DBA
0x180007daa  call    cs:__imp_ReleaseSRWLockExclusive
0x180007db0  xor     ebx, ebx
0x180007db2  mov     eax, ebx
0x180007db4  add     rsp, 20h
0x180007db8  pop     rbx
0x180007db9  retn
0x180007dba  nop
0x180007dbb  mov     ebx, 1
0x180007dc0  mov     cs:dword_180071894, ebx
0x180007dc6  jmp     short loc_180007D54
```
