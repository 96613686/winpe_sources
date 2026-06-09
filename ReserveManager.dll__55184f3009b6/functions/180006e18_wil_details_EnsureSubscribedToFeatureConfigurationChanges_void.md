# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180006e18`
- end: `0x180006ede`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `198`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008154`
- `0x180016040`
- `0x180016134`
- `0x180016228`
- `0x180027c6c`
- `0x180027e58`

## callees

- `0x180006e18`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006e4b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006e4b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006e69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006ebf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006e69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006ebf`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, void (__fastcall *)(wil::details::EnabledStateManager *), void *); // rax

  v1 = dword_18004C4B4;
  if ( !dword_18004C4B4 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_18004C4F8 )
      {
        v1 = dword_18004C4B4;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_18004C4F8 = 0;
      v2 = (void (__fastcall *)(__int64 *, void (__fastcall *)(wil::details::EnabledStateManager *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, void (__fastcall *)(wil::details::EnabledStateManager *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_18004C4F8,
          `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_18004C4F8 )
      {
        v1 = 1;
        dword_18004C4B4 = 1;
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
0x180006e18  push    rbx
0x180006e1a  sub     rsp, 30h
0x180006e1e  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180006e27  mov     ebx, cs:dword_18004C4B4
0x180006e2d  nop
0x180006e2e  test    ebx, ebx
0x180006e30  jnz     loc_180006EC7
0x180006e36  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180006e3c  test    eax, eax
0x180006e3e  jz      loc_180006EC5
0x180006e44  lea     rcx, SRWLock; SRWLock
0x180006e4b  call    cs:__imp_AcquireSRWLockExclusive
0x180006e51  cmp     cs:qword_18004C4F8, 0
0x180006e59  jz      short loc_180006E71
0x180006e5b  mov     ebx, cs:dword_18004C4B4
0x180006e61  nop
0x180006e62  lea     rcx, SRWLock; SRWLock
0x180006e69  call    cs:__imp_ReleaseSRWLockExclusive
0x180006e6f  jmp     short loc_180006EC7
0x180006e71  mov     cs:qword_18004C4F8, 0
0x180006e7c  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180006e83  test    rax, rax
0x180006e86  jnz     short loc_180006E94
0x180006e88  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180006e8f  test    rax, rax
0x180006e92  jz      short loc_180006EAE
0x180006e94  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180006e9b  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z; `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x180006ea2  lea     rcx, qword_18004C4F8
0x180006ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006eae  lea     rcx, SRWLock; SRWLock
0x180006eb5  cmp     cs:qword_18004C4F8, 0
0x180006ebd  jnz     short loc_180006ECF
0x180006ebf  call    cs:__imp_ReleaseSRWLockExclusive
0x180006ec5  xor     ebx, ebx
0x180006ec7  mov     eax, ebx
0x180006ec9  add     rsp, 30h
0x180006ecd  pop     rbx
0x180006ece  retn
0x180006ecf  nop
0x180006ed0  mov     ebx, 1
0x180006ed5  mov     cs:dword_18004C4B4, ebx
0x180006edb  jmp     short loc_180006E69
```
