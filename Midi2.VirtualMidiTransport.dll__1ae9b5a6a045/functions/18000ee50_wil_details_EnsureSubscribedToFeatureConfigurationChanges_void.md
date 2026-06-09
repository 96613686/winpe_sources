# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000ee50`
- end: `0x18000ef0d`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `14`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ef14`
- `0x18000f0e8`
- `0x18000f25c`
- `0x18000f3d0`
- `0x18000f544`
- `0x18000f6b8`
- `0x18000f82c`
- `0x18000f9a0`
- `0x18000fa80`
- `0x18000fb60`
- `0x18000fc40`
- `0x18000fd20`
- `0x18000fe00`
- `0x18000fee0`

## callees

- `0x18000ee50`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ee7a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ee7a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ee98`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000eeee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ee98`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000eeee`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(), void *); // rax

  v1 = dword_18002D714;
  if ( !dword_18002D714 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_18002D758 )
      {
        v1 = dword_18002D714;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_18002D758 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_18002D758,
          `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_18002D758 )
      {
        v1 = 1;
        dword_18002D714 = 1;
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
0x18000ee50  push    rbx
0x18000ee52  sub     rsp, 20h
0x18000ee56  mov     ebx, cs:dword_18002D714
0x18000ee5c  nop
0x18000ee5d  test    ebx, ebx
0x18000ee5f  jnz     loc_18000EEF6
0x18000ee65  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000ee6b  test    eax, eax
0x18000ee6d  jz      loc_18000EEF4
0x18000ee73  lea     rcx, SRWLock; SRWLock
0x18000ee7a  call    cs:__imp_AcquireSRWLockExclusive
0x18000ee80  cmp     cs:qword_18002D758, 0
0x18000ee88  jz      short loc_18000EEA0
0x18000ee8a  mov     ebx, cs:dword_18002D714
0x18000ee90  nop
0x18000ee91  lea     rcx, SRWLock; SRWLock
0x18000ee98  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ee9e  jmp     short loc_18000EEF6
0x18000eea0  mov     cs:qword_18002D758, 0
0x18000eeab  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000eeb2  test    rax, rax
0x18000eeb5  jnz     short loc_18000EEC3
0x18000eeb7  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000eebe  test    rax, rax
0x18000eec1  jz      short loc_18000EEDD
0x18000eec3  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000eeca  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z; `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x18000eed1  lea     rcx, qword_18002D758
0x18000eed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eedd  lea     rcx, SRWLock; SRWLock
0x18000eee4  cmp     cs:qword_18002D758, 0
0x18000eeec  jnz     short loc_18000EEFE
0x18000eeee  call    cs:__imp_ReleaseSRWLockExclusive
0x18000eef4  xor     ebx, ebx
0x18000eef6  mov     eax, ebx
0x18000eef8  add     rsp, 20h
0x18000eefc  pop     rbx
0x18000eefd  retn
0x18000eefe  nop
0x18000eeff  mov     ebx, 1
0x18000ef04  mov     cs:dword_18002D714, ebx
0x18000ef0a  jmp     short loc_18000EE98
```
