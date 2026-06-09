# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000b284`
- end: `0x18000b351`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `205`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c928`
- `0x18001cbdc`
- `0x18001cd7c`
- `0x18001ce64`

## callees

- `0x18000b284`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b2d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b32b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b2d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b32b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b2ae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b2ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_18003CA64;
  if ( !dword_18003CA64 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_18003CAA8 )
      {
        v1 = dword_18003CA64;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_18003CAA8 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_18003CAA8,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_18003CAA8 )
      {
        v1 = 1;
        dword_18003CA64 = 1;
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
0x18000b284  push    rbx
0x18000b286  sub     rsp, 20h
0x18000b28a  mov     ebx, cs:dword_18003CA64
0x18000b290  nop
0x18000b291  test    ebx, ebx
0x18000b293  jnz     loc_18000B339
0x18000b299  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000b29f  test    eax, eax
0x18000b2a1  jz      loc_18000B337
0x18000b2a7  lea     rcx, SRWLock; SRWLock
0x18000b2ae  call    cs:__imp_AcquireSRWLockExclusive
0x18000b2b5  nop     dword ptr [rax+rax+00h]
0x18000b2ba  cmp     cs:qword_18003CAA8, 0
0x18000b2c2  jz      short loc_18000B2E0
0x18000b2c4  mov     ebx, cs:dword_18003CA64
0x18000b2ca  nop
0x18000b2cb  lea     rcx, SRWLock; SRWLock
0x18000b2d2  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b2d9  nop     dword ptr [rax+rax+00h]
0x18000b2de  jmp     short loc_18000B339
0x18000b2e0  and     cs:qword_18003CAA8, 0
0x18000b2e8  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000b2ef  test    rax, rax
0x18000b2f2  jnz     short loc_18000B300
0x18000b2f4  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000b2fb  test    rax, rax
0x18000b2fe  jz      short loc_18000B31A
0x18000b300  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000b307  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18000b30e  lea     rcx, qword_18003CAA8
0x18000b315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b31a  lea     rcx, SRWLock; SRWLock
0x18000b321  cmp     cs:qword_18003CAA8, 0
0x18000b329  jnz     short loc_18000B342
0x18000b32b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b332  nop     dword ptr [rax+rax+00h]
0x18000b337  xor     ebx, ebx
0x18000b339  mov     eax, ebx
0x18000b33b  add     rsp, 20h
0x18000b33f  pop     rbx
0x18000b340  retn
0x18000b342  nop
0x18000b343  mov     ebx, 1
0x18000b348  mov     cs:dword_18003CA64, ebx
0x18000b34e  jmp     short loc_18000B2D2
```
