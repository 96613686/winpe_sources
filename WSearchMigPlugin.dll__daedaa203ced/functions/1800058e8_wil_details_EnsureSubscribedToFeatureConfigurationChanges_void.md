# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1800058e8`
- end: `0x1800059ae`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `198`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006a34`
- `0x18000e1cc`
- `0x18000e3a0`
- `0x18000e514`
- `0x18000e688`
- `0x18000e7fc`
- `0x18000e970`
- `0x18000eae4`
- `0x18000ebc4`
- `0x18000eca4`
- `0x18000ed84`
- `0x18000ee64`
- `0x18000ef44`

## callees

- `0x1800058e8`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000591b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000591b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005939`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000598f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005939`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000598f`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax

  v1 = dword_180025B54;
  if ( !dword_180025B54 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180025B98 )
      {
        v1 = dword_180025B54;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180025B98 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180025B98,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180025B98 )
      {
        v1 = 1;
        dword_180025B54 = 1;
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
0x1800058e8  push    rbx
0x1800058ea  sub     rsp, 30h
0x1800058ee  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800058f7  mov     ebx, cs:dword_180025B54
0x1800058fd  nop
0x1800058fe  test    ebx, ebx
0x180005900  jnz     loc_180005997
0x180005906  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000590c  test    eax, eax
0x18000590e  jz      loc_180005995
0x180005914  lea     rcx, SRWLock; SRWLock
0x18000591b  call    cs:__imp_AcquireSRWLockExclusive
0x180005921  cmp     cs:qword_180025B98, 0
0x180005929  jz      short loc_180005941
0x18000592b  mov     ebx, cs:dword_180025B54
0x180005931  nop
0x180005932  lea     rcx, SRWLock; SRWLock
0x180005939  call    cs:__imp_ReleaseSRWLockExclusive
0x18000593f  jmp     short loc_180005997
0x180005941  mov     cs:qword_180025B98, 0
0x18000594c  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180005953  test    rax, rax
0x180005956  jnz     short loc_180005964
0x180005958  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000595f  test    rax, rax
0x180005962  jz      short loc_18000597E
0x180005964  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000596b  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180005972  lea     rcx, qword_180025B98
0x180005979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000597e  lea     rcx, SRWLock; SRWLock
0x180005985  cmp     cs:qword_180025B98, 0
0x18000598d  jnz     short loc_18000599F
0x18000598f  call    cs:__imp_ReleaseSRWLockExclusive
0x180005995  xor     ebx, ebx
0x180005997  mov     eax, ebx
0x180005999  add     rsp, 30h
0x18000599d  pop     rbx
0x18000599e  retn
0x18000599f  nop
0x1800059a0  mov     ebx, 1
0x1800059a5  mov     cs:dword_180025B54, ebx
0x1800059ab  jmp     short loc_180005939
```
