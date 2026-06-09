# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x1800212ec`
- end: `0x180021327`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180011504`

## callees

- `0x1800092d0`
- `0x1800212ec`
- `0x180025010`

## string_xrefs

- `0x180021301`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x1800212ec  push    rbx
0x1800212ee  sub     rsp, 20h
0x1800212f2  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x1800212f9  mov     rbx, rcx
0x1800212fc  test    rax, rax
0x1800212ff  jnz     short loc_180021319
0x180021301  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x180021308  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002130d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180021314  test    rax, rax
0x180021317  jz      short loc_180021321
0x180021319  mov     rcx, rbx
0x18002131c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021321  add     rsp, 20h
0x180021325  pop     rbx
0x180021326  retn
```
