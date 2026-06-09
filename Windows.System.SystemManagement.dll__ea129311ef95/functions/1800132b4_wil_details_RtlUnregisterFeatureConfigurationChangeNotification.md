# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x1800132b4`
- end: `0x1800132ef`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001061c`

## callees

- `0x180009b20`
- `0x1800132b4`
- `0x18002b010`

## string_xrefs

- `0x1800132c9`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x1800132b4  push    rbx
0x1800132b6  sub     rsp, 20h
0x1800132ba  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x1800132c1  mov     rbx, rcx
0x1800132c4  test    rax, rax
0x1800132c7  jnz     short loc_1800132E1
0x1800132c9  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x1800132d0  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800132d5  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x1800132dc  test    rax, rax
0x1800132df  jz      short loc_1800132E9
0x1800132e1  mov     rcx, rbx
0x1800132e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132e9  add     rsp, 20h
0x1800132ed  pop     rbx
0x1800132ee  retn
```
