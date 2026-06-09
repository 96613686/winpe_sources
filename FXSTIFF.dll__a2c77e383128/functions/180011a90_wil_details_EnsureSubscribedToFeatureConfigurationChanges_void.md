# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180011a90`
- end: `0x180011b4d`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180011a90`
- `0x180019010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011ad8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011b2e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011ad8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011b2e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011aba`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011aba`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_1800702AC;
  if ( !dword_1800702AC )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1800702F0 )
      {
        v1 = dword_1800702AC;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_1800702F0 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_1800702F0,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_1800702F0 )
      {
        v1 = 1;
        dword_1800702AC = 1;
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
0x180011a90  push    rbx
0x180011a92  sub     rsp, 20h
0x180011a96  mov     ebx, cs:dword_1800702AC
0x180011a9c  nop
0x180011a9d  test    ebx, ebx
0x180011a9f  jnz     loc_180011B36
0x180011aa5  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180011aab  test    eax, eax
0x180011aad  jz      loc_180011B34
0x180011ab3  lea     rcx, SRWLock; SRWLock
0x180011aba  call    cs:__imp_AcquireSRWLockExclusive
0x180011ac0  cmp     cs:qword_1800702F0, 0
0x180011ac8  jz      short loc_180011AE0
0x180011aca  mov     ebx, cs:dword_1800702AC
0x180011ad0  nop
0x180011ad1  lea     rcx, SRWLock; SRWLock
0x180011ad8  call    cs:__imp_ReleaseSRWLockExclusive
0x180011ade  jmp     short loc_180011B36
0x180011ae0  mov     cs:qword_1800702F0, 0
0x180011aeb  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180011af2  test    rax, rax
0x180011af5  jnz     short loc_180011B03
0x180011af7  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180011afe  test    rax, rax
0x180011b01  jz      short loc_180011B1D
0x180011b03  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180011b0a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180011b11  lea     rcx, qword_1800702F0
0x180011b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b1d  lea     rcx, SRWLock; SRWLock
0x180011b24  cmp     cs:qword_1800702F0, 0
0x180011b2c  jnz     short loc_180011B3E
0x180011b2e  call    cs:__imp_ReleaseSRWLockExclusive
0x180011b34  xor     ebx, ebx
0x180011b36  mov     eax, ebx
0x180011b38  add     rsp, 20h
0x180011b3c  pop     rbx
0x180011b3d  retn
0x180011b3e  nop
0x180011b3f  mov     ebx, 1
0x180011b44  mov     cs:dword_1800702AC, ebx
0x180011b4a  jmp     short loc_180011AD8
```
