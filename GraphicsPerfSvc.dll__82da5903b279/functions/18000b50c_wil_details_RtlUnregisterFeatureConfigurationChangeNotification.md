# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x18000b50c`
- end: `0x18000b547`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180005ce8`

## callees

- `0x18000adb0`
- `0x18000b50c`
- `0x180031010`

## string_xrefs

- `0x18000b521`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18000b50c  push    rbx
0x18000b50e  sub     rsp, 20h
0x18000b512  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000b519  mov     rbx, rcx
0x18000b51c  test    rax, rax
0x18000b51f  jnz     short loc_18000B539
0x18000b521  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000b528  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b52d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000b534  test    rax, rax
0x18000b537  jz      short loc_18000B541
0x18000b539  mov     rcx, rbx
0x18000b53c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b541  add     rsp, 20h
0x18000b545  pop     rbx
0x18000b546  retn
```
