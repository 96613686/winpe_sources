# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180008ad0`
- end: `0x180008b8b`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `187`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `15`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001b974`
- `0x18001bb04`
- `0x18001bc94`
- `0x180029030`
- `0x180029318`
- `0x180029600`
- `0x18002b6bc`
- `0x18002c168`
- `0x180045b94`
- `0x180045d6c`
- `0x180046778`
- `0x1800471b4`
- `0x1800474dc`
- `0x18004abe0`
- `0x18004afc0`

## callees

- `0x180008ad0`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008af8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008af8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008b16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008b6c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008b16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008b6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(), void *); // rax

  v1 = dword_18009D48C;
  if ( !dword_18009D48C )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_18009D490 )
      {
        v1 = dword_18009D48C;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_18009D490 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_18009D490,
          `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_18009D490 )
      {
        v1 = 1;
        dword_18009D48C = 1;
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
0x180008ad0  push    rbx
0x180008ad2  sub     rsp, 20h
0x180008ad6  mov     ebx, cs:dword_18009D48C
0x180008adc  nop
0x180008add  test    ebx, ebx
0x180008adf  jnz     loc_180008B74
0x180008ae5  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, bl; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008aeb  jz      loc_180008B72
0x180008af1  lea     rcx, SRWLock; SRWLock
0x180008af8  call    cs:__imp_AcquireSRWLockExclusive
0x180008afe  cmp     cs:qword_18009D490, 0
0x180008b06  jz      short loc_180008B1E
0x180008b08  mov     ebx, cs:dword_18009D48C
0x180008b0e  nop
0x180008b0f  lea     rcx, SRWLock; SRWLock
0x180008b16  call    cs:__imp_ReleaseSRWLockExclusive
0x180008b1c  jmp     short loc_180008B74
0x180008b1e  mov     cs:qword_18009D490, 0
0x180008b29  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180008b30  test    rax, rax
0x180008b33  jnz     short loc_180008B41
0x180008b35  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180008b3c  test    rax, rax
0x180008b3f  jz      short loc_180008B5B
0x180008b41  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008b48  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z; `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x180008b4f  lea     rcx, qword_18009D490
0x180008b56  call    _guard_dispatch_icall
0x180008b5b  lea     rcx, SRWLock; SRWLock
0x180008b62  cmp     cs:qword_18009D490, 0
0x180008b6a  jnz     short loc_180008B7C
0x180008b6c  call    cs:__imp_ReleaseSRWLockExclusive
0x180008b72  xor     ebx, ebx
0x180008b74  mov     eax, ebx
0x180008b76  add     rsp, 20h
0x180008b7a  pop     rbx
0x180008b7b  retn
0x180008b7c  nop
0x180008b7d  mov     ebx, 1
0x180008b82  mov     cs:dword_18009D48C, ebx
0x180008b88  jmp     short loc_180008B16
```
