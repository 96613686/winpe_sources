# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000bf40`
- end: `0x18000bfa4`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ab98`

## callees

- `0x180007920`
- `0x18000bf40`
- `0x180018010`

## string_xrefs

- `0x18000bf64`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000bf40  mov     [rsp+arg_0], rbx
0x18000bf45  mov     [rsp+arg_8], rsi
0x18000bf4a  push    rdi
0x18000bf4b  sub     rsp, 30h
0x18000bf4f  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000bf56  mov     rbx, r9
0x18000bf59  mov     rdi, rdx
0x18000bf5c  mov     rsi, rcx
0x18000bf5f  test    rax, rax
0x18000bf62  jnz     short loc_18000BF83
0x18000bf64  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000bf6b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000bf70  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000bf77  test    rax, rax
0x18000bf7a  jnz     short loc_18000BF83
0x18000bf7c  mov     eax, 0C0000139h
0x18000bf81  jmp     short loc_18000BF94
0x18000bf83  mov     r9, rbx
0x18000bf86  xor     r8d, r8d
0x18000bf89  mov     rdx, rdi
0x18000bf8c  mov     rcx, rsi
0x18000bf8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf94  mov     rbx, [rsp+38h+arg_0]
0x18000bf99  mov     rsi, [rsp+38h+arg_8]
0x18000bf9e  add     rsp, 30h
0x18000bfa2  pop     rdi
0x18000bfa3  retn
```
