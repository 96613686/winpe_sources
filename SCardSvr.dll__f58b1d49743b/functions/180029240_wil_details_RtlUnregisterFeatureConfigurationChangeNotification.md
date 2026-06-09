# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x180029240`
- end: `0x18002927b`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180016f88`

## callees

- `0x1800288a0`
- `0x180029240`
- `0x180037010`

## string_xrefs

- `0x180029255`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x180029240  push    rbx
0x180029242  sub     rsp, 20h
0x180029246  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18002924d  mov     rbx, rcx
0x180029250  test    rax, rax
0x180029253  jnz     short loc_18002926D
0x180029255  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18002925c  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180029261  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180029268  test    rax, rax
0x18002926b  jz      short loc_180029275
0x18002926d  mov     rcx, rbx
0x180029270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029275  add     rsp, 20h
0x180029279  pop     rbx
0x18002927a  retn
```
