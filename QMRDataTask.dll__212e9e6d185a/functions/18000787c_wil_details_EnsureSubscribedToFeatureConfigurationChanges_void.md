# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000787c`
- end: `0x180007939`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `12`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007df0`
- `0x180007ed0`
- `0x180007fb0`
- `0x180008090`
- `0x180008170`
- `0x180008250`
- `0x180008330`
- `0x180008410`
- `0x180008584`
- `0x1800086f8`
- `0x18000886c`
- `0x18000ba78`

## callees

- `0x18000787c`
- `0x180015010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1800078a6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800078a6`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800078c4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000791a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800078c4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000791a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_180023724;
  if ( !dword_180023724 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180023768 )
      {
        v1 = dword_180023724;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180023768 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180023768,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180023768 )
      {
        v1 = 1;
        dword_180023724 = 1;
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
0x18000787c  push    rbx
0x18000787e  sub     rsp, 20h
0x180007882  mov     ebx, cs:dword_180023724
0x180007888  nop
0x180007889  test    ebx, ebx
0x18000788b  jnz     loc_180007922
0x180007891  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180007897  test    eax, eax
0x180007899  jz      loc_180007920
0x18000789f  lea     rcx, SRWLock; SRWLock
0x1800078a6  call    cs:__imp_AcquireSRWLockExclusive
0x1800078ac  cmp     cs:qword_180023768, 0
0x1800078b4  jz      short loc_1800078CC
0x1800078b6  mov     ebx, cs:dword_180023724
0x1800078bc  nop
0x1800078bd  lea     rcx, SRWLock; SRWLock
0x1800078c4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800078ca  jmp     short loc_180007922
0x1800078cc  mov     cs:qword_180023768, 0
0x1800078d7  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800078de  test    rax, rax
0x1800078e1  jnz     short loc_1800078EF
0x1800078e3  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800078ea  test    rax, rax
0x1800078ed  jz      short loc_180007909
0x1800078ef  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800078f6  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x1800078fd  lea     rcx, qword_180023768
0x180007904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007909  lea     rcx, SRWLock; SRWLock
0x180007910  cmp     cs:qword_180023768, 0
0x180007918  jnz     short loc_18000792A
0x18000791a  call    cs:__imp_ReleaseSRWLockExclusive
0x180007920  xor     ebx, ebx
0x180007922  mov     eax, ebx
0x180007924  add     rsp, 20h
0x180007928  pop     rbx
0x180007929  retn
0x18000792a  nop
0x18000792b  mov     ebx, 1
0x180007930  mov     cs:dword_180023724, ebx
0x180007936  jmp     short loc_1800078C4
```
