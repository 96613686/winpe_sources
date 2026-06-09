# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000da08`
- end: `0x18000dac5`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `12`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000dacc`
- `0x18000dca0`
- `0x18000dd80`
- `0x18000df54`
- `0x18000e0c8`
- `0x18000e23c`
- `0x18000e3b0`
- `0x18000e524`
- `0x18000e604`
- `0x18000e6e4`
- `0x18000e7c4`
- `0x18000e8a4`

## callees

- `0x18000da08`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000da32`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000da32`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000da50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000daa6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000da50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000daa6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(), void *); // rax

  v1 = dword_18001E40C;
  if ( !dword_18001E40C )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_18001E450 )
      {
        v1 = dword_18001E40C;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_18001E450 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_18001E450,
          `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_18001E450 )
      {
        v1 = 1;
        dword_18001E40C = 1;
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
0x18000da08  push    rbx
0x18000da0a  sub     rsp, 20h
0x18000da0e  mov     ebx, cs:dword_18001E40C
0x18000da14  nop
0x18000da15  test    ebx, ebx
0x18000da17  jnz     loc_18000DAAE
0x18000da1d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000da23  test    eax, eax
0x18000da25  jz      loc_18000DAAC
0x18000da2b  lea     rcx, SRWLock; SRWLock
0x18000da32  call    cs:__imp_AcquireSRWLockExclusive
0x18000da38  cmp     cs:qword_18001E450, 0
0x18000da40  jz      short loc_18000DA58
0x18000da42  mov     ebx, cs:dword_18001E40C
0x18000da48  nop
0x18000da49  lea     rcx, SRWLock; SRWLock
0x18000da50  call    cs:__imp_ReleaseSRWLockExclusive
0x18000da56  jmp     short loc_18000DAAE
0x18000da58  mov     cs:qword_18001E450, 0
0x18000da63  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000da6a  test    rax, rax
0x18000da6d  jnz     short loc_18000DA7B
0x18000da6f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000da76  test    rax, rax
0x18000da79  jz      short loc_18000DA95
0x18000da7b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000da82  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z; `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x18000da89  lea     rcx, qword_18001E450
0x18000da90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da95  lea     rcx, SRWLock; SRWLock
0x18000da9c  cmp     cs:qword_18001E450, 0
0x18000daa4  jnz     short loc_18000DAB6
0x18000daa6  call    cs:__imp_ReleaseSRWLockExclusive
0x18000daac  xor     ebx, ebx
0x18000daae  mov     eax, ebx
0x18000dab0  add     rsp, 20h
0x18000dab4  pop     rbx
0x18000dab5  retn
0x18000dab6  nop
0x18000dab7  mov     ebx, 1
0x18000dabc  mov     cs:dword_18001E40C, ebx
0x18000dac2  jmp     short loc_18000DA50
```
