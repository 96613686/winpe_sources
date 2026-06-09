# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180004880`
- end: `0x180004961`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `225`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000b3a0`

## callees

- `0x180004880`
- `0x180008eb0`
- `0x18001cdf0`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1800048a7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800048a7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800048c4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000494a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800048c4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000494a`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  __int64 result; // rax
  unsigned int v2; // ebx
  _QWORD *v3; // rax

  result = (unsigned int)dword_18002D33C;
  if ( !dword_18002D33C )
  {
    if ( !wil::details::g_enabledStateManager )
      return 0;
    AcquireSRWLockExclusive(&SRWLock);
    if ( qword_18002D340 )
    {
      v2 = dword_18002D33C;
    }
    else
    {
      v3 = (_QWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,void (*)(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),&void wil::details::WilApi_UnsubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),wistd::integral_constant<unsigned __int64,0>,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,0,std::nullptr_t>>>::operator&(&qword_18002D340);
      v2 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification )
      {
        ((void (__fastcall *)(_QWORD *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification)(
          v3,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      else if ( g_wil_details_apiSubscribeFeatureStateChangeNotification )
      {
        ((void (__fastcall *)(_QWORD *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification)(
          v3,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      else
      {
        *v3 = 0;
      }
      if ( qword_18002D340 )
      {
        dword_18002D33C = 1;
        ReleaseSRWLockExclusive(&SRWLock);
        return 1;
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x180004880  push    rbx
0x180004882  sub     rsp, 20h
0x180004886  mov     eax, cs:dword_18002D33C
0x18000488c  test    eax, eax
0x18000488e  jnz     loc_18000495B
0x180004894  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, al; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000489a  jz      loc_180004957
0x1800048a0  lea     rcx, SRWLock; SRWLock
0x1800048a7  call    cs:__imp_AcquireSRWLockExclusive
0x1800048ad  cmp     cs:qword_18002D340, 0
0x1800048b5  jz      short loc_1800048CF
0x1800048b7  mov     ebx, cs:dword_18002D33C
0x1800048bd  lea     rcx, SRWLock; SRWLock
0x1800048c4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800048ca  jmp     loc_180004959
0x1800048cf  lea     rcx, qword_18002D340
0x1800048d6  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAU1@@Z$1?WilApi_UnsubscribeFeatureStateChangeNotification@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,void (*)(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),&wil::details::WilApi_UnsubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),wistd::integral_constant<unsigned __int64,0>,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,0,std::nullptr_t>>>::operator&(void)
0x1800048db  xor     ebx, ebx
0x1800048dd  mov     r9, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800048e4  test    r9, r9
0x1800048e7  jz      short loc_180004905
0x1800048e9  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800048f0  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x1800048f7  mov     rcx, rax
0x1800048fa  mov     rax, r9
0x1800048fd  call    cs:__guard_dispatch_icall_fptr
0x180004903  jmp     short loc_180004930
0x180004905  mov     r9, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000490c  test    r9, r9
0x18000490f  jz      short loc_18000492D
0x180004911  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004918  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18000491f  mov     rcx, rax
0x180004922  mov     rax, r9
0x180004925  call    cs:__guard_dispatch_icall_fptr
0x18000492b  jmp     short loc_180004930
0x18000492d  mov     [rax], rbx
0x180004930  lea     rcx, SRWLock; SRWLock
0x180004937  cmp     cs:qword_18002D340, rbx
0x18000493e  jz      short loc_1800048C4
0x180004940  mov     cs:dword_18002D33C, 1
0x18000494a  call    cs:__imp_ReleaseSRWLockExclusive
0x180004950  mov     ebx, 1
0x180004955  jmp     short loc_180004959
0x180004957  xor     ebx, ebx
0x180004959  mov     eax, ebx
0x18000495b  add     rsp, 20h
0x18000495f  pop     rbx
0x180004960  retn
```
