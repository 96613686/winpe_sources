# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x140011e04`
- end: `0x140011e68`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140010f40`

## callees

- `0x140007e70`
- `0x140011e04`
- `0x140019010`

## string_xrefs

- `0x140011e28`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
__int64 __fastcall wil_details_RtlRegisterFeatureConfigurationChangeNotification(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  FARPROC NtDllProcedureAddress; // rax

  NtDllProcedureAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
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
0x140011e04  mov     [rsp+arg_0], rbx
0x140011e09  mov     [rsp+arg_8], rsi
0x140011e0e  push    rdi
0x140011e0f  sub     rsp, 30h
0x140011e13  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140011e1a  mov     rbx, r9
0x140011e1d  mov     rdi, rdx
0x140011e20  mov     rsi, rcx
0x140011e23  test    rax, rax
0x140011e26  jnz     short loc_140011E47
0x140011e28  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x140011e2f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140011e34  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x140011e3b  test    rax, rax
0x140011e3e  jnz     short loc_140011E47
0x140011e40  mov     eax, 0C0000139h
0x140011e45  jmp     short loc_140011E58
0x140011e47  mov     r9, rbx
0x140011e4a  xor     r8d, r8d
0x140011e4d  mov     rdx, rdi
0x140011e50  mov     rcx, rsi
0x140011e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011e58  mov     rbx, [rsp+38h+arg_0]
0x140011e5d  mov     rsi, [rsp+38h+arg_8]
0x140011e62  add     rsp, 30h
0x140011e66  pop     rdi
0x140011e67  retn
```
