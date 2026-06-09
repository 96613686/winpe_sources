# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x1800273fc`
- end: `0x180027438`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180014620`

## callees

- `0x180027098`
- `0x1800273fc`
- `0x180029010`

## string_xrefs

- `0x180027411`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x1800273fc  push    rbx
0x1800273fe  sub     rsp, 20h
0x180027402  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x180027409  mov     rbx, rcx
0x18002740c  test    rax, rax
0x18002740f  jnz     short loc_180027429
0x180027411  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x180027418  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002741d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180027424  test    rax, rax
0x180027427  jz      short loc_180027431
0x180027429  mov     rcx, rbx
0x18002742c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027431  add     rsp, 20h
0x180027435  pop     rbx
0x180027436  retn
```
