# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x18000d168`
- end: `0x18000d1a3`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000936c`

## callees

- `0x18000cdec`
- `0x18000d168`
- `0x18000e010`

## string_xrefs

- `0x18000d17d`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18000d168  push    rbx
0x18000d16a  sub     rsp, 20h
0x18000d16e  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000d175  mov     rbx, rcx
0x18000d178  test    rax, rax
0x18000d17b  jnz     short loc_18000D195
0x18000d17d  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000d184  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000d189  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000d190  test    rax, rax
0x18000d193  jz      short loc_18000D19D
0x18000d195  mov     rcx, rbx
0x18000d198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d19d  add     rsp, 20h
0x18000d1a1  pop     rbx
0x18000d1a2  retn
```
