# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x140004168`
- end: `0x140004223`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `187`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `31`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140005e94`
- `0x1400060c4`
- `0x1400062f4`
- `0x140006524`
- `0x140006754`
- `0x140006984`
- `0x140006bb4`
- `0x140006de4`
- `0x140007014`
- `0x140007244`
- `0x140007474`
- `0x1400076a4`
- `0x1400078d4`
- `0x140007b04`
- `0x140007d34`
- `0x140007f64`
- `0x140008194`
- `0x1400083c4`
- `0x1400085f4`
- `0x140008824`
- `0x140008a54`
- `0x140008c84`
- `0x140008eb4`
- `0x1400090e4`
- `0x140009314`
- `0x140009544`
- `0x140009774`
- `0x1400099a4`
- `0x140009bd4`
- `0x140009e04`
- `0x14000a034`

## callees

- `0x140004168`
- `0x14000f4d0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400041ae`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140004204`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400041ae`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140004204`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140004190`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140004190`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_14001511C;
  if ( !dword_14001511C )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_140015120 )
      {
        v1 = dword_14001511C;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_140015120 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_140015120,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_140015120 )
      {
        v1 = 1;
        dword_14001511C = 1;
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
0x140004168  push    rbx
0x14000416a  sub     rsp, 20h
0x14000416e  mov     ebx, cs:dword_14001511C
0x140004174  nop
0x140004175  test    ebx, ebx
0x140004177  jnz     loc_14000420C
0x14000417d  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, bl; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140004183  jz      loc_14000420A
0x140004189  lea     rcx, SRWLock; SRWLock
0x140004190  call    cs:__imp_AcquireSRWLockExclusive
0x140004196  cmp     cs:qword_140015120, 0
0x14000419e  jz      short loc_1400041B6
0x1400041a0  mov     ebx, cs:dword_14001511C
0x1400041a6  nop
0x1400041a7  lea     rcx, SRWLock; SRWLock
0x1400041ae  call    cs:__imp_ReleaseSRWLockExclusive
0x1400041b4  jmp     short loc_14000420C
0x1400041b6  mov     cs:qword_140015120, 0
0x1400041c1  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1400041c8  test    rax, rax
0x1400041cb  jnz     short loc_1400041D9
0x1400041cd  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1400041d4  test    rax, rax
0x1400041d7  jz      short loc_1400041F3
0x1400041d9  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1400041e0  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x1400041e7  lea     rcx, qword_140015120
0x1400041ee  call    _guard_dispatch_icall
0x1400041f3  lea     rcx, SRWLock; SRWLock
0x1400041fa  cmp     cs:qword_140015120, 0
0x140004202  jnz     short loc_140004214
0x140004204  call    cs:__imp_ReleaseSRWLockExclusive
0x14000420a  xor     ebx, ebx
0x14000420c  mov     eax, ebx
0x14000420e  add     rsp, 20h
0x140004212  pop     rbx
0x140004213  retn
0x140004214  nop
0x140004215  mov     ebx, 1
0x14000421a  mov     cs:dword_14001511C, ebx
0x140004220  jmp     short loc_1400041AE
```
