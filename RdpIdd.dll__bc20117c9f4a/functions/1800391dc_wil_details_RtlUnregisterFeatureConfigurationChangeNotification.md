# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x1800391dc`
- end: `0x180039218`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180036888`

## callees

- `0x18000c6dc`
- `0x1800391dc`
- `0x18003f010`

## string_xrefs

- `0x1800391f1`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x1800391dc  push    rbx
0x1800391de  sub     rsp, 20h
0x1800391e2  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x1800391e9  mov     rbx, rcx
0x1800391ec  test    rax, rax
0x1800391ef  jnz     short loc_180039209
0x1800391f1  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x1800391f8  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800391fd  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180039204  test    rax, rax
0x180039207  jz      short loc_180039211
0x180039209  mov     rcx, rbx
0x18003920c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039211  add     rsp, 20h
0x180039215  pop     rbx
0x180039216  retn
```
