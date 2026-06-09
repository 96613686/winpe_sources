# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000d6e0`
- end: `0x18000d79d`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `14`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d7a4`
- `0x18000d978`
- `0x18000daec`
- `0x18000dc60`
- `0x18000ddd4`
- `0x18000df48`
- `0x18000e0bc`
- `0x18000e230`
- `0x18000e310`
- `0x18000e3f0`
- `0x18000e4d0`
- `0x18000e5b0`
- `0x18000e690`
- `0x18000e770`

## callees

- `0x18000d6e0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d70a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d70a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d728`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d77e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d728`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d77e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(), void *); // rax

  v1 = dword_18001A354;
  if ( !dword_18001A354 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_18001A398 )
      {
        v1 = dword_18001A354;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_18001A398 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_18001A398,
          `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_18001A398 )
      {
        v1 = 1;
        dword_18001A354 = 1;
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
0x18000d6e0  push    rbx
0x18000d6e2  sub     rsp, 20h
0x18000d6e6  mov     ebx, cs:dword_18001A354
0x18000d6ec  nop
0x18000d6ed  test    ebx, ebx
0x18000d6ef  jnz     loc_18000D786
0x18000d6f5  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000d6fb  test    eax, eax
0x18000d6fd  jz      loc_18000D784
0x18000d703  lea     rcx, SRWLock; SRWLock
0x18000d70a  call    cs:__imp_AcquireSRWLockExclusive
0x18000d710  cmp     cs:qword_18001A398, 0
0x18000d718  jz      short loc_18000D730
0x18000d71a  mov     ebx, cs:dword_18001A354
0x18000d720  nop
0x18000d721  lea     rcx, SRWLock; SRWLock
0x18000d728  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d72e  jmp     short loc_18000D786
0x18000d730  mov     cs:qword_18001A398, 0
0x18000d73b  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000d742  test    rax, rax
0x18000d745  jnz     short loc_18000D753
0x18000d747  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000d74e  test    rax, rax
0x18000d751  jz      short loc_18000D76D
0x18000d753  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000d75a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z; `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x18000d761  lea     rcx, qword_18001A398
0x18000d768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d76d  lea     rcx, SRWLock; SRWLock
0x18000d774  cmp     cs:qword_18001A398, 0
0x18000d77c  jnz     short loc_18000D78E
0x18000d77e  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d784  xor     ebx, ebx
0x18000d786  mov     eax, ebx
0x18000d788  add     rsp, 20h
0x18000d78c  pop     rbx
0x18000d78d  retn
0x18000d78e  nop
0x18000d78f  mov     ebx, 1
0x18000d794  mov     cs:dword_18001A354, ebx
0x18000d79a  jmp     short loc_18000D728
```
