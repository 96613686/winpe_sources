# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180004618`
- end: `0x1800046d4`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `188`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004b64`
- `0x180005890`

## callees

- `0x180004618`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004642`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004642`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004660`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800046b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004660`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800046b6`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_18001237C;
  if ( !dword_18001237C )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1800123C0 )
      {
        v1 = dword_18001237C;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_1800123C0 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_1800123C0,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_1800123C0 )
      {
        v1 = 1;
        dword_18001237C = 1;
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
0x180004618  push    rbx
0x18000461a  sub     rsp, 20h
0x18000461e  mov     ebx, cs:dword_18001237C
0x180004624  nop
0x180004625  test    ebx, ebx
0x180004627  jnz     loc_1800046BE
0x18000462d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004633  test    eax, eax
0x180004635  jz      loc_1800046BC
0x18000463b  lea     rcx, SRWLock; SRWLock
0x180004642  call    cs:__imp_AcquireSRWLockExclusive
0x180004648  cmp     cs:qword_1800123C0, 0
0x180004650  jz      short loc_180004668
0x180004652  mov     ebx, cs:dword_18001237C
0x180004658  lea     rcx, SRWLock; SRWLock
0x18000465f  nop
0x180004660  call    cs:__imp_ReleaseSRWLockExclusive
0x180004666  jmp     short loc_1800046BE
0x180004668  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000466f  mov     cs:qword_1800123C0, 0
0x18000467a  test    rax, rax
0x18000467d  jnz     short loc_18000468B
0x18000467f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180004686  test    rax, rax
0x180004689  jz      short loc_1800046A5
0x18000468b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004692  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180004699  lea     rcx, qword_1800123C0
0x1800046a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046a5  cmp     cs:qword_1800123C0, 0
0x1800046ad  lea     rcx, SRWLock; SRWLock
0x1800046b4  jnz     short loc_1800046C6
0x1800046b6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800046bc  xor     ebx, ebx
0x1800046be  mov     eax, ebx
0x1800046c0  add     rsp, 20h
0x1800046c4  pop     rbx
0x1800046c5  retn
0x1800046c6  mov     ebx, 1
0x1800046cb  nop
0x1800046cc  mov     cs:dword_18001237C, ebx
0x1800046d2  jmp     short loc_180004660
```
