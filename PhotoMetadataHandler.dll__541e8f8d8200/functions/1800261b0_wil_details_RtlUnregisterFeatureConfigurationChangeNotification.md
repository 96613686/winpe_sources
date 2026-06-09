# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x1800261b0`
- end: `0x1800261eb`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180013c6c`

## callees

- `0x180025e58`
- `0x1800261b0`
- `0x180028010`

## string_xrefs

- `0x1800261c5`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x1800261b0  push    rbx
0x1800261b2  sub     rsp, 20h
0x1800261b6  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x1800261bd  mov     rbx, rcx
0x1800261c0  test    rax, rax
0x1800261c3  jnz     short loc_1800261DD
0x1800261c5  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x1800261cc  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800261d1  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x1800261d8  test    rax, rax
0x1800261db  jz      short loc_1800261E5
0x1800261dd  mov     rcx, rbx
0x1800261e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261e5  add     rsp, 20h
0x1800261e9  pop     rbx
0x1800261ea  retn
```
