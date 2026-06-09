# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x140004d18`
- end: `0x140004dd4`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `188`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140005824`
- `0x1400068c8`
- `0x14000c50c`
- `0x140013254`

## callees

- `0x140004d18`
- `0x140017010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x140004d60`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140004db6`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140004d60`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140004db6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140004d42`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140004d42`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_140020A44;
  if ( !dword_140020A44 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_140020A88 )
      {
        v1 = dword_140020A44;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_140020A88 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_140020A88,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_140020A88 )
      {
        v1 = 1;
        dword_140020A44 = 1;
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
0x140004d18  push    rbx
0x140004d1a  sub     rsp, 20h
0x140004d1e  mov     ebx, cs:dword_140020A44
0x140004d24  nop
0x140004d25  test    ebx, ebx
0x140004d27  jnz     loc_140004DBE
0x140004d2d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140004d33  test    eax, eax
0x140004d35  jz      loc_140004DBC
0x140004d3b  lea     rcx, SRWLock; SRWLock
0x140004d42  call    cs:__imp_AcquireSRWLockExclusive
0x140004d48  cmp     cs:qword_140020A88, 0
0x140004d50  jz      short loc_140004D68
0x140004d52  mov     ebx, cs:dword_140020A44
0x140004d58  lea     rcx, SRWLock; SRWLock
0x140004d5f  nop
0x140004d60  call    cs:__imp_ReleaseSRWLockExclusive
0x140004d66  jmp     short loc_140004DBE
0x140004d68  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x140004d6f  mov     cs:qword_140020A88, 0
0x140004d7a  test    rax, rax
0x140004d7d  jnz     short loc_140004D8B
0x140004d7f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x140004d86  test    rax, rax
0x140004d89  jz      short loc_140004DA5
0x140004d8b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140004d92  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x140004d99  lea     rcx, qword_140020A88
0x140004da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004da5  cmp     cs:qword_140020A88, 0
0x140004dad  lea     rcx, SRWLock; SRWLock
0x140004db4  jnz     short loc_140004DC6
0x140004db6  call    cs:__imp_ReleaseSRWLockExclusive
0x140004dbc  xor     ebx, ebx
0x140004dbe  mov     eax, ebx
0x140004dc0  add     rsp, 20h
0x140004dc4  pop     rbx
0x140004dc5  retn
0x140004dc6  mov     ebx, 1
0x140004dcb  nop
0x140004dcc  mov     cs:dword_140020A44, ebx
0x140004dd2  jmp     short loc_140004D60
```
