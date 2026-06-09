# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x140009dc8`
- end: `0x140009e85`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000b4cc`

## callees

- `0x140009dc8`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009df2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009df2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009e10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009e66`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009e10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009e66`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_14001B714;
  if ( !dword_14001B714 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_14001B758 )
      {
        v1 = dword_14001B714;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_14001B758 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_14001B758,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_14001B758 )
      {
        v1 = 1;
        dword_14001B714 = 1;
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
0x140009dc8  push    rbx
0x140009dca  sub     rsp, 20h
0x140009dce  mov     ebx, cs:dword_14001B714
0x140009dd4  nop
0x140009dd5  test    ebx, ebx
0x140009dd7  jnz     loc_140009E6E
0x140009ddd  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140009de3  test    eax, eax
0x140009de5  jz      loc_140009E6C
0x140009deb  lea     rcx, SRWLock; SRWLock
0x140009df2  call    cs:__imp_AcquireSRWLockExclusive
0x140009df8  cmp     cs:qword_14001B758, 0
0x140009e00  jz      short loc_140009E18
0x140009e02  mov     ebx, cs:dword_14001B714
0x140009e08  nop
0x140009e09  lea     rcx, SRWLock; SRWLock
0x140009e10  call    cs:__imp_ReleaseSRWLockExclusive
0x140009e16  jmp     short loc_140009E6E
0x140009e18  mov     cs:qword_14001B758, 0
0x140009e23  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x140009e2a  test    rax, rax
0x140009e2d  jnz     short loc_140009E3B
0x140009e2f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x140009e36  test    rax, rax
0x140009e39  jz      short loc_140009E55
0x140009e3b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140009e42  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x140009e49  lea     rcx, qword_14001B758
0x140009e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e55  lea     rcx, SRWLock; SRWLock
0x140009e5c  cmp     cs:qword_14001B758, 0
0x140009e64  jnz     short loc_140009E76
0x140009e66  call    cs:__imp_ReleaseSRWLockExclusive
0x140009e6c  xor     ebx, ebx
0x140009e6e  mov     eax, ebx
0x140009e70  add     rsp, 20h
0x140009e74  pop     rbx
0x140009e75  retn
0x140009e76  nop
0x140009e77  mov     ebx, 1
0x140009e7c  mov     cs:dword_14001B714, ebx
0x140009e82  jmp     short loc_140009E10
```
