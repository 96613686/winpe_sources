# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x18002b75c`
- end: `0x18002b797`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180028d1c`

## callees

- `0x180007aa0`
- `0x18002b75c`
- `0x180031010`

## string_xrefs

- `0x18002b771`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
__int64 (*__fastcall wil_details_RtlUnregisterFeatureConfigurationChangeNotification(__int64 a1))(void)
{
  __int64 (*result)(void); // rax

  result = (__int64 (*)(void))g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
  if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification )
    return (__int64 (*)(void))((__int64 (__fastcall *)(__int64))result)(a1);
  result = wil_details_GetNtDllProcedureAddress("RtlUnregisterFeatureConfigurationChangeNotification");
  g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (__int64)result;
  if ( result )
    return (__int64 (*)(void))((__int64 (__fastcall *)(__int64))result)(a1);
  return result;
}

```

## disassembly

```asm
0x18002b75c  push    rbx
0x18002b75e  sub     rsp, 20h
0x18002b762  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18002b769  mov     rbx, rcx
0x18002b76c  test    rax, rax
0x18002b76f  jnz     short loc_18002B789
0x18002b771  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18002b778  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002b77d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18002b784  test    rax, rax
0x18002b787  jz      short loc_18002B791
0x18002b789  mov     rcx, rbx
0x18002b78c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b791  add     rsp, 20h
0x18002b795  pop     rbx
0x18002b796  retn
```
