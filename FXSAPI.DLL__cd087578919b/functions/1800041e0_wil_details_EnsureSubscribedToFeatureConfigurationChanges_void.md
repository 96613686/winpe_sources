# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1800041e0`
- end: `0x1800042b3`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `211`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800041e0`
- `0x18003e010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000422e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000428a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000422e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000428a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000420a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000420a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_180050E44;
  if ( !dword_180050E44 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180050E48 )
      {
        v1 = dword_180050E44;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180050E48 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180050E48,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180050E48 )
      {
        v1 = 1;
        dword_180050E44 = 1;
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
0x1800041e0  push    rbx
0x1800041e2  sub     rsp, 20h
0x1800041e6  mov     ebx, cs:dword_180050E44
0x1800041ec  nop
0x1800041ed  test    ebx, ebx
0x1800041ef  jnz     loc_180004298
0x1800041f5  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800041fb  test    eax, eax
0x1800041fd  jz      loc_180004296
0x180004203  lea     rcx, SRWLock; SRWLock
0x18000420a  call    cs:__imp_AcquireSRWLockExclusive
0x180004211  nop     dword ptr [rax+rax+00h]
0x180004216  cmp     cs:qword_180050E48, 0
0x18000421e  jz      short loc_18000423C
0x180004220  mov     ebx, cs:dword_180050E44
0x180004226  nop
0x180004227  lea     rcx, SRWLock; SRWLock
0x18000422e  call    cs:__imp_ReleaseSRWLockExclusive
0x180004235  nop     dword ptr [rax+rax+00h]
0x18000423a  jmp     short loc_180004298
0x18000423c  mov     cs:qword_180050E48, 0
0x180004247  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000424e  test    rax, rax
0x180004251  jnz     short loc_18000425F
0x180004253  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000425a  test    rax, rax
0x18000425d  jz      short loc_180004279
0x18000425f  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004266  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18000426d  lea     rcx, qword_180050E48
0x180004274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004279  lea     rcx, SRWLock; SRWLock
0x180004280  cmp     cs:qword_180050E48, 0
0x180004288  jnz     short loc_1800042A1
0x18000428a  call    cs:__imp_ReleaseSRWLockExclusive
0x180004291  nop     dword ptr [rax+rax+00h]
0x180004296  xor     ebx, ebx
0x180004298  mov     eax, ebx
0x18000429a  add     rsp, 20h
0x18000429e  pop     rbx
0x18000429f  retn
0x1800042a1  nop
0x1800042a2  mov     ebx, 1
0x1800042a7  mov     cs:dword_180050E44, ebx
0x1800042ad  jmp     loc_18000422E
```
