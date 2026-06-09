# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x180031bc4`
- end: `0x180031c28`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180031330`

## callees

- `0x18000a780`
- `0x180031bc4`
- `0x180046010`

## string_xrefs

- `0x180031be8`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
__int64 __fastcall wil_details_RtlRegisterFeatureConfigurationChangeNotification(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 (*NtDllProcedureAddress)(void); // rax

  NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
  if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification )
    return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64))NtDllProcedureAddress)(a1, a2, 0, a4);
  NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlRegisterFeatureConfigurationChangeNotification");
  g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress;
  if ( NtDllProcedureAddress )
    return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64))NtDllProcedureAddress)(a1, a2, 0, a4);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x180031bc4  mov     [rsp+arg_0], rbx
0x180031bc9  mov     [rsp+arg_8], rsi
0x180031bce  push    rdi
0x180031bcf  sub     rsp, 30h
0x180031bd3  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180031bda  mov     rbx, r9
0x180031bdd  mov     rdi, rdx
0x180031be0  mov     rsi, rcx
0x180031be3  test    rax, rax
0x180031be6  jnz     short loc_180031C07
0x180031be8  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180031bef  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180031bf4  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180031bfb  test    rax, rax
0x180031bfe  jnz     short loc_180031C07
0x180031c00  mov     eax, 0C0000139h
0x180031c05  jmp     short loc_180031C18
0x180031c07  mov     r9, rbx
0x180031c0a  xor     r8d, r8d
0x180031c0d  mov     rdx, rdi
0x180031c10  mov     rcx, rsi
0x180031c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c18  mov     rbx, [rsp+38h+arg_0]
0x180031c1d  mov     rsi, [rsp+38h+arg_8]
0x180031c22  add     rsp, 30h
0x180031c26  pop     rdi
0x180031c27  retn
```
