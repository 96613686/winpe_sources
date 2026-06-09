# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x18000f37c`
- end: `0x18000f3b7`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180007504`

## callees

- `0x18000eb20`
- `0x18000f37c`
- `0x18002b010`

## string_xrefs

- `0x18000f391`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18000f37c  push    rbx
0x18000f37e  sub     rsp, 20h
0x18000f382  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000f389  mov     rbx, rcx
0x18000f38c  test    rax, rax
0x18000f38f  jnz     short loc_18000F3A9
0x18000f391  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000f398  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000f39d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000f3a4  test    rax, rax
0x18000f3a7  jz      short loc_18000F3B1
0x18000f3a9  mov     rcx, rbx
0x18000f3ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3b1  add     rsp, 20h
0x18000f3b5  pop     rbx
0x18000f3b6  retn
```
