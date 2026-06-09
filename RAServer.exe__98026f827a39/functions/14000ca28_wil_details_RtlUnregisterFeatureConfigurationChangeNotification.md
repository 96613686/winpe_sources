# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x14000ca28`
- end: `0x14000ca63`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140003978`

## callees

- `0x14000c630`
- `0x14000ca28`
- `0x140017010`

## string_xrefs

- `0x14000ca3d`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x14000ca28  push    rbx
0x14000ca2a  sub     rsp, 20h
0x14000ca2e  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x14000ca35  mov     rbx, rcx
0x14000ca38  test    rax, rax
0x14000ca3b  jnz     short loc_14000CA55
0x14000ca3d  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x14000ca44  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000ca49  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x14000ca50  test    rax, rax
0x14000ca53  jz      short loc_14000CA5D
0x14000ca55  mov     rcx, rbx
0x14000ca58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ca5d  add     rsp, 20h
0x14000ca61  pop     rbx
0x14000ca62  retn
```
