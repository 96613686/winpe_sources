# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x180031c30`
- end: `0x180031c6b`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18002e2f4`

## callees

- `0x18000a780`
- `0x180031c30`
- `0x180046010`

## string_xrefs

- `0x180031c45`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x180031c30  push    rbx
0x180031c32  sub     rsp, 20h
0x180031c36  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x180031c3d  mov     rbx, rcx
0x180031c40  test    rax, rax
0x180031c43  jnz     short loc_180031C5D
0x180031c45  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x180031c4c  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180031c51  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180031c58  test    rax, rax
0x180031c5b  jz      short loc_180031C65
0x180031c5d  mov     rcx, rbx
0x180031c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c65  add     rsp, 20h
0x180031c69  pop     rbx
0x180031c6a  retn
```
