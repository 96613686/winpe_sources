# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x18000bdbc`
- end: `0x18000bdf7`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180003dd4`

## callees

- `0x18000b160`
- `0x18000bdbc`
- `0x180011010`

## string_xrefs

- `0x18000bdd1`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18000bdbc  push    rbx
0x18000bdbe  sub     rsp, 20h
0x18000bdc2  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000bdc9  mov     rbx, rcx
0x18000bdcc  test    rax, rax
0x18000bdcf  jnz     short loc_18000BDE9
0x18000bdd1  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000bdd8  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000bddd  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000bde4  test    rax, rax
0x18000bde7  jz      short loc_18000BDF1
0x18000bde9  mov     rcx, rbx
0x18000bdec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdf1  add     rsp, 20h
0x18000bdf5  pop     rbx
0x18000bdf6  retn
```
