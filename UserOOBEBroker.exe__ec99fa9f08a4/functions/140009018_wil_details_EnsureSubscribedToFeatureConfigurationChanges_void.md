# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x140009018`
- end: `0x1400090d5`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000a244`
- `0x14000a660`

## callees

- `0x140009018`
- `0x14000f010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x140009042`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140009042`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140009060`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400090b6`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140009060`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400090b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_1400173D4;
  if ( !dword_1400173D4 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_140017418 )
      {
        v1 = dword_1400173D4;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_140017418 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_140017418,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_140017418 )
      {
        v1 = 1;
        dword_1400173D4 = 1;
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
0x140009018  push    rbx
0x14000901a  sub     rsp, 20h
0x14000901e  mov     ebx, cs:dword_1400173D4
0x140009024  nop
0x140009025  test    ebx, ebx
0x140009027  jnz     loc_1400090BE
0x14000902d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140009033  test    eax, eax
0x140009035  jz      loc_1400090BC
0x14000903b  lea     rcx, SRWLock; SRWLock
0x140009042  call    cs:__imp_AcquireSRWLockExclusive
0x140009048  cmp     cs:qword_140017418, 0
0x140009050  jz      short loc_140009068
0x140009052  mov     ebx, cs:dword_1400173D4
0x140009058  nop
0x140009059  lea     rcx, SRWLock; SRWLock
0x140009060  call    cs:__imp_ReleaseSRWLockExclusive
0x140009066  jmp     short loc_1400090BE
0x140009068  mov     cs:qword_140017418, 0
0x140009073  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x14000907a  test    rax, rax
0x14000907d  jnz     short loc_14000908B
0x14000907f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x140009086  test    rax, rax
0x140009089  jz      short loc_1400090A5
0x14000908b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140009092  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x140009099  lea     rcx, qword_140017418
0x1400090a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400090a5  lea     rcx, SRWLock; SRWLock
0x1400090ac  cmp     cs:qword_140017418, 0
0x1400090b4  jnz     short loc_1400090C6
0x1400090b6  call    cs:__imp_ReleaseSRWLockExclusive
0x1400090bc  xor     ebx, ebx
0x1400090be  mov     eax, ebx
0x1400090c0  add     rsp, 20h
0x1400090c4  pop     rbx
0x1400090c5  retn
0x1400090c6  nop
0x1400090c7  mov     ebx, 1
0x1400090cc  mov     cs:dword_1400173D4, ebx
0x1400090d2  jmp     short loc_140009060
```
