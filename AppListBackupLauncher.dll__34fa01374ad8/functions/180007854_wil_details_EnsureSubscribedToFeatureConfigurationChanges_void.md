# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180007854`
- end: `0x180007911`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007d94`
- `0x180007e74`
- `0x180007fe8`
- `0x180009108`

## callees

- `0x180007854`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000789c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800078f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000789c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800078f2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000787e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000787e`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_1800196D4;
  if ( !dword_1800196D4 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180019718 )
      {
        v1 = dword_1800196D4;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180019718 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180019718,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180019718 )
      {
        v1 = 1;
        dword_1800196D4 = 1;
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
0x180007854  push    rbx
0x180007856  sub     rsp, 20h
0x18000785a  mov     ebx, cs:dword_1800196D4
0x180007860  nop
0x180007861  test    ebx, ebx
0x180007863  jnz     loc_1800078FA
0x180007869  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000786f  test    eax, eax
0x180007871  jz      loc_1800078F8
0x180007877  lea     rcx, SRWLock; SRWLock
0x18000787e  call    cs:__imp_AcquireSRWLockExclusive
0x180007884  cmp     cs:qword_180019718, 0
0x18000788c  jz      short loc_1800078A4
0x18000788e  mov     ebx, cs:dword_1800196D4
0x180007894  nop
0x180007895  lea     rcx, SRWLock; SRWLock
0x18000789c  call    cs:__imp_ReleaseSRWLockExclusive
0x1800078a2  jmp     short loc_1800078FA
0x1800078a4  mov     cs:qword_180019718, 0
0x1800078af  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800078b6  test    rax, rax
0x1800078b9  jnz     short loc_1800078C7
0x1800078bb  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800078c2  test    rax, rax
0x1800078c5  jz      short loc_1800078E1
0x1800078c7  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800078ce  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x1800078d5  lea     rcx, qword_180019718
0x1800078dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078e1  lea     rcx, SRWLock; SRWLock
0x1800078e8  cmp     cs:qword_180019718, 0
0x1800078f0  jnz     short loc_180007902
0x1800078f2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800078f8  xor     ebx, ebx
0x1800078fa  mov     eax, ebx
0x1800078fc  add     rsp, 20h
0x180007900  pop     rbx
0x180007901  retn
0x180007902  nop
0x180007903  mov     ebx, 1
0x180007908  mov     cs:dword_1800196D4, ebx
0x18000790e  jmp     short loc_18000789C
```
