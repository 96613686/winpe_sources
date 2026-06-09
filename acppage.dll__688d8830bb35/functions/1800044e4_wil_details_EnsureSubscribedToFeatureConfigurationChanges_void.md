# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1800044e4`
- end: `0x1800045a0`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `188`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005698`
- `0x180009128`

## callees

- `0x1800044e4`
- `0x180017010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000452c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180004582`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000452c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180004582`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000450e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000450e`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_18002048C;
  if ( !dword_18002048C )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1800204D0 )
      {
        v1 = dword_18002048C;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_1800204D0 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_1800204D0,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_1800204D0 )
      {
        v1 = 1;
        dword_18002048C = 1;
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
0x1800044e4  push    rbx
0x1800044e6  sub     rsp, 20h
0x1800044ea  mov     ebx, cs:dword_18002048C
0x1800044f0  nop
0x1800044f1  test    ebx, ebx
0x1800044f3  jnz     loc_18000458A
0x1800044f9  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800044ff  test    eax, eax
0x180004501  jz      loc_180004588
0x180004507  lea     rcx, SRWLock; SRWLock
0x18000450e  call    cs:__imp_AcquireSRWLockExclusive
0x180004514  cmp     cs:qword_1800204D0, 0
0x18000451c  jz      short loc_180004534
0x18000451e  mov     ebx, cs:dword_18002048C
0x180004524  lea     rcx, SRWLock; SRWLock
0x18000452b  nop
0x18000452c  call    cs:__imp_ReleaseSRWLockExclusive
0x180004532  jmp     short loc_18000458A
0x180004534  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000453b  mov     cs:qword_1800204D0, 0
0x180004546  test    rax, rax
0x180004549  jnz     short loc_180004557
0x18000454b  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180004552  test    rax, rax
0x180004555  jz      short loc_180004571
0x180004557  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000455e  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180004565  lea     rcx, qword_1800204D0
0x18000456c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004571  cmp     cs:qword_1800204D0, 0
0x180004579  lea     rcx, SRWLock; SRWLock
0x180004580  jnz     short loc_180004592
0x180004582  call    cs:__imp_ReleaseSRWLockExclusive
0x180004588  xor     ebx, ebx
0x18000458a  mov     eax, ebx
0x18000458c  add     rsp, 20h
0x180004590  pop     rbx
0x180004591  retn
0x180004592  mov     ebx, 1
0x180004597  nop
0x180004598  mov     cs:dword_18002048C, ebx
0x18000459e  jmp     short loc_18000452C
```
