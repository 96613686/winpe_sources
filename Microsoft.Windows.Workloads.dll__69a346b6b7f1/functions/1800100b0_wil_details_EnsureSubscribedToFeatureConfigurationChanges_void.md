# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1800100b0`
- end: `0x180010191`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `225`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000e150`
- `0x18000eaa0`
- `0x18001a430`
- `0x18001a6a0`
- `0x18001a880`
- `0x18002a1b0`

## callees

- `0x180010030`
- `0x1800100b0`
- `0x18003bed0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800100f4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001017a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800100f4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001017a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800100d7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800100d7`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  __int64 result; // rax
  unsigned int v2; // ebx
  _QWORD *v3; // rax

  result = (unsigned int)dword_1800583FC;
  if ( !dword_1800583FC )
  {
    if ( !wil::details::g_enabledStateManager )
      return 0;
    AcquireSRWLockExclusive(&SRWLock);
    if ( qword_180058400 )
    {
      v2 = dword_1800583FC;
    }
    else
    {
      v3 = (_QWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,void (*)(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),&void wil::details::WilApi_UnsubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),wistd::integral_constant<unsigned __int64,0>,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,0,std::nullptr_t>>>::operator&(&qword_180058400);
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
      if ( qword_180058400 )
      {
        dword_1800583FC = 1;
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
0x1800100b0  push    rbx
0x1800100b2  sub     rsp, 20h
0x1800100b6  mov     eax, cs:dword_1800583FC
0x1800100bc  test    eax, eax
0x1800100be  jnz     loc_18001018B
0x1800100c4  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, al; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800100ca  jz      loc_180010187
0x1800100d0  lea     rcx, SRWLock; SRWLock
0x1800100d7  call    cs:__imp_AcquireSRWLockExclusive
0x1800100dd  cmp     cs:qword_180058400, 0
0x1800100e5  jz      short loc_1800100FF
0x1800100e7  mov     ebx, cs:dword_1800583FC
0x1800100ed  lea     rcx, SRWLock; SRWLock
0x1800100f4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800100fa  jmp     loc_180010189
0x1800100ff  lea     rcx, qword_180058400
0x180010106  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAU1@@Z$1?WilApi_UnsubscribeFeatureStateChangeNotification@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,void (*)(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),&wil::details::WilApi_UnsubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),wistd::integral_constant<unsigned __int64,0>,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,0,std::nullptr_t>>>::operator&(void)
0x18001010b  xor     ebx, ebx
0x18001010d  mov     r9, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180010114  test    r9, r9
0x180010117  jz      short loc_180010135
0x180010119  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180010120  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180010127  mov     rcx, rax
0x18001012a  mov     rax, r9
0x18001012d  call    cs:__guard_dispatch_icall_fptr
0x180010133  jmp     short loc_180010160
0x180010135  mov     r9, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18001013c  test    r9, r9
0x18001013f  jz      short loc_18001015D
0x180010141  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180010148  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18001014f  mov     rcx, rax
0x180010152  mov     rax, r9
0x180010155  call    cs:__guard_dispatch_icall_fptr
0x18001015b  jmp     short loc_180010160
0x18001015d  mov     [rax], rbx
0x180010160  lea     rcx, SRWLock; SRWLock
0x180010167  cmp     cs:qword_180058400, rbx
0x18001016e  jz      short loc_1800100F4
0x180010170  mov     cs:dword_1800583FC, 1
0x18001017a  call    cs:__imp_ReleaseSRWLockExclusive
0x180010180  mov     ebx, 1
0x180010185  jmp     short loc_180010189
0x180010187  xor     ebx, ebx
0x180010189  mov     eax, ebx
0x18001018b  add     rsp, 20h
0x18001018f  pop     rbx
0x180010190  retn
```
