# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x14001cf18`
- end: `0x14001cf53`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400091d4`

## callees

- `0x14001bce4`
- `0x14001cf18`
- `0x14001f010`

## string_xrefs

- `0x14001cf2d`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x14001cf18  push    rbx
0x14001cf1a  sub     rsp, 20h
0x14001cf1e  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x14001cf25  mov     rbx, rcx
0x14001cf28  test    rax, rax
0x14001cf2b  jnz     short loc_14001CF45
0x14001cf2d  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x14001cf34  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14001cf39  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x14001cf40  test    rax, rax
0x14001cf43  jz      short loc_14001CF4D
0x14001cf45  mov     rcx, rbx
0x14001cf48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cf4d  add     rsp, 20h
0x14001cf51  pop     rbx
0x14001cf52  retn
```
