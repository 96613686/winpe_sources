# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x14000b758`
- end: `0x14000b793`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140006728`

## callees

- `0x140005fd0`
- `0x14000b758`
- `0x14002b010`

## string_xrefs

- `0x14000b76d`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x14000b758  push    rbx
0x14000b75a  sub     rsp, 20h
0x14000b75e  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x14000b765  mov     rbx, rcx
0x14000b768  test    rax, rax
0x14000b76b  jnz     short loc_14000B785
0x14000b76d  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x14000b774  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000b779  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x14000b780  test    rax, rax
0x14000b783  jz      short loc_14000B78D
0x14000b785  mov     rcx, rbx
0x14000b788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b78d  add     rsp, 20h
0x14000b791  pop     rbx
0x14000b792  retn
```
