# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180012cc0`
- end: `0x180012d7d`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `18`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180013134`
- `0x180013214`
- `0x1800134dc`
- `0x18002022c`
- `0x1800203ac`
- `0x18002052c`
- `0x1800206ac`
- `0x180020880`
- `0x1800209f4`
- `0x180020b74`
- `0x180020c54`
- `0x180022bd8`
- `0x180022cb8`
- `0x18002e920`
- `0x18002ea00`
- `0x18003fc70`
- `0x18003fd50`
- `0x180047724`

## callees

- `0x180012cc0`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012d08`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012d5e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012d08`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012d5e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012cea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012cea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_180065F64;
  if ( !dword_180065F64 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180065FA8 )
      {
        v1 = dword_180065F64;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180065FA8 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180065FA8,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180065FA8 )
      {
        v1 = 1;
        dword_180065F64 = 1;
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
0x180012cc0  push    rbx
0x180012cc2  sub     rsp, 20h
0x180012cc6  mov     ebx, cs:dword_180065F64
0x180012ccc  nop
0x180012ccd  test    ebx, ebx
0x180012ccf  jnz     loc_180012D66
0x180012cd5  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180012cdb  test    eax, eax
0x180012cdd  jz      loc_180012D64
0x180012ce3  lea     rcx, SRWLock; SRWLock
0x180012cea  call    cs:__imp_AcquireSRWLockExclusive
0x180012cf0  cmp     cs:qword_180065FA8, 0
0x180012cf8  jz      short loc_180012D10
0x180012cfa  mov     ebx, cs:dword_180065F64
0x180012d00  nop
0x180012d01  lea     rcx, SRWLock; SRWLock
0x180012d08  call    cs:__imp_ReleaseSRWLockExclusive
0x180012d0e  jmp     short loc_180012D66
0x180012d10  mov     cs:qword_180065FA8, 0
0x180012d1b  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180012d22  test    rax, rax
0x180012d25  jnz     short loc_180012D33
0x180012d27  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180012d2e  test    rax, rax
0x180012d31  jz      short loc_180012D4D
0x180012d33  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180012d3a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180012d41  lea     rcx, qword_180065FA8
0x180012d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d4d  lea     rcx, SRWLock; SRWLock
0x180012d54  cmp     cs:qword_180065FA8, 0
0x180012d5c  jnz     short loc_180012D6E
0x180012d5e  call    cs:__imp_ReleaseSRWLockExclusive
0x180012d64  xor     ebx, ebx
0x180012d66  mov     eax, ebx
0x180012d68  add     rsp, 20h
0x180012d6c  pop     rbx
0x180012d6d  retn
0x180012d6e  nop
0x180012d6f  mov     ebx, 1
0x180012d74  mov     cs:dword_180065F64, ebx
0x180012d7a  jmp     short loc_180012D08
```
