# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180004a48`
- end: `0x180004b05`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `23`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005b54`
- `0x18000a6a0`
- `0x180012e80`
- `0x180012f60`
- `0x180013040`
- `0x180013120`
- `0x180013200`
- `0x180013380`
- `0x1800134f4`
- `0x180013668`
- `0x1800137dc`
- `0x180013950`
- `0x180013ac4`
- `0x180013c38`
- `0x180013d18`
- `0x180013df8`
- `0x180013ed8`
- `0x180013fb8`
- `0x180014098`
- `0x180014218`
- `0x1800142f8`
- `0x180018adc`
- `0x180023fdc`

## callees

- `0x180004a48`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004a90`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004ae6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004a90`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004ae6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004a72`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004a72`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_180033334;
  if ( !dword_180033334 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180033378 )
      {
        v1 = dword_180033334;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180033378 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180033378,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180033378 )
      {
        v1 = 1;
        dword_180033334 = 1;
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
0x180004a48  push    rbx
0x180004a4a  sub     rsp, 20h
0x180004a4e  mov     ebx, cs:dword_180033334
0x180004a54  nop
0x180004a55  test    ebx, ebx
0x180004a57  jnz     loc_180004AEE
0x180004a5d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004a63  test    eax, eax
0x180004a65  jz      loc_180004AEC
0x180004a6b  lea     rcx, SRWLock; SRWLock
0x180004a72  call    cs:__imp_AcquireSRWLockExclusive
0x180004a78  cmp     cs:qword_180033378, 0
0x180004a80  jz      short loc_180004A98
0x180004a82  mov     ebx, cs:dword_180033334
0x180004a88  nop
0x180004a89  lea     rcx, SRWLock; SRWLock
0x180004a90  call    cs:__imp_ReleaseSRWLockExclusive
0x180004a96  jmp     short loc_180004AEE
0x180004a98  mov     cs:qword_180033378, 0
0x180004aa3  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180004aaa  test    rax, rax
0x180004aad  jnz     short loc_180004ABB
0x180004aaf  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180004ab6  test    rax, rax
0x180004ab9  jz      short loc_180004AD5
0x180004abb  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004ac2  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180004ac9  lea     rcx, qword_180033378
0x180004ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ad5  lea     rcx, SRWLock; SRWLock
0x180004adc  cmp     cs:qword_180033378, 0
0x180004ae4  jnz     short loc_180004AF6
0x180004ae6  call    cs:__imp_ReleaseSRWLockExclusive
0x180004aec  xor     ebx, ebx
0x180004aee  mov     eax, ebx
0x180004af0  add     rsp, 20h
0x180004af4  pop     rbx
0x180004af5  retn
0x180004af6  nop
0x180004af7  mov     ebx, 1
0x180004afc  mov     cs:dword_180033334, ebx
0x180004b02  jmp     short loc_180004A90
```
