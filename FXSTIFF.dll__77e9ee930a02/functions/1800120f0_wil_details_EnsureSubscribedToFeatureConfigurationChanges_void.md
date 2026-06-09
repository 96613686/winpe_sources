# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1800120f0`
- end: `0x1800121c3`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `211`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800120f0`
- `0x180019010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001213e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001219a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001213e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001219a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001211a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001211a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_1800712A4;
  if ( !dword_1800712A4 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1800712A8 )
      {
        v1 = dword_1800712A4;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_1800712A8 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_1800712A8,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_1800712A8 )
      {
        v1 = 1;
        dword_1800712A4 = 1;
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
0x1800120f0  push    rbx
0x1800120f2  sub     rsp, 20h
0x1800120f6  mov     ebx, cs:dword_1800712A4
0x1800120fc  nop
0x1800120fd  test    ebx, ebx
0x1800120ff  jnz     loc_1800121A8
0x180012105  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001210b  test    eax, eax
0x18001210d  jz      loc_1800121A6
0x180012113  lea     rcx, SRWLock; SRWLock
0x18001211a  call    cs:__imp_AcquireSRWLockExclusive
0x180012121  nop     dword ptr [rax+rax+00h]
0x180012126  cmp     cs:qword_1800712A8, 0
0x18001212e  jz      short loc_18001214C
0x180012130  mov     ebx, cs:dword_1800712A4
0x180012136  nop
0x180012137  lea     rcx, SRWLock; SRWLock
0x18001213e  call    cs:__imp_ReleaseSRWLockExclusive
0x180012145  nop     dword ptr [rax+rax+00h]
0x18001214a  jmp     short loc_1800121A8
0x18001214c  mov     cs:qword_1800712A8, 0
0x180012157  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18001215e  test    rax, rax
0x180012161  jnz     short loc_18001216F
0x180012163  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18001216a  test    rax, rax
0x18001216d  jz      short loc_180012189
0x18001216f  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180012176  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18001217d  lea     rcx, qword_1800712A8
0x180012184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012189  lea     rcx, SRWLock; SRWLock
0x180012190  cmp     cs:qword_1800712A8, 0
0x180012198  jnz     short loc_1800121B1
0x18001219a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800121a1  nop     dword ptr [rax+rax+00h]
0x1800121a6  xor     ebx, ebx
0x1800121a8  mov     eax, ebx
0x1800121aa  add     rsp, 20h
0x1800121ae  pop     rbx
0x1800121af  retn
0x1800121b1  nop
0x1800121b2  mov     ebx, 1
0x1800121b7  mov     cs:dword_1800712A4, ebx
0x1800121bd  jmp     loc_18001213E
```
