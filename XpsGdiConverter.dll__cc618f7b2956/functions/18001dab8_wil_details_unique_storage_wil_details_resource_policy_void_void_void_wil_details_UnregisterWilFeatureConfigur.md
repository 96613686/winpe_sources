# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x18001dab8`
- end: `0x18001daf9`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001dbbc`

## callees

- `0x18000d180`
- `0x18001dab8`
- `0x18004a010`

## string_xrefs

- `0x18001dad2`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
        __int64 *a1)
{
  __int64 v1; // rbx
  __int64 (*NtDllProcedureAddress)(void); // rax

  v1 = *a1;
  if ( *a1 )
  {
    NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
    if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
      || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlUnregisterFeatureConfigurationChangeNotification"),
          (g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress) != 0) )
    {
      ((void (__fastcall *)(__int64))NtDllProcedureAddress)(v1);
    }
  }
}

```

## disassembly

```asm
0x18001dab8  push    rbx
0x18001daba  sub     rsp, 20h
0x18001dabe  mov     rbx, [rcx]
0x18001dac1  test    rbx, rbx
0x18001dac4  jz      short loc_18001DAF3
0x18001dac6  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18001dacd  test    rax, rax
0x18001dad0  jnz     short loc_18001DAEA
0x18001dad2  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18001dad9  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001dade  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18001dae5  test    rax, rax
0x18001dae8  jz      short loc_18001DAF3
0x18001daea  mov     rcx, rbx
0x18001daed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001daf2  nop
0x18001daf3  add     rsp, 20h
0x18001daf7  pop     rbx
0x18001daf8  retn
```
