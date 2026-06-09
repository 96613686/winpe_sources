# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180029a34`
- end: `0x180029af1`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002a464`
- `0x18002b258`

## callees

- `0x180029a34`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029a7c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029ad2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029a7c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029ad2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029a5e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029a5e`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_180046454;
  if ( !dword_180046454 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180046498 )
      {
        v1 = dword_180046454;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180046498 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180046498,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180046498 )
      {
        v1 = 1;
        dword_180046454 = 1;
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
0x180029a34  push    rbx
0x180029a36  sub     rsp, 20h
0x180029a3a  mov     ebx, cs:dword_180046454
0x180029a40  nop
0x180029a41  test    ebx, ebx
0x180029a43  jnz     loc_180029ADA
0x180029a49  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180029a4f  test    eax, eax
0x180029a51  jz      loc_180029AD8
0x180029a57  lea     rcx, SRWLock; SRWLock
0x180029a5e  call    cs:__imp_AcquireSRWLockExclusive
0x180029a64  cmp     cs:qword_180046498, 0
0x180029a6c  jz      short loc_180029A84
0x180029a6e  mov     ebx, cs:dword_180046454
0x180029a74  nop
0x180029a75  lea     rcx, SRWLock; SRWLock
0x180029a7c  call    cs:__imp_ReleaseSRWLockExclusive
0x180029a82  jmp     short loc_180029ADA
0x180029a84  mov     cs:qword_180046498, 0
0x180029a8f  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180029a96  test    rax, rax
0x180029a99  jnz     short loc_180029AA7
0x180029a9b  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180029aa2  test    rax, rax
0x180029aa5  jz      short loc_180029AC1
0x180029aa7  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180029aae  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180029ab5  lea     rcx, qword_180046498
0x180029abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ac1  lea     rcx, SRWLock; SRWLock
0x180029ac8  cmp     cs:qword_180046498, 0
0x180029ad0  jnz     short loc_180029AE2
0x180029ad2  call    cs:__imp_ReleaseSRWLockExclusive
0x180029ad8  xor     ebx, ebx
0x180029ada  mov     eax, ebx
0x180029adc  add     rsp, 20h
0x180029ae0  pop     rbx
0x180029ae1  retn
0x180029ae2  nop
0x180029ae3  mov     ebx, 1
0x180029ae8  mov     cs:dword_180046454, ebx
0x180029aee  jmp     short loc_180029A7C
```
