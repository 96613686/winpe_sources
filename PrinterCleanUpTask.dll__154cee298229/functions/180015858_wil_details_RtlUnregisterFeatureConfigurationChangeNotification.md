# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x180015858`
- end: `0x180015893`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001174c`

## callees

- `0x1800057f0`
- `0x180015858`
- `0x180018010`

## string_xrefs

- `0x18001586d`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x180015858  push    rbx
0x18001585a  sub     rsp, 20h
0x18001585e  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x180015865  mov     rbx, rcx
0x180015868  test    rax, rax
0x18001586b  jnz     short loc_180015885
0x18001586d  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x180015874  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180015879  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180015880  test    rax, rax
0x180015883  jz      short loc_18001588D
0x180015885  mov     rcx, rbx
0x180015888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001588d  add     rsp, 20h
0x180015891  pop     rbx
0x180015892  retn
```
