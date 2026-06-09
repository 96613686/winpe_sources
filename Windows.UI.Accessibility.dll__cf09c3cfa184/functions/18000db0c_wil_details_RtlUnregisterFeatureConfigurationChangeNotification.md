# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x18000db0c`
- end: `0x18000db47`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180009004`

## callees

- `0x18000d438`
- `0x18000db0c`
- `0x180035010`

## string_xrefs

- `0x18000db21`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18000db0c  push    rbx
0x18000db0e  sub     rsp, 20h
0x18000db12  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000db19  mov     rbx, rcx
0x18000db1c  test    rax, rax
0x18000db1f  jnz     short loc_18000DB39
0x18000db21  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000db28  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000db2d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000db34  test    rax, rax
0x18000db37  jz      short loc_18000DB41
0x18000db39  mov     rcx, rbx
0x18000db3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db41  add     rsp, 20h
0x18000db45  pop     rbx
0x18000db46  retn
```
