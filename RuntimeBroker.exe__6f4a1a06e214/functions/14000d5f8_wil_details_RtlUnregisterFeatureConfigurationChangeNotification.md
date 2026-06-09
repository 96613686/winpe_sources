# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x14000d5f8`
- end: `0x14000d633`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400084f0`

## callees

- `0x14000cf28`
- `0x14000d5f8`
- `0x140010010`

## string_xrefs

- `0x14000d60d`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x14000d5f8  push    rbx
0x14000d5fa  sub     rsp, 20h
0x14000d5fe  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x14000d605  mov     rbx, rcx
0x14000d608  test    rax, rax
0x14000d60b  jnz     short loc_14000D625
0x14000d60d  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x14000d614  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000d619  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x14000d620  test    rax, rax
0x14000d623  jz      short loc_14000D62D
0x14000d625  mov     rcx, rbx
0x14000d628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d62d  add     rsp, 20h
0x14000d631  pop     rbx
0x14000d632  retn
```
