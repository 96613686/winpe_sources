# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x180012980`
- end: `0x1800129bc`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180007698`

## callees

- `0x180005940`
- `0x180012980`
- `0x18001e010`

## string_xrefs

- `0x180012995`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x180012980  push    rbx
0x180012982  sub     rsp, 20h
0x180012986  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18001298d  mov     rbx, rcx
0x180012990  test    rax, rax
0x180012993  jnz     short loc_1800129AD
0x180012995  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18001299c  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800129a1  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x1800129a8  test    rax, rax
0x1800129ab  jz      short loc_1800129B5
0x1800129ad  mov     rcx, rbx
0x1800129b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129b5  add     rsp, 20h
0x1800129b9  pop     rbx
0x1800129ba  retn
```
