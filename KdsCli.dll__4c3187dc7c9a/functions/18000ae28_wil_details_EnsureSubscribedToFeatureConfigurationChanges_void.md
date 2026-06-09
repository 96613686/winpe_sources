# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000ae28`
- end: `0x18000aee4`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `188`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b594`
- `0x180013d70`

## callees

- `0x18000ae28`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ae52`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ae52`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ae70`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000aec6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ae70`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000aec6`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_18002321C;
  if ( !dword_18002321C )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180023208);
      if ( qword_180023260 )
      {
        v1 = dword_18002321C;
LABEL_5:
        ReleaseSRWLockExclusive(&stru_180023208);
        return v1;
      }
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_180023260 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180023260,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180023260 )
      {
        v1 = 1;
        dword_18002321C = 1;
        goto LABEL_5;
      }
      ReleaseSRWLockExclusive(&stru_180023208);
    }
    return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x18000ae28  push    rbx
0x18000ae2a  sub     rsp, 20h
0x18000ae2e  mov     ebx, cs:dword_18002321C
0x18000ae34  nop
0x18000ae35  test    ebx, ebx
0x18000ae37  jnz     loc_18000AECE
0x18000ae3d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000ae43  test    eax, eax
0x18000ae45  jz      loc_18000AECC
0x18000ae4b  lea     rcx, stru_180023208; SRWLock
0x18000ae52  call    cs:__imp_AcquireSRWLockExclusive
0x18000ae58  cmp     cs:qword_180023260, 0
0x18000ae60  jz      short loc_18000AE78
0x18000ae62  mov     ebx, cs:dword_18002321C
0x18000ae68  lea     rcx, stru_180023208; SRWLock
0x18000ae6f  nop
0x18000ae70  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ae76  jmp     short loc_18000AECE
0x18000ae78  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000ae7f  mov     cs:qword_180023260, 0
0x18000ae8a  test    rax, rax
0x18000ae8d  jnz     short loc_18000AE9B
0x18000ae8f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000ae96  test    rax, rax
0x18000ae99  jz      short loc_18000AEB5
0x18000ae9b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000aea2  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18000aea9  lea     rcx, qword_180023260
0x18000aeb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeb5  cmp     cs:qword_180023260, 0
0x18000aebd  lea     rcx, stru_180023208; SRWLock
0x18000aec4  jnz     short loc_18000AED6
0x18000aec6  call    cs:__imp_ReleaseSRWLockExclusive
0x18000aecc  xor     ebx, ebx
0x18000aece  mov     eax, ebx
0x18000aed0  add     rsp, 20h
0x18000aed4  pop     rbx
0x18000aed5  retn
0x18000aed6  mov     ebx, 1
0x18000aedb  nop
0x18000aedc  mov     cs:dword_18002321C, ebx
0x18000aee2  jmp     short loc_18000AE70
```
