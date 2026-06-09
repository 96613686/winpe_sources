# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x140011e70`
- end: `0x140011eab`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400090b8`

## callees

- `0x140007e70`
- `0x140011e70`
- `0x140019010`

## string_xrefs

- `0x140011e85`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
FARPROC __fastcall wil_details_RtlUnregisterFeatureConfigurationChangeNotification(__int64 a1)
{
  FARPROC result; // rax

  result = (FARPROC)g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
  if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification )
    return (FARPROC)((__int64 (__fastcall *)(__int64))result)(a1);
  result = wil_details_GetNtDllProcedureAddress("RtlUnregisterFeatureConfigurationChangeNotification");
  g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(__int64))result)(a1);
  return result;
}

```

## disassembly

```asm
0x140011e70  push    rbx
0x140011e72  sub     rsp, 20h
0x140011e76  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x140011e7d  mov     rbx, rcx
0x140011e80  test    rax, rax
0x140011e83  jnz     short loc_140011E9D
0x140011e85  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x140011e8c  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140011e91  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x140011e98  test    rax, rax
0x140011e9b  jz      short loc_140011EA5
0x140011e9d  mov     rcx, rbx
0x140011ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011ea5  add     rsp, 20h
0x140011ea9  pop     rbx
0x140011eaa  retn
```
