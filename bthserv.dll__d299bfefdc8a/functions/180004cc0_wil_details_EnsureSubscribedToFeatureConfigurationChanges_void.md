# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180004cc0`
- end: `0x180004d7d`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `21`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005dd0`
- `0x18000ed5c`
- `0x18000ee3c`
- `0x18000efbc`
- `0x1800263f0`
- `0x1800264d0`
- `0x1800265b0`
- `0x180026690`
- `0x180026804`
- `0x180026978`
- `0x180026aec`
- `0x180026c60`
- `0x180026dd4`
- `0x180026f48`
- `0x180027028`
- `0x180027108`
- `0x1800271e8`
- `0x1800272c8`
- `0x1800273a8`
- `0x180027528`
- `0x180027608`

## callees

- `0x180004cc0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004d08`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004d5e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004d08`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004d5e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004cea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004cea`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_1800444DC;
  if ( !dword_1800444DC )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180044520 )
      {
        v1 = dword_1800444DC;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180044520 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180044520,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180044520 )
      {
        v1 = 1;
        dword_1800444DC = 1;
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
0x180004cc0  push    rbx
0x180004cc2  sub     rsp, 20h
0x180004cc6  mov     ebx, cs:dword_1800444DC
0x180004ccc  nop
0x180004ccd  test    ebx, ebx
0x180004ccf  jnz     loc_180004D66
0x180004cd5  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004cdb  test    eax, eax
0x180004cdd  jz      loc_180004D64
0x180004ce3  lea     rcx, SRWLock; SRWLock
0x180004cea  call    cs:__imp_AcquireSRWLockExclusive
0x180004cf0  cmp     cs:qword_180044520, 0
0x180004cf8  jz      short loc_180004D10
0x180004cfa  mov     ebx, cs:dword_1800444DC
0x180004d00  nop
0x180004d01  lea     rcx, SRWLock; SRWLock
0x180004d08  call    cs:__imp_ReleaseSRWLockExclusive
0x180004d0e  jmp     short loc_180004D66
0x180004d10  mov     cs:qword_180044520, 0
0x180004d1b  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180004d22  test    rax, rax
0x180004d25  jnz     short loc_180004D33
0x180004d27  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180004d2e  test    rax, rax
0x180004d31  jz      short loc_180004D4D
0x180004d33  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004d3a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180004d41  lea     rcx, qword_180044520
0x180004d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d4d  lea     rcx, SRWLock; SRWLock
0x180004d54  cmp     cs:qword_180044520, 0
0x180004d5c  jnz     short loc_180004D6E
0x180004d5e  call    cs:__imp_ReleaseSRWLockExclusive
0x180004d64  xor     ebx, ebx
0x180004d66  mov     eax, ebx
0x180004d68  add     rsp, 20h
0x180004d6c  pop     rbx
0x180004d6d  retn
0x180004d6e  nop
0x180004d6f  mov     ebx, 1
0x180004d74  mov     cs:dword_1800444DC, ebx
0x180004d7a  jmp     short loc_180004D08
```
