# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x18000b5fc`
- end: `0x18000b63d`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `65`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b4d0`

## callees

- `0x18000b5fc`
- `0x18000dc44`
- `0x18001b010`

## string_xrefs

- `0x18000b616`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18000b5fc  push    rbx
0x18000b5fe  sub     rsp, 20h
0x18000b602  mov     rbx, [rcx]
0x18000b605  test    rbx, rbx
0x18000b608  jz      short loc_18000B637
0x18000b60a  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000b611  test    rax, rax
0x18000b614  jnz     short loc_18000B62E
0x18000b616  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000b61d  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b622  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000b629  test    rax, rax
0x18000b62c  jz      short loc_18000B637
0x18000b62e  mov     rcx, rbx
0x18000b631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b636  nop
0x18000b637  add     rsp, 20h
0x18000b63b  pop     rbx
0x18000b63c  retn
```
