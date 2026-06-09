# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x140013c4c`
- end: `0x140013c87`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000936c`

## callees

- `0x140006bd0`
- `0x140013c4c`
- `0x14001c010`

## string_xrefs

- `0x140013c61`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x140013c4c  push    rbx
0x140013c4e  sub     rsp, 20h
0x140013c52  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x140013c59  mov     rbx, rcx
0x140013c5c  test    rax, rax
0x140013c5f  jnz     short loc_140013C79
0x140013c61  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x140013c68  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140013c6d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x140013c74  test    rax, rax
0x140013c77  jz      short loc_140013C81
0x140013c79  mov     rcx, rbx
0x140013c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013c81  add     rsp, 20h
0x140013c85  pop     rbx
0x140013c86  retn
```
