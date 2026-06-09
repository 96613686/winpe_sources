# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x140012690`
- end: `0x1400126cc`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000949c`

## callees

- `0x1400081c8`
- `0x140012690`
- `0x14001a010`

## string_xrefs

- `0x1400126a5`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x140012690  push    rbx
0x140012692  sub     rsp, 20h
0x140012696  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x14001269d  mov     rbx, rcx
0x1400126a0  test    rax, rax
0x1400126a3  jnz     short loc_1400126BD
0x1400126a5  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x1400126ac  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1400126b1  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x1400126b8  test    rax, rax
0x1400126bb  jz      short loc_1400126C5
0x1400126bd  mov     rcx, rbx
0x1400126c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400126c5  add     rsp, 20h
0x1400126c9  pop     rbx
0x1400126ca  retn
```
