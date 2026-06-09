# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x140012224`
- end: `0x14001227f`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000ece0`

## callees

- `0x1400066b0`
- `0x140012224`
- `0x14002a010`

## string_xrefs

- `0x140012240`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
__int64 __fastcall wil_details_RtlRegisterFeatureConfigurationChangeNotification(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 (*NtDllProcedureAddress)(void); // rax

  NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
  if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification )
    return ((__int64 (__fastcall *)(__int64 (__fastcall *)(), __int64, _QWORD, __int64))NtDllProcedureAddress)(
             `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
             a2,
             0,
             a4);
  NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlRegisterFeatureConfigurationChangeNotification");
  g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress;
  if ( NtDllProcedureAddress )
    return ((__int64 (__fastcall *)(__int64 (__fastcall *)(), __int64, _QWORD, __int64))NtDllProcedureAddress)(
             `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
             a2,
             0,
             a4);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x140012224  mov     [rsp+arg_0], rbx
0x140012229  push    rdi
0x14001222a  sub     rsp, 30h
0x14001222e  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140012235  mov     rbx, r9
0x140012238  mov     rdi, rdx
0x14001223b  test    rax, rax
0x14001223e  jnz     short loc_14001225F
0x140012240  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x140012247  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14001224c  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x140012253  test    rax, rax
0x140012256  jnz     short loc_14001225F
0x140012258  mov     eax, 0C0000139h
0x14001225d  jmp     short loc_140012274
0x14001225f  mov     r9, rbx
0x140012262  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToStateChangesUnderLock@FeatureStateManager@details@wil@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@5@PEAX@Z@SA@1@Z; `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,void *)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x140012269  xor     r8d, r8d
0x14001226c  mov     rdx, rdi
0x14001226f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012274  mov     rbx, [rsp+38h+arg_0]
0x140012279  add     rsp, 30h
0x14001227d  pop     rdi
0x14001227e  retn
```
