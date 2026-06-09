# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180005498`
- end: `0x180005555`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `17`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006594`
- `0x18000a550`
- `0x18000a714`
- `0x18000a8e8`
- `0x18000b648`
- `0x18000d10c`
- `0x18000ff68`
- `0x18001013c`
- `0x180010310`
- `0x1800104e4`
- `0x1800106b8`
- `0x180013830`
- `0x180013a04`
- `0x180013bd8`
- `0x180013cb8`
- `0x180013e8c`
- `0x180014060`

## callees

- `0x180005498`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800054c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800054c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800054e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005536`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800054e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005536`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_180023434;
  if ( !dword_180023434 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180023478 )
      {
        v1 = dword_180023434;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180023478 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180023478,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180023478 )
      {
        v1 = 1;
        dword_180023434 = 1;
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
0x180005498  push    rbx
0x18000549a  sub     rsp, 20h
0x18000549e  mov     ebx, cs:dword_180023434
0x1800054a4  nop
0x1800054a5  test    ebx, ebx
0x1800054a7  jnz     loc_18000553E
0x1800054ad  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800054b3  test    eax, eax
0x1800054b5  jz      loc_18000553C
0x1800054bb  lea     rcx, SRWLock; SRWLock
0x1800054c2  call    cs:__imp_AcquireSRWLockExclusive
0x1800054c8  cmp     cs:qword_180023478, 0
0x1800054d0  jz      short loc_1800054E8
0x1800054d2  mov     ebx, cs:dword_180023434
0x1800054d8  nop
0x1800054d9  lea     rcx, SRWLock; SRWLock
0x1800054e0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800054e6  jmp     short loc_18000553E
0x1800054e8  mov     cs:qword_180023478, 0
0x1800054f3  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800054fa  test    rax, rax
0x1800054fd  jnz     short loc_18000550B
0x1800054ff  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180005506  test    rax, rax
0x180005509  jz      short loc_180005525
0x18000550b  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005512  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180005519  lea     rcx, qword_180023478
0x180005520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005525  lea     rcx, SRWLock; SRWLock
0x18000552c  cmp     cs:qword_180023478, 0
0x180005534  jnz     short loc_180005546
0x180005536  call    cs:__imp_ReleaseSRWLockExclusive
0x18000553c  xor     ebx, ebx
0x18000553e  mov     eax, ebx
0x180005540  add     rsp, 20h
0x180005544  pop     rbx
0x180005545  retn
0x180005546  nop
0x180005547  mov     ebx, 1
0x18000554c  mov     cs:dword_180023434, ebx
0x180005552  jmp     short loc_1800054E0
```
