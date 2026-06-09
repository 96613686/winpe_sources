# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180005a94`
- end: `0x180005b62`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `206`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800074dc`

## callees

- `0x180005a94`
- `0x180011010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005add`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005b34`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005b58`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005add`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005b34`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005b58`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180005abe`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180005abe`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_1800173AC;
  if ( !dword_1800173AC )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1800173F0 )
      {
        v1 = dword_1800173AC;
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_1800173F0 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_1800173F0,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_1800173F0 )
      {
        v1 = 1;
        dword_1800173AC = 1;
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
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
0x180005a94  push    rbx
0x180005a96  sub     rsp, 20h
0x180005a9a  mov     ebx, cs:dword_1800173AC
0x180005aa0  nop
0x180005aa1  test    ebx, ebx
0x180005aa3  jnz     loc_180005B3D
0x180005aa9  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005aaf  test    eax, eax
0x180005ab1  jz      loc_180005B3B
0x180005ab7  lea     rcx, SRWLock; SRWLock
0x180005abe  call    cs:__imp_AcquireSRWLockExclusive
0x180005ac4  nop
0x180005ac5  cmp     cs:qword_1800173F0, 0
0x180005acd  jz      short loc_180005AE6
0x180005acf  mov     ebx, cs:dword_1800173AC
0x180005ad5  nop
0x180005ad6  lea     rcx, SRWLock; SRWLock
0x180005add  call    cs:__imp_ReleaseSRWLockExclusive
0x180005ae3  nop
0x180005ae4  jmp     short loc_180005B3D
0x180005ae6  mov     cs:qword_1800173F0, 0
0x180005af1  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180005af8  test    rax, rax
0x180005afb  jnz     short loc_180005B09
0x180005afd  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180005b04  test    rax, rax
0x180005b07  jz      short loc_180005B23
0x180005b09  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005b10  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180005b17  lea     rcx, qword_1800173F0
0x180005b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b23  cmp     cs:qword_1800173F0, 0
0x180005b2b  jnz     short loc_180005B45
0x180005b2d  lea     rcx, SRWLock; SRWLock
0x180005b34  call    cs:__imp_ReleaseSRWLockExclusive
0x180005b3a  nop
0x180005b3b  xor     ebx, ebx
0x180005b3d  mov     eax, ebx
0x180005b3f  add     rsp, 20h
0x180005b43  pop     rbx
0x180005b44  retn
0x180005b45  nop
0x180005b46  mov     ebx, 1
0x180005b4b  mov     cs:dword_1800173AC, ebx
0x180005b51  lea     rcx, SRWLock; SRWLock
0x180005b58  call    cs:__imp_ReleaseSRWLockExclusive
0x180005b5e  nop
0x180005b5f  jmp     short loc_180005B3D
```
