# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180003d18`
- end: `0x180003dd4`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `188`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004e10`

## callees

- `0x180003d18`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003d60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003db6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003d60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003db6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003d42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003d42`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_18001225C;
  if ( !dword_18001225C )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1800122A0 )
      {
        v1 = dword_18001225C;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_1800122A0 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_1800122A0,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_1800122A0 )
      {
        v1 = 1;
        dword_18001225C = 1;
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
0x180003d18  push    rbx
0x180003d1a  sub     rsp, 20h
0x180003d1e  mov     ebx, cs:dword_18001225C
0x180003d24  nop
0x180003d25  test    ebx, ebx
0x180003d27  jnz     loc_180003DBE
0x180003d2d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180003d33  test    eax, eax
0x180003d35  jz      loc_180003DBC
0x180003d3b  lea     rcx, SRWLock; SRWLock
0x180003d42  call    cs:__imp_AcquireSRWLockExclusive
0x180003d48  cmp     cs:qword_1800122A0, 0
0x180003d50  jz      short loc_180003D68
0x180003d52  mov     ebx, cs:dword_18001225C
0x180003d58  lea     rcx, SRWLock; SRWLock
0x180003d5f  nop
0x180003d60  call    cs:__imp_ReleaseSRWLockExclusive
0x180003d66  jmp     short loc_180003DBE
0x180003d68  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180003d6f  mov     cs:qword_1800122A0, 0
0x180003d7a  test    rax, rax
0x180003d7d  jnz     short loc_180003D8B
0x180003d7f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180003d86  test    rax, rax
0x180003d89  jz      short loc_180003DA5
0x180003d8b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180003d92  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180003d99  lea     rcx, qword_1800122A0
0x180003da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003da5  cmp     cs:qword_1800122A0, 0
0x180003dad  lea     rcx, SRWLock; SRWLock
0x180003db4  jnz     short loc_180003DC6
0x180003db6  call    cs:__imp_ReleaseSRWLockExclusive
0x180003dbc  xor     ebx, ebx
0x180003dbe  mov     eax, ebx
0x180003dc0  add     rsp, 20h
0x180003dc4  pop     rbx
0x180003dc5  retn
0x180003dc6  mov     ebx, 1
0x180003dcb  nop
0x180003dcc  mov     cs:dword_18001225C, ebx
0x180003dd2  jmp     short loc_180003D60
```
