# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x140009f8c`
- end: `0x140009fc7`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400028d0`

## callees

- `0x140009ba0`
- `0x140009f8c`
- `0x14000b010`

## string_xrefs

- `0x140009fa1`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x140009f8c  push    rbx
0x140009f8e  sub     rsp, 20h
0x140009f92  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x140009f99  mov     rbx, rcx
0x140009f9c  test    rax, rax
0x140009f9f  jnz     short loc_140009FB9
0x140009fa1  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x140009fa8  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140009fad  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x140009fb4  test    rax, rax
0x140009fb7  jz      short loc_140009FC1
0x140009fb9  mov     rcx, rbx
0x140009fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009fc1  add     rsp, 20h
0x140009fc5  pop     rbx
0x140009fc6  retn
```
