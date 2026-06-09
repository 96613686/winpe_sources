# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x18000d408`
- end: `0x18000d443`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a620`

## callees

- `0x180005cd0`
- `0x18000d408`
- `0x180026010`

## string_xrefs

- `0x18000d41d`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18000d408  push    rbx
0x18000d40a  sub     rsp, 20h
0x18000d40e  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000d415  mov     rbx, rcx
0x18000d418  test    rax, rax
0x18000d41b  jnz     short loc_18000D435
0x18000d41d  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000d424  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000d429  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000d430  test    rax, rax
0x18000d433  jz      short loc_18000D43D
0x18000d435  mov     rcx, rbx
0x18000d438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d43d  add     rsp, 20h
0x18000d441  pop     rbx
0x18000d442  retn
```
