# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x14000d7d8`
- end: `0x14000d813`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000a0c8`

## callees

- `0x140005ed0`
- `0x14000d7d8`
- `0x14002b010`

## string_xrefs

- `0x14000d7ed`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x14000d7d8  push    rbx
0x14000d7da  sub     rsp, 20h
0x14000d7de  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x14000d7e5  mov     rbx, rcx
0x14000d7e8  test    rax, rax
0x14000d7eb  jnz     short loc_14000D805
0x14000d7ed  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x14000d7f4  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000d7f9  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x14000d800  test    rax, rax
0x14000d803  jz      short loc_14000D80D
0x14000d805  mov     rcx, rbx
0x14000d808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d80d  add     rsp, 20h
0x14000d811  pop     rbx
0x14000d812  retn
```
