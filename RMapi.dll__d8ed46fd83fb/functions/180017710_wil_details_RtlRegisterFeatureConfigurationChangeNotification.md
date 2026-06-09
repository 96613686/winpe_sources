# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x180017710`
- end: `0x18001776b`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001621c`

## callees

- `0x18000f050`
- `0x180017710`
- `0x180028010`

## string_xrefs

- `0x18001772c`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180017710  mov     [rsp+arg_0], rbx
0x180017715  push    rdi
0x180017716  sub     rsp, 30h
0x18001771a  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180017721  mov     rbx, r9
0x180017724  mov     rdi, rdx
0x180017727  test    rax, rax
0x18001772a  jnz     short loc_18001774B
0x18001772c  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180017733  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180017738  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001773f  test    rax, rax
0x180017742  jnz     short loc_18001774B
0x180017744  mov     eax, 0C0000139h
0x180017749  jmp     short loc_180017760
0x18001774b  mov     r9, rbx
0x18001774e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToStateChangesUnderLock@FeatureStateManager@details@wil@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@5@PEAX@Z@SA@1@Z; `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,void *)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x180017755  xor     r8d, r8d
0x180017758  mov     rdx, rdi
0x18001775b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017760  mov     rbx, [rsp+38h+arg_0]
0x180017765  add     rsp, 30h
0x180017769  pop     rdi
0x18001776a  retn
```
